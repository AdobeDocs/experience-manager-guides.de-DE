---
title: Experience Manager Guides und Edge Delivery Services (Beta)
description: Erfahren Sie, wie Edge Delivery Services (Beta) die Authoring- und Publishing-Möglichkeiten für Experience Manager Guides erweitert.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 5808d42c530e55e309f192c99a0e71334c888b57
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# Experience Manager Guides und Edge Delivery Services (Beta)

Mit Adobe Experience Manager Guides können Sie Ihre DITA-Inhalte direkt in Edge Delivery Services (EDS) veröffentlichen, das derzeit in *Beta* verfügbar ist, und zwar über ein dediziertes GitHub-basiertes Veröffentlichungsprofil. Mit dieser Funktion können Unternehmen hochleistungsfähige, responsive Dokumentationserlebnisse bereitstellen und gleichzeitig DITA-basierte Authoring-Workflows in Experience Manager Guides beibehalten.

Weitere Informationen zur Verwendung von EDS in Adobe Experience Manager finden Sie in der [Übersicht über Edge Delivery Services](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/edge-delivery/overview).

Um die Veröffentlichung von Experience Manager Guides in EDS (Beta) zu aktivieren, müssen Sie eine Reihe von Konfigurationsschritten für GitHub und Experience Manager Guides durchführen. In den folgenden Abschnitten werden die einzelnen Schritte der Reihe nach beschrieben und erläutert, wie sie im gesamten Veröffentlichungs-Workflow zusammenarbeiten.

1. [Einrichten und Konfigurieren von GitHub für EDS (Beta)](#set-up-and-configure-github-for-eds-beta)
2. [Erstellen und Konfigurieren eines Veröffentlichungsprofils für EDS (Beta) in Experience Manager Guides](#create-and-configure-a-publish-profile-for-eds-beta-in-experience-manager)
3. [Anpassen der Ausgabe mithilfe von EDS-Blöcken](#customize-output-using-eds-blocks)

Eine kurze Videoanleitung finden Sie unter [Veröffentlichen in AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/publishing-in-aem-guides-aug25).



## Einrichten und Konfigurieren von GitHub für EDS (Beta)

In diesem Abschnitt wird beschrieben, wie Sie GitHub für die Verwendung mit EDS (Beta) einrichten und konfigurieren. Es behandelt das Erstellen eines Repositorys mit dem Adobe-Textbaustein, das Verbinden von GitHub mit Adobe Experience Manager über AEM Code Sync, das Konfigurieren der erforderlichen GitHub- und OAuth-Anwendungen und das Definieren des Repository-Bereitstellungspunkts, der für die Veröffentlichung von Inhalten verwendet wird.

### Erstellen eines GitHub-Repositorys für EDS (Beta)

EDS (Beta) erfordert ein GitHub-Repository mit einer vordefinierten Struktur. Adobe bietet ein offizielles Textbaustein-Repository, das speziell für Experience Manager Guides-Anwender entwickelt wurde.

Führen Sie die folgenden Schritte aus, um Ihr Repository zu erstellen:

1. Öffnen Sie die [`aem-guides-boilerplate`](https://github.com/adobe/aem-guides-boilerplate) Experience Manager Guides-Textbausteinvorlagen-Repository .
   ![](assets/eds-boilerplate-template.png){align="left"}

2. Erstellen Sie mithilfe dieser Vorlage ein neues Repository. Erfahren Sie [Erstellen eines Repositorys aus einer Vorlage](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template). Stellen Sie sicher, dass die Repository-Sichtbarkeit auf &quot;*&quot;* ist, damit der Zugriff über EDS möglich ist.

   ![](assets/eds-create-new-repo.png){align="left"}

Das Repository wird jetzt erstellt und an der Textbausteinvorlagenstruktur ausgerichtet.

![](assets/eds-repo-created-github-view.png){align="left"}

### Verbinden von GitHub mit Adobe über die AEM-Codesynchronisierung

Adobe Experience Manager verwendet eine GitHub-Anwendung namens **AEM Code Sync**, um Inhalte von Experience Manager Guides auf GitHub zu pushen.

Führen Sie die folgenden Schritte aus, um die Anwendung *AEM Code Sync* zu installieren und zu konfigurieren:

1. Navigieren Sie zur Seite [AEM Code Sync](https://github.com/apps/aem-code-sync) und wählen Sie **Installieren**.
2. *AEM Code Sync* überwacht Repository-Änderungen und stellt sicher, dass Aktualisierungen korrekt an GitHub gesendet werden.

   >
   >
   > Stellen Sie bei der Installation der Anwendung sicher, dass Sie dasselbe GitHub-Konto verwenden, dem das Repository gehört.

   ![](assets/eds-aem-code-sync-page.png){align="left"}
3. Gewähren Sie auf der nächsten Seite Zugriff auf das von Ihnen erstellte Repository. Wählen Sie dazu die Option **Nur Repositorys auswählen** und wählen Sie dann Ihr Repository aus der Dropdown-Liste aus.

   ![](assets/eds-aem-code-sync-install-authorize.png){width="350" align="left"}
4. Wählen Sie **Installieren und autorisieren** aus.

Sie werden zur GitHub-Setup-Seite weitergeleitet, auf der die erfolgreiche Registrierung der Anwendung *AEM Code Sync* bestätigt wird. Auf dieser Seite können Sie auch die Vorschau- und Live-URLs für Ihre Website speichern.

![](assets/eds-aem-code-sync-registered.png){align="left"}

### Erstellen einer neuen GitHub-App

1. Navigieren Sie auf GitHub zur linken Seitenleiste und wählen Sie **Entwicklereinstellungen**.
2. Wählen Sie in der linken Seitenleiste **GitHub-Apps** aus.
3. Wählen Sie **Neue GitHub-App** aus.

   ![](assets/eds-new-github-app.png){width="650" align="left"}
4. Geben **auf der Seite „Neue GitHub** App registrieren“ die folgenden Details an:
   - **GitHub-App-Name**: Geben Sie einen Namen für Ihre App ein. `USERNAME-eds-app` Sie beispielsweise, wobei USERNAME Ihr GitHub-Benutzername ist.
   - **Homepage-URL**: Geben Sie die URL für die Experience Manager Guides-Instanz ein.

     Beispiel-URL (Format): `https://<aem-author-url>/libs/fmdita/clientlibs/xmleditor/page.html`

     Beispiel-URL: `https://author-p16602-e335172-cmstg.adobeaemcloud.com/libs/fmdita/clientlibs/xmleditor/page.html`
   - **Callback-URL**: Wie die Homepage-URL.
   - **Webhook-URL**: Deaktivieren Sie diese Option.
   - **Repository-Berechtigungen**: Legen Sie **Lese- und**) für *Aktionen, Administration und* fest.
5. Wählen Sie **GitHub-App erstellen** aus.

Ihre App ist jetzt bereit. Sie werden zur Seite **Einstellungen** Ihrer GitHub-App weitergeleitet.

![](assets/eds-github-app-registered-page.png){align="left"}

### Erstellen einer neuen OAuth-App

Zum Authentifizieren von Benutzern beim Erstellen eines EDS (Beta)-Veröffentlichungsprofils in Experience Manager Guides ist eine OAuth-App erforderlich. Dies ermöglicht einen sicheren Anmeldefluss mit einer *Client-ID* und *Client-Geheimnis*.

Führen Sie die folgenden Schritte aus, um eine neue OAuth-App zu erstellen:

1. Navigieren Sie auf GitHub zur linken Seitenleiste und wählen Sie **Entwicklereinstellungen**.
2. Wählen Sie in der linken Seitenleiste **OAuth-Apps** aus.
3. Wählen Sie **Neue OAuth-App** aus.

   ![](assets/eds-new-oauth-app.png){width="650" align="left"}
4. Registrieren Sie Ihre Anwendung, indem Sie die folgenden obligatorischen Details angeben:
   - **Anwendungsname**: Geben Sie den Namen Ihres EDS-Repositorys ein
   - **Homepage-URL**: Geben Sie die URL für die Experience Manager Guides-Instanz ein. (Das Beispiel-URL-Format finden Sie in Schritt 4 des Abschnitts [Erstellen einer neuen GitHub](#create-a-new-github-app)App).
   - **Autorisierungs-Callback-URL**: identisch mit der Homepage-URL
5. Wählen Sie die Option **Gerätefluss aktivieren** und wählen Sie dann **Anwendung registrieren**, um die Registrierung abzuschließen.

   ![](assets/eds-new-github-app-register.png){width="650" align="left"}

Ihre App ist jetzt bereit. Notieren Sie sich die *Client-ID*. Experience Manager Guides Beim Konfigurieren des Veröffentlichungsprofils in *können Sie jetzt oder* bis zu fünf Client-Geheimnisse generieren.

![](assets/eds-new-oauth-app-page.png){align="left"}


### Konfigurieren der Bereitstellungspunkt-URL im EDS-Repository (Beta)

EDS (Beta) liest Inhalte aus einem GitHub-Repository-Pfad, der als *Bereitstellungspunkt*-URL in der `fstab.yaml`-Datei definiert ist.

So konfigurieren Sie die Bereitstellungspunkt-URL in der `fstab.yaml`:

1. Öffnen Sie die `fstab.yaml` in Ihrem Repository und aktualisieren Sie Folgendes:
   - `your-user-name`
   - `your-repo-name`

   >
   >
   > In der Bereitstellungs-URL gibt `main` die Verzweigung an, in der Sie die Inhalte veröffentlichen möchten, und `docs` den Stammordner des EDS (Beta)-Repositorys, an dem Sie arbeiten. Wenn Sie es vorziehen, den Verzweigungsnamen auf GitHub zu ändern, müssen Sie denselben Verzweigungsnamen in der *mountpoint*-URL (in der `fstab.yaml`-Datei) und das entsprechende EDS-Veröffentlichungsprofil in Experience Manager Guides aktualisieren.

   ![](assets/eds-fstab-yaml-file.png){width="650" align="left"}
2. Wählen Sie **Änderungen übernehmen**, geben Sie Details zum Commit ein und bestätigen Sie.
3. Kehren Sie zu [Entwicklereinstellungen](https://github.com/settings/apps) zurück, suchen Sie Ihre App und klicken Sie auf **Bearbeiten**.

   ![](assets/eds-edit-github-app.png){width="650" align="left"}
4. Navigieren Sie zur Seite **Programm installieren** und wählen Sie **Installieren** aus.

   ![](assets/eds-install-eds-app.png){width="650" align="left"}
5. Wiederholen Sie die Schritte 2 und 3 aus dem Abschnitt [Verbinden von GitHub mit Adobe über AEM Code-](#connect-github-to-adobe-via-aem-code-sync)), um das Repository zu autorisieren.

## Erstellen und Konfigurieren eines Veröffentlichungsprofils für EDS (Beta) in Experience Manager

In den folgenden Abschnitten werden die einzelnen Schritte der Reihe nach beschrieben und erläutert, wie Sie ein EDS (Beta)-Veröffentlichungsprofil einrichten, eine Ausgabevorgabe konfigurieren und mithilfe von EDS (Beta) in Experience Manager Guides eine Ausgabe generieren.

### Erstellen des EDS (Beta)-Veröffentlichungsprofils

1. Wechseln Sie zu **[Workspace]** Einstellungen **>** Profile **veröffentlichen**.
2. Wählen Sie das Symbol **+** aus, um ein neues Veröffentlichungsprofil zu erstellen, und geben Sie die folgenden Details an:
   - **Servertyp**: Wählen Sie **GitHub Edge Delivery Services (Beta)** aus der Dropdown-Liste aus.
   - **Name**: Geben Sie einen Namen für dieses Profil ein.
   - **Repository-Name**: Verwenden Sie den aus dem Textbaustein erstellten GitHub-Repository-Namen.
   - **Benutzername**: Geben Sie Ihren GitHub-Benutzernamen ein.
   - **Verzweigung Main**: Auf Main (Standard) festlegen.
   - **Stammordner**: Auf „docs“ (Standard) festlegen.
   - **Client-ID und Client-Geheimnis**: Rufen Sie diese aus Ihrer GitHub-App ab (weitere Informationen finden [ im Abschnitt Erstellen einer neuen OAuth](#create-a-new-oauth-app)App).
3. Wählen Sie **Anmelden** aus, um sich zu authentifizieren.

   ![](assets/eds-publish-profile.png){width="650" align="left"}
4. Wählen Sie nach erfolgreicher Authentifizierung **Speichern** aus.

Ihr EDS (Beta)-Veröffentlichungsprofil ist jetzt konfiguriert.

### Erstellen einer Ausgabevorgabe für EDS (Beta) und Generieren einer Ausgabe

1. Öffnen Sie Ihre Karte in der Kartenkonsole.
2. Wählen Sie auf **Registerkarte** Ausgabevorgaben“ **+** aus, um eine neue Ausgabevorgabe zu erstellen.
3. Geben Sie **Dialogfeld „Neue**&quot; die folgenden Details ein:
   - **type**: **Edge Delivery-Service (Beta) auswählen**
   - **Name**: Geben Sie einen Namen für diese Voreinstellung an
4. Wählen Sie **Hinzufügen** aus.

   ![](assets/eds-output-preset.png){width="650" align="left"}
5. Öffnen Sie die neu erstellte EDS (Beta)-Ausgabevorgabe und navigieren Sie zur Registerkarte **Konfiguration** .
   - Wählen Sie das im vorherigen Schritt erstellte Veröffentlichungsprofil aus.
   - Aktivieren Sie **Push zur Live-Schaltung**.

   Wenn **Push an Live** aktiviert ist, wird die generierte Ausgabe an GitHub übergeben, und die entsprechenden Aktualisierungen werden sofort an die Live-Website übertragen.

   ![](assets/eds-output-preset-config-tab.png){width="650" align="left"}

6. Wählen Sie **Speichern** und dann **Ausgabe generieren**.

>
>
> Die generierte Ausgabe wird im Ordner **docs** des EDS (Beta)-Repositorys gespeichert.

Die EDS (Beta)-Ausgabe wird jetzt generiert. Der Inhalt wird in einem sauberen, responsiven Layout präsentiert. Sie enthält reguläre Elemente wie den Seitentitel, Breadcrumbs, Textinhalte und alle im Thema verwendeten Blöcke. Das Inhaltsverzeichnis auf der linken Seite (generiert aus der Karte) hilft Ihnen, durch Themen zu navigieren, während ein Mini-Inhaltsverzeichnis auf der rechten Seite die Abschnitte innerhalb der aktuellen Seite hervorhebt. Die gesamte Ausgabe ist vollständig responsiv und sorgt für ein optimiertes, konsistentes Leseerlebnis auf allen Geräten.

![](assets/eds-site-output.png){align="left"}

## Anpassen der Ausgabe mithilfe von EDS-Blöcken

EDS verwendet `blocks`, um zu steuern, wie verschiedene Teile Ihres Inhalts formatiert und angezeigt werden. Sie können vorhandene Blöcke ändern oder benutzerdefinierte Blöcke erstellen.

Die folgenden Beispiele führen Sie durch die Anpassung eines bestehenden Bausteins und die Erstellung eines neuen Bausteins, um die endgültige EDS (Beta)-Ausgabe in Experience Manager Guides zu gestalten.

### Anpassen eines Breadcrumb-Blocks, um seine Textfarbe zu aktualisieren

Breadcrumbs werden seitenübergreifend verwendet, damit Benutzer verstehen können, wo sie sich in der Dokumentation befinden. Da dieser Baustein auf der gesamten Website konsistent angezeigt wird, ermöglicht eine Aktualisierung seines Stils eine einheitliche Design-Aktualisierung.

Führen Sie die folgenden Schritte aus, um einen Breadcrumb-Block anzupassen und seine Textfarbe zu aktualisieren:

1. Wechseln Sie zu Ihrem GitHub-Repository und öffnen Sie den Ordner `blocks` .
2. Wählen Sie den **Breadcrumbs**-Block aus.

   ![](assets/eds-breadcrumbs.png){width="650" align="left"}
3. Öffnen Sie die `css` und aktualisieren Sie die Textfarbe.
4. Übertragen Sie die Änderungen an GitHub.
5. Aktualisieren Sie die Live-Website, um die Aktualisierungen anzuzeigen.

### Aktualisieren von EDS (Beta)-Skripten, um benutzerdefinierte Elemente in der veröffentlichten Ausgabe zu erstellen

In einigen Fällen möchten Sie möglicherweise nur einen bestimmten Teil Ihres Inhalts formatieren. Führen Sie die folgenden Schritte aus, um dies mithilfe eines benutzerdefinierten Blocks zu erreichen.

1. Öffnen Sie die Themendatei und wählen Sie den Text in einem Tag-Element aus.

   Im folgenden Screenshot ist der Inhalt innerhalb des `example`-Tags ausgewählt.
   ![](assets/eds-example-tag-org-output.png){width="650" align="left"}
2. So konfigurieren Sie den Text im `example`-Tag:
   - Navigieren Sie zu **Inhaltseigenschaften**.
   - Fügen Sie das Attribut `outputclass` hinzu.
   - Legen Sie den Wert auf `example eds-force-block` fest.
   - Wählen Sie **Hinzufügen** aus.
     ![](assets/eds-example-tag.png){width="650" align="left"}
3. Speichern und regenerieren Sie die Ausgabe.
4. Erstellen Sie einen neuen Ordner mit demselben Namen wie der `outputclass` im `blocks`. Erfahren Sie mehr über [Hinzufügen von Dateien zu einem Repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository#adding-a-file-to-a-repository-using-the-command-line).

   ![](assets/eds-example-folder.png){width="650" align="left"}
5. Fügen Sie die erforderlichen `css` und optionale `js` hinzu.

   ![](assets/eds-example-folder-subfolders.png){width="650" align="left"}
6. Änderungen übernehmen und Ausgabe neu generieren.

Der ausgewählte Inhalt zeigt jetzt die benutzerdefinierten Stile an, die in Ihrem Block definiert sind.

![](assets/eds-example-output.png){width="650" align="left"}