---
title: Native PDF | Konfigurieren von JVM-Flags für die native PDF-Veröffentlichung
description: Konfigurieren von JVM-Flags für die native PDF-Veröffentlichung
exl-id: d5432913-4b5a-48e7-9467-7f6c6e0adbe4
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Konfigurieren von JVM-Flags für die native PDF-Veröffentlichung

Die native PDF-Veröffentlichung startet einen separaten JVM-Prozess zum Generieren einer PDF. Möglicherweise müssen Sie die Konfigurationen dieser JVM anpassen, um verschiedene Szenarien zu unterstützen. Um beispielsweise größere Arbeitslasten auszuführen, sollten Sie die maximale Heap-Größe erhöhen, die für den erstellten JVM-Prozess verfügbar ist.

Führen Sie die folgenden Schritte aus, um JVM-Flags für das native PDF-Publishing in AEM Guides zu konfigurieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Aktualisieren Sie die Eigenschaft **Java-Befehlszeilenoptionen für native PDF** (*native.pdf.java.opts*), um alle standardmäßigen JVM-Flags zu übergeben.



1. Klicken Sie auf **Speichern**.
