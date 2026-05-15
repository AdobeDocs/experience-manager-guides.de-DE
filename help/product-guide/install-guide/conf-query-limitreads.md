---
title: Konfigurieren der Anzahl der LimitReads für eine Abfrage
description: Erfahren Sie, wie Sie die Anzahl der LimitReads für eine Abfrage konfigurieren
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/BwhrVPLcY4zw-pzB2wYGXnzBQHV2eFruoQnHWOE4F88
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 98
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
