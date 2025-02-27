---
title: Erstellen einer Massenaktivierungs-Zuordnungssammlung
description: In den AEM-Handbüchern erfahren Sie, wie Sie eine Massen-Aktivierungszuordnungssammlung erstellen.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: a242efde-2b29-4d2b-8a50-fd4ae7e8f239
source-git-commit: 4801f0d327b4bd0641aa195d39ec2c4be2a2ce74
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Erstellen einer Massenaktivierungs-Zuordnungssammlung {#id214GG0E90EV}

Um eine Massen-Aktivierungszuordnungssammlung zu erstellen, führen Sie die folgenden Schritte aus:

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und anschließend auf **Tools**.

1. Wählen Sie die **Dashboard für Massenveröffentlichung** aus.

   Zum ersten Mal wird eine leere Sammlungsseite angezeigt. Wenn Sie zuvor Massenaktivierungssammlungen erstellt haben, werden diese auf dieser Seite angezeigt.

1. Klicken Sie auf **Erstellen**.

1. Geben Sie einen Titel für Ihre Massenaktivierungszuordnungssammlung ein und klicken Sie auf **Erstellen**.

   Bei der Erstellung der Massen-Aktivierungszuordnungssammlung wird eine Erfolgsmeldung angezeigt.

1. Klicken **auf** Erfolgsmeldung.

1. Wählen Sie **Bearbeiten** und dann **Karten hinzufügen** aus.

1. Suchen Sie die DITA-Zuordnungen, die Sie der Zuordnungssammlung für die Massenaktivierung hinzufügen möchten, und fügen Sie sie hinzu.

   Standardmäßig werden alle der Zuordnung zugeordneten Vorgaben und Gebietsschemata automatisch hinzugefügt.

1. Wählen Sie den gewünschten Ausgang, indem Sie die Schiebetaste ein- oder ausschalten.

   Sie können mehrere Ausgabevorgaben für alle verfügbaren Gebietsschemata auswählen.

1. Klicken Sie auf **Fertig**.

Die DITA-Zuordnungsdateien werden Ihrer Massen-Aktivierungszuordnungssammlung hinzugefügt.

![ erstellte Massenaktivierungs-Sammlung](images/bulk-activation-collection-created.png){width="800" align="left"}

## Registerkarte „Zuordnungen und Vorgaben“

Die **Zuordnungen und Vorgaben** enthält Informationen in den folgenden Spalten:

- **Map**: Zeigt den Titel der DITA-Zuordnungsdatei an.
- **Map Path**: Zeigt den vollständigen Pfad der DITA-Zuordnungsdatei an.

- **UUID**: Zeigt die eindeutige Kennung an, die mit der Datei verknüpft ist.

- **Language**: Zeigt den Sprach-Code der DITA-Karte an.
- **Voreinstellung**: Zeigt den Titel der Ausgabevorgabe an, die in der Zuordnungsdatei konfiguriert ist. Außerdem wird das Symbol je nach Typ der Ausgabevorgabe angezeigt.

  >[!NOTE]
  >
  > Das kleine ![](images/global-preset-icon.svg) zeigt eine Vorgabe auf Ordnerprofilebene an.

- **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wird. Basierend auf diesen Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Map aktivieren möchten oder nicht.
- **Erstellt**: Zeigt Datum und Uhrzeit der letzten generierten Ausgabe an.
- **Veröffentlicht**: Zeigt Datum und Uhrzeit der letzten veröffentlichten (oder aktivierten) Ausgabe an. Wenn Sie den Link auswählen, wird die **Aktivierungsergebnisse** angezeigt, die die Protokolle mit Informationen zum Stammpfad enthält, in dem der Inhalt aktiviert wird.

## Registerkarte „Audit-Verlauf“

Die **Audit-Verlauf** enthält Informationen zu den aktivierten Zuordnungsausgaben in den folgenden Spalten:
- **Map**: Zeigt den Titel der DITA-Zuordnungsdatei an.
- **Map Path**: Zeigt den vollständigen Pfad der DITA-Zuordnungsdatei an.
- **UUID** : Zeigt die eindeutige Kennung an, die mit der Datei verknüpft ist.
- **Language**: Zeigt den Sprach-Code der DITA-Karte an.
- **Voreinstellung**: Zeigt den Titel der Ausgabevorgabe an, die in der Zuordnungsdatei konfiguriert ist. Außerdem wird das Symbol je nach Typ der Ausgabevorgabe angezeigt.
- **Status**: Zeigt den Status der Aktivierung als erfolgreich oder nicht erfolgreich an.
- **Ziel**: Wenn Sie die Ausgabe in Experience Manager Guides as a Cloud Service generieren, können Sie das Ziel der Ausgabe als Veröffentlichung oder Vorschau anzeigen.

  >[!NOTE]
  >
  > Das kleine ![](images/global-preset-icon.svg) zeigt eine Vorgabe auf Ordnerprofilebene an.

- **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wurde. Basierend auf diesen Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Zuordnung aktivieren möchten.
- **Veröffentlicht**: Zeigt Datum und Uhrzeit der letzten veröffentlichten (oder aktivierten) Ausgabe an. Wenn Sie auf den Link klicken, wird die Seite Aktivierungsergebnisse angezeigt, die die Protokolle mit Informationen zum Stammpfad enthält, in dem der Inhalt aktiviert wird.
  ![ hat die Registerkarte „Audit-Verlauf der Massenaktivierungssammlung“ erstellt](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Informationen zu den aktivierten Zuordnungsausgaben finden Sie auf der Registerkarte **Prüfverlauf**.*


  >[!NOTE]
  >
  > Die Ausgaben in der Registerkarte **Auditverlauf** werden nach der Spalte **Veröffentlicht** sortiert.



## Linkes Bedienfeld

Die folgenden Filteroptionen sind im linken Bedienfeld verfügbar:

- **Geändert**: Sie können „Ja“ oder „Nein“ auswählen. Wenn Sie auf Ja klicken, werden nur die geänderten DITA-Karten angezeigt. Eine geänderte Zuordnung ist eine Zuordnung, die seit ihrer letzten Veröffentlichung generiert wurde.
- **Voreinstellung**: Wählen Sie eine Voreinstellung aus, für die Sie die Zuordnungsdateien herausfiltern möchten. In dieser Spalte wird der Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe angezeigt. Wenn Sie beispielsweise die Vorgabe *AEM-Site* auswählen, werden nur die Zuordnungen angezeigt, für die die Ausgabevorgabe *AEM-Site* konfiguriert ist.
- **Sprache**: Sie können einen beliebigen der verfügbaren Sprach-Codes auswählen und nur die ausgewählte Sprache auf der Registerkarte Zuordnungen und Vorgaben anzeigen.

Die Filter werden aktualisiert, wenn Sie von der Registerkarte **Zuordnungen und Vorgaben** zur Registerkarte **Prüfverlauf** und umgekehrt wechseln.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
