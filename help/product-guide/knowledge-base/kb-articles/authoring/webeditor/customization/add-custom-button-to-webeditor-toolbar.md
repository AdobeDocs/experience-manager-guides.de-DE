---
title: Fügen Sie eine neue, benutzerdefiniert umsetzbare Schaltfläche in der Web-Beditor-Symbolleiste hinzu.
description: Erfahren Sie, wie Sie eine neue benutzerdefinierte Schaltfläche in der WebBeditor-Symbolleiste hinzufügen und JavaScript aufrufen, um sie benutzerdefiniert zu bedienen.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Fügen Sie eine neue, benutzerdefiniert umsetzbare Schaltfläche in der Web-Beditor-Symbolleiste hinzu.

In diesem Artikel erfahren wir, wie Sie eine neue benutzerdefinierte Schaltfläche in der WebBeditor-Symbolleiste hinzufügen und JavaScript aufrufen, um den gewünschten benutzerdefinierten Vorgang auszuführen.

Das Hinzufügen einer umsetzbaren Schaltfläche zum Webserver umfasst die folgenden Schritte:
- Hinzufügen der Schaltfläche in der Datei *ui_config.json* an der Stelle, an der sie benötigt wird
- Registrieren des Klick-Ereignis auf der Schaltfläche im Webserver, damit der Benutzer beim Klicken eine Aktion ausführen kann


## Implementieren anhand eines Beispiels

Sehen wir uns dazu ein Beispiel an, in dem ein Autor einen Jira-Verweis zu einem Themenprologabschnitt hinzufügen möchte. Der Prologabschnitt mit eingebetteter jira reference-id kann wie folgt aussehen:

![Prologabschnitt mit JIRA-ID-Referenz](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

Das Element &quot;change-request-id&quot;, das die JIRA-ID enthält, sollte aus der API abgerufen werden (beispielsweise basierend auf einer bestimmten JIRA-Abfrage, die von der Anwendung dargestellt wird). Wenn der Benutzer den Prologabschnitt bearbeitet, sollte der Benutzer auf eine Schaltfläche klicken und eine jira-Referenz-ID aus der Symbolleiste des Web-Editors einfügen können, z. B.:

![Prolog-Abschnitt - JIRA-Referenz hinzufügen](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

Wenn der Benutzer auf die Schaltfläche klickt, sollte ein Dialogfeld angezeigt werden, in dem die möglichen Optionen abgerufen werden und der Benutzer die gewünschte JIRA-ID auswählen kann, z. B.:

![Prologue-Abschnitt JIRA-ID-Dialogfeld hinzufügen](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

, das dann die &quot;change-request-id&quot;zum Prolog hinzufügen sollte:

![Prologabschnitt mit JIRA-ID-Referenz](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## Implementieren


### Fügen Sie die Schaltfläche im Webserver hinzu, indem Sie sie in *ui_config.json* konfigurieren.

Verwenden Sie die Ordnerprofile, um die *ui_config.json* auf der Registerkarte &quot;XML Editor Configuration&quot;zu überprüfen und die Schaltflächenkonfiguration JSON zum gewünschten Abschnitt der Gruppe &quot;toolbar&quot;hinzuzufügen.

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[Verwenden Sie diesen Link, um mehr über das Ordnerprofil zu erfahren und ui_config.json zu konfigurieren](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### Verarbeiten des On-Click-Ereignisses für die neue Schaltfläche

    HINWEIS: Die unten erwähnten Schritte sind als in diesem Beitrag angehängtes Paket verfügbar


- Erstellen Sie nach dem Speichern des Ordnerprofils einen &quot;cq:ClientLibraryFolder&quot;in einem Projektverzeichnis (möglicherweise unter */apps*) und fügen Sie Eigenschaften hinzu, wie im folgenden Screenshot gezeigt:
  ![Client-Bibliothekseinstellungen für WebBeditor](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- Erstellen Sie unter diesem Client-Bibliotheksordner zwei Dateien, wie unten erwähnt:
   - *overrides.js*: , der über den JavaScript-Code verfügt, der das On-Click-Ereignis für &quot;insertJIRARef&quot;verarbeitet (verwenden Sie das angehängte Paket, um den Inhalt dieses JavaScripts zu erhalten)
   - *js.txt*: enthält die Datei &quot;overrides.js&quot;, um dieses JavaScript zu aktivieren

- Speichern Sie die Änderungen und Sie sollten bereit zum Testen sein.


### Testen

- Öffnen Sie den Web-Editor
- Wählen Sie in den Benutzereinstellungen das Ordnerprofil aus, in dem Sie die benutzerdefinierte Datei *ui_config.json* hinzugefügt haben. Wenn Sie es zum Profil Global hinzugefügt haben, verwenden Sie es wahrscheinlich bereits.
- Öffnen Sie ein Thema. Sie werden feststellen, dass die Symbolleiste über eine neue Schaltfläche &quot;Jira-Referenz einfügen&quot;verfügt.
- Sie können dann den Prologabschnitt wie unten angegeben zum Thema hinzufügen und versuchen, auf die Schaltfläche &quot;Jira-Referenz einfügen&quot;im Prologelement &quot;change-request-reference&quot;zu klicken

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

Im folgenden Screenshot erfahren Sie, wie er aussehen wird:

![Testen der neuen Schaltfläche](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Anhänge

- Beispiel-clientlibs-Paket, das die Webserver-Client-Bibliothek mit JavaScript-Code für die Symbolleisten-Schaltflächenaktion installiert: [Download mit diesem Link](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Beispiel *ui_config.json* , das Sie in ein Ordnerprofil hochladen können: [Download-Beispiel ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
