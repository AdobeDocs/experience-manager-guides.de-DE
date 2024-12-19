---
title: Entfernen der Option „Löschen“ aus dem Dateikontextmenü im Web-Editor für bestimmte Benutzer
description: Erfahren Sie, wie Sie den Web-Editor anpassen können, indem Sie die Option „Löschen“ aus dem Dateikontextmenü für bestimmte Benutzer/Gruppen entfernen.
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Option „Löschen“ aus dem Datei-Kontextmenü im Web-Editor entfernen

In diesem Artikel erfahren Sie, wie Sie die Option „Löschen“ im Dateikontextmenü im AEM Guides-Web-Editor für bestimmte Benutzende oder Gruppen ausblenden. Für andere Anpassungen der Optionen im Datei-Kontextmenü überprüfen Sie bitte das Handbuch-Erweiterungs-Framework. Weitere Informationen finden Sie [hier](https://github.com/adobe/guides-extension/tree/main).

Wie Sie im folgenden Ausschnitt sehen können, ist im Dateikontextmenü für diesen Benutzer die Option „Löschen“ verfügbar.

![Datei-Kontextmenü mit Löschen](../../../assets/authoring/file-contextmenu-Delete.png)

Sehen wir uns nun an, wie wir die Option „Löschen“ für diesen Benutzer ausblenden können.

## Implementierungsschritte:

- Navigieren Sie von der AEM-Startseite aus zu Tools > Sicherheit > Berechtigungen .
- Wählen Sie die Gruppe oder den Benutzer aus dem Suchfeld aus.
- Klicken Sie oben rechts auf „ACE hinzufügen“.
- Wählen Sie den Ordnerpfad.
- Einschließen der Berechtigungen „jcr:removeChildNodes“ und „jcr:removeNode“.
- Wählen Sie „Berechtigungstyp“ als „Ablehnen“ aus und klicken Sie wie unten dargestellt auf „Hinzufügen“.

![Benutzerberechtigung „ACE verweigern](../../../assets/authoring/permission-ACE-Delete.png)

![Zugriffssteuerungsliste in Berechtigungen](../../../assets/authoring/delete-acl.png)

### Testen

- Melden Sie sich bei AEM als der Benutzer an, für den der ACE hinzugefügt wurde.
- Öffnen Sie den Web-Editor.
- Gehen Sie zur Repository-Ansicht und wählen Sie den Ordner aus, für den die ACEs hinzugefügt wurden.
- Öffnen Sie das Datei-Kontextmenü.
- Die Option „Löschen“ wird nicht im Kontextmenü angezeigt.

Das Datei-Kontextmenü sieht nun wie folgt aus:

![Datei-Kontextmenü ohne Löschen](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Web Editor as they are also tied to delete process at the backend.
```
