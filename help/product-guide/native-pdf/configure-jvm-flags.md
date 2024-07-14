---
title: Native PDF | JVM-Flags für native PDF-Veröffentlichung konfigurieren
description: JVM-Flags für native PDF-Veröffentlichung konfigurieren
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# JVM-Flags für native PDF-Veröffentlichung konfigurieren

Die native PDF-Veröffentlichung startet einen separaten JVM-Prozess zum Generieren einer PDF. Möglicherweise müssen Sie die Konfigurationen dieser JVM anpassen, um verschiedene Szenarien zu unterstützen. Um beispielsweise größere Workloads auszuführen, sollten Sie die maximale Heap-Größe erhöhen, die für den erzeugten JVM-Prozess verfügbar ist.

Führen Sie die folgenden Schritte aus, um die AEM Guides Native PDF Publishing JVM-Flags zu konfigurieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Aktualisieren Sie die Eigenschaft **Java-Befehlszeilenoptionen für natives PDF** (*native.pdf.java.opts*), um alle standardmäßigen JVM-Flags zu übergeben.



1. Klicken Sie auf **Speichern**.
