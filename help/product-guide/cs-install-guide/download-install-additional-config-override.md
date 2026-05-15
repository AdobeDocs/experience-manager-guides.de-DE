---
title: Überschreibungen der Konfiguration
description: Erfahren Sie, wie Sie Konfigurations-Überschreibungen vornehmen
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/0ym-EC9f3TgvvZtlGhaeIm70-AycRYd7ZHS4-ZPbxCg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: baa3aa24-d162-4a57-b73a-d27341145083
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 303
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

   ![](assets/enable-penultimate-ui.png){width="800"}

   Wenn Sie den Wert auf **true** setzen, wird die alte Benutzeroberfläche beibehalten, während **false** die neue Benutzeroberfläche aktiviert.



**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)
