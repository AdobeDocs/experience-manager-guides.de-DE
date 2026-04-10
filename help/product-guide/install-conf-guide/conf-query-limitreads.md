---
title: Konfigurieren der Anzahl der LimitReads für eine Abfrage
description: Erfahren Sie, wie Sie die Anzahl der LimitReads für eine Abfrage konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Konfigurieren der Anzahl der LimitReads für eine On-Premise-Abfrage

Um die Anzahl der Knoten zu erhöhen, die eine Abfrage gleichzeitig lesen kann, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die JMX-Seite der Adobe Experience Manager-Web-Konsole.

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Suchen Sie nach „QueryEngineSettings **und klicken Sie darauf**.

1. Ändern Sie den Attributwert für das Attribut **LimitReads**.

1. Klicken Sie auf **Speichern**.


Wenn Sie diesen Attributwert erhöhen, können Sie damit den Bericht für größere DITA-Zuordnungen erstellen.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
