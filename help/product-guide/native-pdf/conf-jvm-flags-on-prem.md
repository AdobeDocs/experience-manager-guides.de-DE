---
title: Native PDF | JVM-Flags für native PDF-Veröffentlichung konfigurieren
description: Konfigurieren von JVM-Flags für native PDF-Veröffentlichung
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 1%

---

# Konfigurieren von JVM-Flags für native PDF-Veröffentlichung für On-Premise

Die native PDF-Veröffentlichung startet einen separaten JVM-Prozess zum Generieren einer PDF. Möglicherweise müssen Sie die Konfigurationen dieser JVM anpassen, um verschiedene Szenarien zu unterstützen. Um beispielsweise größere Arbeitslasten auszuführen, sollten Sie die maximale Heap-Größe erhöhen, die für den erstellten JVM-Prozess verfügbar ist.

Führen Sie die folgenden Schritte aus, um JVM-Flags für die native Veröffentlichung von AEM Guides in PDF zu konfigurieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Aktualisieren Sie die Eigenschaft **Java-Befehlszeilenoptionen für native PDF** (*native.pdf.java.opts*), um alle standardmäßigen JVM-Flags zu übergeben.



1. Klicken Sie auf **Speichern**.
