---
title: Konfigurieren der Anzahl der LimitReads für eine Abfrage
description: Erfahren Sie, wie Sie die Anzahl der LimitReads für eine Abfrage konfigurieren
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Konfigurieren der Anzahl der LimitReads für eine Abfrage {#id231RC0HL0ID}

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

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
