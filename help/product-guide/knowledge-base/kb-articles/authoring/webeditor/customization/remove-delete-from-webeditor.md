---
title: Entfernen Sie die Option "Löschen"aus dem Dateikontextmenü im WebEditor für bestimmte Benutzer
description: Erfahren Sie, wie Sie den WebEditor anpassen, indem Sie die Option "Löschen"aus dem Dateikontextmenü für bestimmte Benutzer/Gruppen entfernen.
source-git-commit: aacc04e2fb6ca061825e5e219ad6e03bf711b3d0
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---


# Option &quot;Löschen&quot;aus dem Dateikontextmenü in WebEditor entfernen

In diesem Artikel erfahren wir, wie wir die Option &quot;Löschen&quot;im Dateikontextmenü im Guides-Web-Editor für bestimmte Benutzer oder Gruppen ausblenden. Weitere Anpassungen der Menüoptionen im Dateikontext finden Sie unter Guides Extension Framework . Weitere Informationen finden Sie unter [here](https://github.com/adobe/guides-extension/tree/main).

Wie Sie aus dem folgenden Snippet sehen können, ist im Dateikontextmenü für diesen bestimmten Benutzer die Option &quot;Löschen&quot;verfügbar.

![Dateikontextmenü mit Löschen](../../../assets/authoring/file-contextmenu-Delete.png)

Lassen Sie uns nun sehen, wie wir die Löschoption für diesen Benutzer ausblenden können.

## Implementierungsschritte:

- Navigieren Sie von AEM Startseite aus zu Tools > Sicherheit > Berechtigungen .
- Wählen Sie die Gruppe oder den Benutzer aus dem Suchfeld aus.
- Klicken Sie oben rechts auf &quot;ACE hinzufügen&quot;.
- Wählen Sie den Ordnerpfad aus.
- Schließen Sie die Berechtigungen &quot;jcr:removeChildNodes&quot;und &quot;jcr:removeNode&quot;ein.
- Wählen Sie &quot;Berechtigungstyp&quot;als &quot;Ablehnen&quot;und klicken Sie auf &quot;Hinzufügen&quot;, wie unten dargestellt.

![Benutzerberechtigungen - ACE verweigern](../../../assets/authoring/permission-ACE-Delete.png)

![Zugriffssteuerungsliste in Berechtigungen](../../../assets/authoring/delete-acl.png)

### Testen

- Melden Sie sich bei AEM als Benutzer an, für den die ACE hinzugefügt wurde.
- Öffnen Sie den Web-Editor.
- Gehen Sie zur Repository-Ansicht und wählen Sie den Ordner aus, für den die ACE hinzugefügt wurden.
- Öffnen Sie das Dateikontextmenü.
- Die Option &quot;Löschen&quot;wird nicht im Kontextmenü angezeigt.

Das Dateikontextmenü sieht nun wie folgt aus:

![Dateikontextmenü ohne Löschen](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Web Editor as they are also tied to delete process at the backend.
```
