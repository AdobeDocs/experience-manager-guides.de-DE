---
title: Konfigurieren der Anzahl der LimitReads für eine Abfrage
description: Erfahren Sie, wie Sie die Anzahl der LimitReads für eine Abfrage konfigurieren
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 2%

---

# Konfigurieren der Anzahl der LimitReads für eine Abfrage {#id231RC0HL0ID}

Führen Sie die folgenden Schritte aus, um die Anzahl der Knoten zu erhöhen, die eine Abfrage gleichzeitig lesen kann:

1. Öffnen Sie die JMX-Seite der Adobe Experience Manager Web Console.

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Suchen Sie nach **QueryEngineSettings** und klicken Sie darauf.

1. Ändern Sie den Attributwert für das Attribut **LimitReads** .

1. Klicken Sie auf **Speichern**.


Wenn Sie diesen Attributwert erhöhen, hilft Ihnen dies beim Generieren des Berichts für größere DITA-Maps.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
