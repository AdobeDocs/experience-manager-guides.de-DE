---
title: Konfigurieren der Anzahl der LimitReads für eine Abfrage
description: Erfahren Sie, wie Sie die Anzahl der LimitReads für eine Abfrage konfigurieren
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
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

1. Suchen Sie nach und klicken Sie auf **QueryEngineSettings**.

1. Ändern Sie den Attributwert für **LimitReads** -Attribut.

1. Klicken Sie auf **Speichern**.


Wenn Sie diesen Attributwert erhöhen, hilft Ihnen dies beim Generieren des Berichts für größere DITA-Maps.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
