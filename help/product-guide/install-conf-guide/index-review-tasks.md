---
title: Indizierung durchführen, um alle Prüfungsaufgaben in das Kommentarbedienfeld aufzunehmen
description: Erfahren Sie, wie Sie vorhandene Prüfungsaufgaben indizieren, damit sie neben neueren Aufgaben im Dropdown-Menü Prüfungsaufgabe des Kommentarbedienfelds angezeigt werden.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 7d0c757b647a2e6c5e563f0ed7db6a7225769033
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Indizieren, um alle Prüfungsaufgaben für ein Thema in den Kommentarbereich aufzunehmen

Die Funktion [Alle Prüfungsaufgaben für ein Thema anzeigen](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic), die im Kommentarbereich verfügbar ist, ermöglicht es Autoren, jede Prüfungsaufgabe (offen oder geschlossen) auszuwählen, die mit dem aktuell geöffneten Thema verknüpft ist, ohne die Prüfungsprojekte zu wechseln. Wenn diese Option aktiviert **, enthält** Bedienfeld „Kommentare“ im Editor eine Dropdown-Liste für jede Prüfungsaufgabe, zu der das Thema gehört, sowie für jeden Aufgabenstatus und das Projekt, zu dem sie gehört.

Wenn diese Funktion in einer -Instanz aktiviert ist, werden Prüfungsaufgaben standardmäßig indiziert, sobald sie erstellt werden, sodass sie in dieser Dropdown-Liste automatisch verfügbar sind.

Wenn die Funktion jedoch zum Zeitpunkt der Bereitstellung von Experience Manager Guides auf einer Instanz deaktiviert ist, werden Überprüfungsaufgaben, die bei deaktivierter Funktion erstellt wurden, nicht indiziert. Wenn Sie als Administrator die Funktion aktivieren, nachdem solche Prüfungsaufgaben bereits vorhanden sind, werden diese Aufgaben erst dann in der Dropdown-Liste angezeigt, wenn sie indiziert wurden. Um sie verfügbar zu machen, müssen Sie ein einmaliges Skript ausführen, um die vorhandenen Prüfungsaufgaben zu indizieren.

Führen Sie den folgenden cURL-Befehl einmal aus, um vorhandene Prüfungsaufgaben zu indizieren:

```bash
curl --location 'http://<host>:<port>/bin/guides/script/start' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic <base64-encoded-credentials>' \
--header 'Cookie: cq-authoring-mode=TOUCH' \
--data-urlencode 'jobType=review-topic-guids-migration'
```
