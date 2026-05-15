---
title: Entfernen der Option „Löschen“ aus dem Dateikontextmenü im Web-Editor für bestimmte Benutzer
description: Erfahren Sie, wie Sie den Web-Editor anpassen können, indem Sie die Option „Löschen“ aus dem Dateikontextmenü für bestimmte Benutzer/Gruppen entfernen.
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
TQID: https://experienceleague.adobe.com/dzbMsXUoEibR5QxKB-Z-h4qGnQaX2NmIYLTtxVJHE-A
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 241
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
- Schließen Sie die Berechtigungen „jcr:removeChildNodes&quot; und „jcr:removeNode&quot; ein.
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
