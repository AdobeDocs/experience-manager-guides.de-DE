---
title: Erstellen einer Massen-Aktivierungszuordnung
description: Erfahren Sie, wie Sie in AEM Handbüchern eine Massen-Aktivierungszuordnung erstellen.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: 1be8cddcbf58696a53bfccf887a04e5807f2198e
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Erstellen einer Massen-Aktivierungszuordnung {#id214GG0E90EV}

Führen Sie die folgenden Schritte aus, um eine Massen-Aktivierungszuordnung zu erstellen:

1. Auswählen **Handbücher** aus der Liste der Tools.

1. Wählen Sie oben den Link Adobe Experience Manager aus und wählen Sie **Instrumente**.

1. Wählen Sie die **Massen-Veröffentlichungs-Dashboard** Kachel.

   Zum ersten Mal wird eine leere Sammlungsseite angezeigt. Wenn Sie zuvor Massenaktivierungskollektionen erstellt haben, werden diese auf dieser Seite angezeigt.

1. Klicken Sie auf **Erstellen**.

1. Geben Sie einen Titel für Ihre Massen-Aktivierungszuordnung ein und klicken Sie auf **Erstellen**.

   Bei der Erstellung der Massen-Aktivierungszuordnung wird eine Erfolgsmeldung angezeigt.

1. Klicks **Öffnen** auf der Erfolgsmeldung angezeigt.

1. Auswählen **Bearbeiten** und wählen Sie **Zuordnen hinzufügen**.

1. Suchen Sie die DITA-Maps, die Sie zur Massen-Aktivierungszuordnungssammlung hinzufügen möchten, und fügen Sie sie hinzu.

   Standardmäßig werden alle Vorgaben und Gebietsschemata, die mit der Zuordnung verknüpft sind, automatisch hinzugefügt.

1. Wählen Sie die gewünschte Ausgabe aus, indem Sie die gleitende Schaltfläche ein- oder ausschalten.

   Sie können mehrere Ausgabevorgaben für die verschiedenen Gebietsschemata auswählen.

1. Klicken Sie auf **Fertig**.

Die DITA-Zuordnungsdateien werden Ihrer Massen-Aktivierungszuordnungssammlung hinzugefügt.

![ Erstellte Massenaktivierungskollektion](images/bulk-activation-collection-created.png){width="800" align="left"}

## Registerkarte &quot;Maps und Vorgaben&quot;

Die **Maps und Vorgaben** -Tab enthält Informationen in den folgenden Spalten:

- **Zuordnung**: Zeigt den Titel der DITA-Map-Datei an.
- **Zuordnungspfad**: Zeigt den vollständigen Pfad der DITA-Map-Datei an.

- **UUID**: Zeigt die eindeutige Kennung an, die mit der Datei verknüpft ist.

- **Sprache**: Zeigt den Sprachcode der DITA-Zuordnung an.
- **Voreinstellung**: Zeigt den Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe an. Außerdem wird das Symbol je nach Typ der Ausgabevorgabe angezeigt.

  >[!NOTE]
  >
  > Der kleine ![](images/global-preset-icon.svg) -Symbol zeigt eine Vorgabe auf Ordnerprofilebene an.

- **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wird. Anhand dieser Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Zuordnung aktivieren möchten oder nicht.
- **Generiert**: Zeigt Datum und Uhrzeit der letzten generierten Ausgabe an.
- **Veröffentlicht**: Zeigt das Datum und die Uhrzeit der letzten veröffentlichten (oder aktivierten) Ausgabe an. Wenn Sie den Link auswählen, wird die **Aktivierungsergebnisse** angezeigt, die die Protokolle mit Informationen zum Stammpfad enthält, in dem der Inhalt aktiviert ist.

## Registerkarte &quot;Audit History&quot;

Die **Prüfverlauf** -Tab enthält Informationen zu den aktivierten Zuordnungsausgaben in den folgenden Spalten:
- **Zuordnung**: Zeigt den Titel der DITA-Map-Datei an.
- **Zuordnungspfad**: Zeigt den vollständigen Pfad der DITA-Map-Datei an.
- **UUID** : Zeigt die eindeutige Kennung an, die mit der Datei verknüpft ist.
- **Sprache**: Zeigt den Sprachcode der DITA-Zuordnung an.
- **Voreinstellung**: Zeigt den Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe an. Außerdem wird das Symbol je nach Typ der Ausgabevorgabe angezeigt.
- **Status**: Zeigt den Status der Aktivierung als erfolgreich oder fehlgeschlagen an.
- **Ziel**: Wenn Sie die Ausgabe as a Cloud Service in den Experience Manager-Handbüchern generieren, können Sie das Ziel der Ausgabe als Veröffentlichen oder Vorschau anzeigen.

  >[!NOTE]
  >
  > Der kleine ![](images/global-preset-icon.svg) -Symbol zeigt eine Vorgabe auf Ordnerprofilebene an.

- **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wurde. Basierend auf diesen Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Zuordnung aktivieren möchten.
- **Veröffentlicht**: Zeigt das Datum und die Uhrzeit der letzten veröffentlichten (oder aktivierten) Ausgabe an. Wenn Sie den Link auswählen, wird die Seite Aktivierungsergebnisse angezeigt, die die Protokolle mit Informationen zum Stammpfad enthält, in dem der Inhalt aktiviert ist.
  ![ Registerkarte für den Verlauf der Massenaktivierung](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Anzeigen der Informationen zu den aktivierten Zuordnungsausgaben im **Prüfverlauf**Registerkarte.*


  >[!NOTE]
  >
  > Die Ausgaben in der **Prüfverlauf** -Tab nach **Veröffentlicht** Spalte.



## Linke Leiste

Die folgenden Filteroptionen sind im linken Bereich verfügbar:

- **Geändert**: Sie können &quot;Ja&quot;oder &quot;Nein&quot;auswählen. Wenn Sie &quot;Ja&quot;auswählen, werden nur die modifizierten DITA-Maps angezeigt. Eine geänderte Karte ist eine Karte, die seit der letzten Veröffentlichung erstellt wurde.
- **Voreinstellung**: Wählen Sie eine Vorgabe aus, nach der Sie die Zuordnungsdateien herausfiltern möchten. Diese Spalte zeigt den Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe. Wenn Sie beispielsweise *AEM Site* voreingestellt ist, werden nur die Karten angezeigt, die die *AEM Site* Ausgabevorgabe, die für sie konfiguriert ist.
- **Sprache**: Sie können einen der verfügbaren Sprachcodes auswählen und auf der Registerkarte &quot;Karten und Vorgaben&quot;nur die ausgewählte Sprache anzeigen.

Die Filter werden aktualisiert, wenn Sie von der **Maps und Vorgaben** zum **Prüfverlauf** und umgekehrt.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
