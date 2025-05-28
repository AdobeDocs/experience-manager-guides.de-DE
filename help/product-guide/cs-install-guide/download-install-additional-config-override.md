---
title: Überschreibungen der Konfiguration
description: Erfahren Sie, wie Sie Konfigurations-Überschreibungen vornehmen
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: e4b213b5f0efda18fb24f100f3ee8237947890bf
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Überschreibungen der Konfiguration {#id216IFC003XA}

Für Konfigurationsaktualisierungen sollte der folgende allgemeine Ansatz verwendet werden:

1. Greifen Sie auf das Git-Repository Ihrer Cloud Manager zu.

1. Erstellen Sie eine neue JSON-Datei am folgenden Speicherort:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Benennen Sie die Datei im folgenden Format:

   $\{PID\}.cfg.json

   Hier ist die PID die Prozess-ID der Konfiguration.

1. Fügen Sie Eigenschaften in der JSON-Datei im folgenden Format hinzu:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Übertragen Sie die Änderungen und führen Sie die Cloud Manager-Pipeline aus, um die aktualisierte Konfiguration bereitzustellen.

## Konfigurieren der Experience Manager Guides-Benutzeroberfläche

Die Version 2025.02.0 von Adobe Experience Manager Guides bietet eine überarbeitete Benutzeroberfläche und erweiterte Funktionen, mit denen Sie schneller und effizienter als je zuvor arbeiten können. Dazu gehören eine völlig neue Startseite, eine übersichtlichere Editor-Symbolleiste, eine spezielle Kartenkonsole und erweiterte Funktionen.

Um einen reibungslosen Übergang sicherzustellen und Unterbrechungen zu minimieren, bietet Experience Manager Guides eine Konfigurationsoption, mit der Sie bei Bedarf zurück zur alten Benutzeroberfläche wechseln können (und umgekehrt).

>[!IMPORTANT]
>
> Diese Konfigurationsoption zum Wechseln zwischen der neuen und der alten Benutzeroberfläche wurde bis zur Version 2025.4.0 unterstützt. Mit der Version 2025.6.0 ist diese Einstellung veraltet und kann nicht mehr für die Wiederherstellung zur alten Benutzeroberfläche verwendet werden.

Führen Sie die folgenden Schritte aus, um die Benutzeroberfläche von Experience Manager Guides zu konfigurieren:

1. Öffnen Sie Adobe Experience Manager und wählen Sie dann Ihr Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
2. Wechseln Sie zur Registerkarte **Umgebungen**.
3. Wählen Sie den Namen der Umgebung aus, die Sie konfigurieren möchten. Dadurch sollten Sie zur Seite **Umgebungsinformationen** gelangen.
4. Wechseln Sie zur Registerkarte **Konfiguration** .
5. Wählen Sie **Hinzufügen/Aktualisieren** aus.
6. Fügen Sie die Konfigurationsdetails der Benutzeroberfläche hinzu. Stellen Sie sicher, dass Sie denselben Namen und dieselbe Konfiguration wie im folgenden Screenshot verwenden.

   ![](assets/enable-penultimate-ui.png){width="800" align="left"}

   Wenn Sie den Wert auf **true** setzen, wird die alte Benutzeroberfläche beibehalten, während **false** die neue Benutzeroberfläche aktiviert.



**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)
