---
title: Einrichten und Konfigurieren von GitLab für Edge Delivery Services
description: Erfahren Sie, wie Sie GitLab-Repositorys, Zugriffstoken, Cloud Manager und Webhooks konfigurieren und Ihr eigenes Git verwenden, um Inhalte von Experience Manager Guides in Edge Delivery Services zu veröffentlichen.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97620587a9e736e0886ea4d7158af330814e6392
workflow-type: tm+mt
source-wordcount: '1256'
ht-degree: 3%
---

# Einrichten und Konfigurieren von GitLab für Edge Delivery Services

Um Inhalte mithilfe von GitLab von Experience Manager Guides in Edge Delivery Services (EDS) zu veröffentlichen, verbinden Sie ein GitLab-Repository über die Cloud Manager-Funktion *Eigenes Git* (BYOG) hinzufügen mit Ihrer EDS-Site. In diesem Artikel werden die Schritte nacheinander aufgelistet. Einzelheiten zu den einzelnen Schritten finden Sie in der entsprechenden Dokumentation.

## Funktionsweise

- Ein **GitHub-Repository** erstellt die EDS-Site über die AEM Code Sync -App.
- Ein **GitLab-Repository** speichert die von Experience Manager Guides veröffentlichten Inhalte.
- **Cloud Manager** verbindet beide, indem GitLab-Push-Ereignisse (Webhook) empfangen und mit der EDS-Site synchronisiert werden.

## Voraussetzungen

- Zugriff auf GitHub und GitLab (GitLab.com oder selbst gehostet) zum Erstellen von Repositorys und Token.
- Zugriff auf Cloud Manager mit einer Rolle, die das Hinzufügen von Repositorys ermöglicht (Bereitstellungs-Manager oder Geschäftsinhaber).
- Systemadministrator oder API-Entwicklerrolle in Ihrem Adobe-Unternehmen, um die Cloud Manager-API-Integration zu erstellen.
- Eine im Konfigurations-Service registrierte `aem.live`. Weitere Informationen finden Sie unter [Einrichten des Konfigurationsdienstes](https://www.aem.live/docs/config-service-setup).

## Konfigurationssequenz

1. [Erstellen der EDS-Site mit GitHub](#1-create-the-eds-site-using-github-create-eds-site)
2. [Erstellen des GitLab-Repositorys](#2-create-the-gitlab-repository)
3. [Konfigurieren der Bereitstellungspunkt-URL](#3-configure-the-mountpoint-url)
4. [Erstellen von GitLab-Zugriffstoken](#4-create-gitlab-access-tokens)
5. [Hinzufügen des GitLab-Repositorys zu Cloud Manager](#5-add-the-gitlab-repository-to-cloud-manager)
6. [Generieren eines Cloud Manager-API-Schlüssels](#6-generate-a-cloud-manager-api-key)
7. [Konfigurieren des GitLab-Webhooks](#7-configure-the-gitlab-webhook)
8. [Hinzufügen der EDS-Site zu Cloud Manager](#8-add-the-eds-site-to-cloud-manager)
9. [Verbinden Sie das Repository mit Bring Your Own Git](#9-connect-the-repository-using-bring-your-own-git)
10. [Konfigurieren der EDS-Site für die Verwendung von Cloud Manager](#10-configure-the-eds-site-to-use-cloud-manager)
11. [Synchronisieren und überprüfen](#11-sync-and-verify)
12. [Aus Experience Manager Guides veröffentlichen](#12-publish-from-experience-manager-guides)

### &#x200B;1. Erstellen der EDS-Site mit GitHub {#create-eds-site}

Erstellen Sie ein GitHub-Repository aus dem AEM Guides-Textbaustein und installieren Sie die AEM Code Sync -App darauf. Speichern Sie die generierte **Live-URL** (`https://<branch>--<github-repo>--<github-username>.aem.live`) für später.

Anweisungen hierzu finden Sie unter [Erstellen eines GitHub-Repositorys für EDS](./configure-eds.md#create-a-github-repository-for-eds) und [Verbinden von GitHub mit Adobe über die AEM-Codesynchronisierung](./configure-eds.md#connect-github-to-adobe-via-aem-code-sync).

>[!IMPORTANT]
>
> Erstellen Sie die EDS-Site nicht mit der Option „One-click“ in Cloud Manager. Auf diese Weise erstellte Sites erhalten Sie nicht die erforderlichen Administratorberechtigungen für die späteren Schritte. Weitere Informationen finden Sie unter [Vorbereiten der Edge Delivery Services-Site](https://www.aem.live/developer/byo-git#1.-prepare-your-edge-delivery-services-site).

### &#x200B;2. Erstellen des GitLab-Repositorys

Erstellen Sie ein separates GitLab-Repository (z. B. `my-eds-gitlab`) aus demselben AEM Guides-Textbaustein. Experience Manager Guides veröffentlicht die generierte Ausgabe in diesem Repository. EDS erwartet eine `main`.

Um das Repository zu erstellen, erstellen Sie entweder ein leeres Projekt und übertragen Sie den Inhalt von [aem-guides-boilerplate](https://github.com/adobe/aem-guides-boilerplate) oder importieren Sie das Boilerplate in ein neues Projekt. Anweisungen hierzu finden Sie unter [Erstellen eines Projekts](https://docs.gitlab.com/user/project/) und [Importieren Ihres Projekts von GitHub nach GitLab](https://docs.gitlab.com/user/project/import/github/) in der GitLab-Dokumentation.

### &#x200B;3. Konfigurieren der Bereitstellungspunkt-URL

Aktualisieren Sie im GitHub-Repository `fstab.yaml` so, dass die Inhaltsquelle auf das GitLab-Repository verweist, und übertragen Sie die Änderung auf `main`.

```text
https://<worker URL>/gitlab/<git acc domain>/<git username>/<git repo>/main/docs
```

| Parameter | Beschreibung |
|---|---|
| `<worker URL>` | Von Adobe bereitgestellte Arbeitsknoten-URL. |
| `<git acc domain>` | GitLab-Domain, z. B. `gitlab.com`, oder Ihre selbst gehostete Domain. |
| `<git username>` | Ihr GitLab-Benutzername. |
| `<git repo>` | Name des GitLab-Repositorys |
| `main` / `docs` | Verzweigung und Stammordner Standardeinstellungen für Experience Manager Guides. |

### &#x200B;4. Erstellen von GitLab-Zugriffstoken

Erstellen Sie die Zugriffstoken, die für Folgendes erforderlich sind:

- **Cloud Manager**, um das Repository zu validieren und darauf zuzugreifen. Weitere Informationen finden Sie unter [Hinzufügen externer Repositorys in Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).
- **Experience Manager Guides-Veröffentlichungsprofil**, um die veröffentlichte Ausgabe zu übertragen. Erstellen Sie ein GitLab-Projekt-Zugriffstoken mit der Rolle **Entwickler** und dem `api`. Weitere Informationen finden Sie in der [GitLab-Dokumentation](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html).

>[!NOTE]
>
> Verlängern Sie Token, bevor sie ablaufen. Die Veröffentlichung schlägt fehl, wenn das Token im Veröffentlichungsprofil abgelaufen ist. Um ein von Cloud Manager verwendetes Token zu aktualisieren, lesen Sie [Zugriffstoken für externe Repositorys verwalten](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/manage-access-tokens).

### &#x200B;5. Hinzufügen des GitLab-Repositorys zu Cloud Manager

Gehen Sie in Cloud Manager zu **Repositorys** > **Repository hinzufügen**, wählen Sie **Privates Repository** aus und überprüfen Sie die Eigentümerschaft mithilfe des Zugriffstokens. Warten Sie, bis der Repository-Status **Bereit** ist. Die BYOG-Option ist erst verfügbar, wenn mindestens ein externes Repository bereit ist.

Anweisungen hierzu finden Sie unter [Hinzufügen externer Repositorys in Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).

### &#x200B;6. Generieren eines Cloud Manager-API-Schlüssels

Erstellen Sie eine API-Integration in Adobe Developer Console (**Cloud Manager** API, **OAuth Server-to-Server**) und kopieren Sie die **Client-ID (API-Schlüssel)**.

Anweisungen hierzu finden Sie unter [Erstellen eines API-Integrationsprojekts](https://developer.adobe.com/experience-cloud/cloud-manager/guides/getting-started/create-api-integration).

### &#x200B;7. Konfigurieren des GitLab-Webhooks

Wählen Sie in Cloud Manager **Webhook konfigurieren** für das Repository aus und kopieren Sie die **Webhook-URL** und **Secret**. Hängen Sie den API-Schlüssel an die URL an (`<webhook URL>&api-key=<CLIENT_ID>`). Wechseln Sie in GitLab zu **Einstellungen** > **Webhooks**, fügen Sie die URL und das Geheimnis hinzu, wählen Sie die `main` Verzweigung aus und aktivieren Sie **Push-Ereignisse**.

Weitere Informationen finden Sie unter [Konfigurieren des externen Repositorys in Cloud Manager](https://www.aem.live/developer/byo-git#2.-configure-your-external-repository-in-cloud-manager).

### &#x200B;8. Hinzufügen der EDS-Site zu Cloud Manager

Wechseln Sie in Cloud Manager zu **Edge Delivery** > **Edge Delivery-Site hinzufügen** und geben Sie die in Schritt 1 gespeicherte Live-URL ein. Führen Sie die Eigentümervalidierung durch.

Anweisungen hierzu finden Sie unter [Hinzufügen einer Edge Delivery-Site](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/edge-delivery-sites/add-edge-delivery-site).

### &#x200B;9. Verbinden Sie das Repository mit Bring Your Own Git

Wählen Sie auf der EDS-Website in Cloud Manager **Eigenes Git (BYOG)**, wählen Sie das GitLab-Repository aus und bestätigen Sie. Kopieren Sie die generierten geheimen Daten und speichern Sie sie sicher. Er wird nur einmal angezeigt und es wird ein neuer geheimer Schlüssel generiert, wenn Sie die Site neu konfigurieren.

Weitere Informationen finden Sie unter [Konfigurieren Ihrer Edge Delivery-Site in Cloud Manager](https://www.aem.live/developer/byo-git#3.-configure-your-edge-delivery-site-in-cloud-manager).

### &#x200B;10. Konfigurieren der EDS-Site für die Verwendung von Cloud Manager

Setzen Sie die Code-Quelle der EDS-Site auf das Cloud Manager-Repository, indem Sie die **Programm-ID** (`/program/<PROGRAM_ID>/`) und **Repository-ID** (`/repo/<REPO_ID>/`) aus der Webhook-URL verwenden. Erstellen Sie dann aus Schritt 9 geheime Daten mit dem Namen `cm-byog` mit den geheimen Daten.

Für die Admin-API-Aufrufe anzeigen Sie [Konfigurieren Sie Ihre AEM-Site für die Verwendung von Cloud Manager](https://www.aem.live/developer/byo-git#4.-configure-your-aem-site-to-use-cloud-manager).

### &#x200B;11. Synchronisieren und überprüfen

Wählen Sie in Cloud Manager **Code synchronisieren** aus dem Menü der Site aus und wählen Sie die `main`. Öffnen Sie dann `https://main--<site>--<org>.aem.page`, um die Site zu überprüfen.

Weitere Informationen finden Sie unter [Trigger der ersten Synchronisierung](https://www.aem.live/developer/byo-git#5.-trigger-your-first-sync) und [AEM-Site überprüfen](https://www.aem.live/developer/byo-git#6.-verify-your-aem-site).

### &#x200B;12. Aus Experience Manager Guides veröffentlichen

Erstellen Sie ein EDS-Veröffentlichungsprofil mit **Git-Kontotyp** , der auf **GitLab** festgelegt ist, unter Verwendung des Projektzugriffs-Tokens aus Schritt 4. Wählen Sie dann dieses Profil in einer EDS-Ausgabevorgabe aus und generieren Sie die Ausgabe. Die Ausgabe wird in den `docs` des GitLab-Repositorys übertragen.

Anweisungen hierfür finden Sie [Erstellen des EDS-Veröffentlichungsprofils](./configure-eds.md#create-the-eds-publish-profile-for-github-or-gitlab) und [Erstellen einer Ausgabevorgabe für EDS und Generieren einer Ausgabe](./configure-eds.md#create-an-output-preset-for-eds-and-generate-output).

## Fehlerbehebung

- **Site zeigt alten Inhalt nach einer Push-Benachrichtigung an** Überprüfen Sie, ob der Webhook Ereignisse an Cloud Manager sendet, und überprüfen Sie dann den Status des neuesten Synchronisierungsauftrags.
- **Synchronisierungsfehler `Unable to fetch hlxignore: 401`:** Das `cm-byog` ist falsch. Erstellen Sie sie mit den geheimen Daten aus Schritt 9 neu.
- **Repository ist mit einer anderen Website verknüpft** Ein Cloud Manager-Repository kann jeweils nur mit einer Website verknüpft werden. Um ein Repository für mehrere Sites freizugeben, verwenden Sie [Repoless](https://www.aem.live/docs/repoless).

Weitere Informationen finden Sie unter [Fehlerbehebung in „Eigenes Git einbringen](https://www.aem.live/developer/byo-git#troubleshooting).
