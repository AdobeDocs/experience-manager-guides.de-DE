---
title: AEM Guides mit Handbüchern und Wissens-KI verbinden
description: Erfahren Sie, wie Sie AEM Guides mit KI-Handbüchern verbinden
feature: Introduction
role: Admin
level: Experienced
source-git-commit: cdc177110720dbbe944a361142911a2e365ef8fa
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 2%
---

# Verbinden von Adobe Experience Manager Guides mit Handbüchern zur Wissens-KI (Beta)

>[!IMPORTANT]
>
> Diese Funktion ist standardmäßig deaktiviert. Wenden Sie sich an Ihr Customer Success-Team, um die Funktion „Handbücher zur Wissens-KI“ zu aktivieren.

In diesem Artikel erhalten Admins und Inhaltsingenieure einen umfassenden Prozess zur Konfiguration von Handbüchern für den Zugriff auf und das Hochladen von Experience Manager Guides-Inhalten für die Verwendung in der Wissens-KI.

## Prozessübersicht

| Schritt | Was du tun wirst |
|---|---|
| 1 | Erstellen Sie ein Service-Konto in Adobe Developer Console und konfigurieren Sie es für Ihre Umgebung. |
| 2 | Rufen Sie die E-Mail für das technische Konto aus der Datei mit den Anmeldedaten für das Service-Konto ab. |
| 3 | Gewähren Sie dem Service-Konto Zugriff in Wissens-KI, indem Sie eine Rolle erstellen und den Benutzer hinzufügen. |
| 4 | Konfigurieren einer Wissens-KI-Ausgabevorgabe in Experience Manager Guides und Hochladen von Inhalten. |


## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie über die folgenden Zugriffsrechte und Berechtigungen verfügen:

| Anforderung | Zweck |
|---|---|
| Adobe-Entwicklerkonsole | Erstellen Sie das Service-Konto und laden Sie seine JSON-Anmeldeinformationen herunter. |
| Adobe Experience Manager Guides | Erstellen Sie Inhalte und konfigurieren Sie die Ausgabevorgabe für Wissens-KI. |
| [KI-](https://guidesai.adobe.io/) | Rollen und Benutzer verwalten und hochgeladene Inhalte erhalten. |
| Berechtigung: Dienstkonten erstellen | Erforderlich in Adobe Developer Console, um ein Service-Konto zu erstellen. |
| Berechtigung: Verwalten von Benutzern und Rollen in Knowledge AI | Erforderlich, um dem Service-Konto Zugriff in Knowledge AI zu gewähren. |

## Erstellen eines Service-Kontos

Die Wissens-KI verwendet ein Service-Konto, um sich sicher zu authentifizieren und auf Inhalte zuzugreifen.

1. Befolgen Sie die Anweisungen unter [Konfigurieren der IMT-Konfiguration für Microservices](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-microservices-imt-config)

1. Erstellen Sie ein neues Service-Konto und laden Sie die generierte JSON-Anmeldedaten-Datei herunter.

1. Konfigurieren Sie die erforderlichen Umgebungseinstellungen mithilfe der heruntergeladenen Anmeldeinformationen.

Nach Abschluss des Vorgangs sollte das Service-Konto erfolgreich mit Ihrer Umgebung verknüpft werden.

>[!NOTE]
>
> Wenn Sie bereits ein Service-Konto für Ihre Umgebung erstellt und konfiguriert haben, können Sie mit dem nächsten Schritt fortfahren.


## E-Mail zum technischen Konto abrufen

Um Zugriff auf die Wissens-KI zu gewähren, identifizieren Sie das Service-Konto.

1. Öffnen Sie die heruntergeladene JSON-Datei für das Service-Konto.
1. Suchen Sie nach dem Feldnamen `technical_account_email`. Einen Wert ähnlich dem folgenden anzeigen:

   ```json
   {
   "technical_account_email": "a1b2c3d4e5f6@techacct.adobe.com"
   }
   ```

1. Kopieren Sie die mit `technical_account_email` verknüpfte E-Mail-Adresse. Sie verwenden diese E-Mail-Adresse im nächsten Schritt.

## Zugriff auf Knowledge AI gewähren

Damit das Service-Konto Inhalte verwalten und hochladen kann, fügen Sie sie mit den entsprechenden Berechtigungen zu Wissens-KI hinzu.

1. Öffnen Sie [Wissens-KI](https://guidesai.adobe.io/).
1. Navigieren Sie zu **Sicherheit > Rollen** und erstellen Sie eine Rolle mit den minimal erforderlichen Berechtigungen.
1. Navigieren Sie zu **Sicherheit > Benutzer > Benutzer hinzufügen**. Fügen Sie einen neuen Benutzer mit dem aus dem Service-Konto-JSON kopierten `technical_account_email` hinzu, wählen Sie die Domains aus **Dropdown-Liste &quot;**&quot; aus und weisen Sie die im vorherigen Schritt erstellte Rolle zu.

Das Service-Konto ist jetzt berechtigt, Inhaltsverwaltungs- und Upload-Vorgänge auszuführen.

## Konfigurieren der KI-Voreinstellung für Kenntnisse und Hochladen von Inhalten

Um Inhalte in der Wissens-KI zu veröffentlichen, konfigurieren Sie Experience Manager Guides, sobald Sie Berechtigungen eingerichtet haben.

1. Öffnen Sie **Map-** in Experience Manager Guides.
1. Navigieren Sie **Registerkarte &quot;**&quot;.
1. Wählen Sie das Symbol + aus, um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **Knowledge AI** aus der Dropdown-Liste **Typ** im Dialogfeld **Neue**) aus. Geben Sie **Name** ein und wählen Sie **Zum aktuellen Ordnerprofil hinzufügen** aus, um eine Ausgabevorgabe im aktuellen Ordnerprofil zu erstellen.

   ![Knowledge-AI-preset-creation](assets/knowledge-ai-preset.png)

1. Wählen Sie **Hinzufügen** aus. Die KI-Voreinstellung „Wissen“ wird erstellt.
1. Öffnen Sie die konfigurierte Wissens-KI-Voreinstellung.
1. Wählen Sie die Domain aus, für die dem `technical_account_email` die Rolle zugewiesen wurde, und klicken Sie auf **Inhalt hochladen**. Dadurch wird der Workflow zum Hochladen von Inhalten in die Knowledge AI Trigger. Warten Sie, bis der Upload-Vorgang abgeschlossen ist.

   ![Knowledge-AI-Domain](assets/knowledge-ai-domain.png)

1. Wählen Sie nach Abschluss des Uploads **In Wissens-KI öffnen** aus. Dadurch wird der Wissens-KI-Chat innerhalb der Domain unter Verwendung des hochgeladenen Inhalts geöffnet.

   ![Knowledge-AI-Open](assets/open-knowledge-ai.png)

Sie haben das Service-Konto erfolgreich konfiguriert, die erforderlichen Berechtigungen zugewiesen und Ihren Experience Manager Guides-Inhalt in der Wissens-KI verfügbar gemacht. Wenn Sie aktualisierte Inhalte veröffentlichen möchten, erstellen Sie eine neue Wissens-KI-Vorgabe und befolgen Sie die Schritte, die im Abschnitt [Konfigurieren der Wissens-KI-Vorgabe und Hochladen &#x200B;](#configure-knowledge-ai-preset-and-upload-content) Inhalts“ oben beschrieben sind.



