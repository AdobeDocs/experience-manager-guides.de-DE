---
title: Erstellen einer Massen-Aktivierungszuordnung
description: Erfahren Sie, wie Sie in AEM Handbüchern eine Massen-Aktivierungszuordnung erstellen.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
feature: Publishing, Bulk Activation
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Erstellen einer Massen-Aktivierungszuordnung {#id214GG0E90EV}

Führen Sie die folgenden Schritte aus, um eine Massen-Aktivierungszuordnung zu erstellen:

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Wählen Sie oben den Adobe Experience Manager-Link und dann **Tools** aus.

1. Wählen Sie die Kachel **Publish-Dashboard-Stapel** aus.

   Zum ersten Mal wird eine leere Sammlungsseite angezeigt. Wenn Sie zuvor Massenaktivierungskollektionen erstellt haben, werden diese auf dieser Seite angezeigt.

1. Klicken Sie auf **Erstellen**.

1. Geben Sie einen Titel für Ihre Massen-Aktivierungszuordnung ein und klicken Sie auf **Erstellen**.

   Bei der Erstellung der Massen-Aktivierungszuordnung wird eine Erfolgsmeldung angezeigt.

1. Klicken Sie in der Erfolgsmeldung auf **Öffnen** .

1. Wählen Sie **Bearbeiten** und dann **Karten hinzufügen** aus.

1. Suchen Sie die DITA-Maps, die Sie zur Massen-Aktivierungszuordnungssammlung hinzufügen möchten, und fügen Sie sie hinzu.

   Standardmäßig werden alle Vorgaben und Gebietsschemata, die mit der Zuordnung verknüpft sind, automatisch hinzugefügt.

1. Wählen Sie die gewünschte Ausgabe aus, indem Sie die gleitende Schaltfläche ein- oder ausschalten.

   Sie können mehrere Ausgabevorgaben für die verschiedenen Gebietsschemata auswählen.

1. Klicken Sie auf **Fertig**.

Die DITA-Zuordnungsdateien werden Ihrer Massen-Aktivierungszuordnungssammlung hinzugefügt.

![ erstellte Massenaktivierungssammlung](images/bulk-activation-collection-created.png){width="800" align="left"}

## Registerkarte &quot;Maps und Vorgaben&quot;

Die Registerkarte **Maps und Vorgaben** enthält Informationen in den folgenden Spalten:

- **Zuordnung**: Zeigt den Titel der DITA-Map-Datei an.
- **Map Path**: Zeigt den vollständigen Pfad der DITA-Map-Datei an.

- **UUID**: Zeigt die eindeutige Kennung an, die mit der Datei verknüpft ist.

- **Sprache**: Zeigt den Sprachcode der DITA-Zuordnung an.
- **Vorgabe**: Zeigt den Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe an. Außerdem wird das Symbol je nach Typ der Ausgabevorgabe angezeigt.

  >[!NOTE]
  >
  > Das kleine ![](images/global-preset-icon.svg) -Symbol zeigt eine Vorgabe auf Ordnerprofilebene an.

- **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wird. Anhand dieser Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Zuordnung aktivieren möchten oder nicht.
- **Generiert**: Zeigt Datum und Uhrzeit der letzten generierten Ausgabe an.
- **Veröffentlicht**: Zeigt das Datum und die Uhrzeit der letzten veröffentlichten (oder aktivierten) Ausgabe an. Wenn Sie den Link auswählen, wird die Seite **Aktivierungsergebnisse** angezeigt, die die Protokolle mit Informationen zum Stammpfad enthält, in dem der Inhalt aktiviert ist.

## Registerkarte &quot;Audit History&quot;

Die Registerkarte **Audit History** enthält Informationen über die aktivierten Zuordnungsausgaben in den folgenden Spalten:
- **Zuordnung**: Zeigt den Titel der DITA-Map-Datei an.
- **Map Path**: Zeigt den vollständigen Pfad der DITA-Map-Datei an.
- **UUID** : Zeigt die eindeutige Kennung an, die mit der Datei verknüpft ist.
- **Sprache**: Zeigt den Sprachcode der DITA-Zuordnung an.
- **Vorgabe**: Zeigt den Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe an. Außerdem wird das Symbol je nach Typ der Ausgabevorgabe angezeigt.
- **Status**: Zeigt den Status der Aktivierung als erfolgreich oder fehlgeschlagen an.
- **Ziel**: Wenn Sie die Ausgabe in Experience Manager Guides as a Cloud Service generieren, können Sie das Ziel der Ausgabe als Publish oder Vorschau anzeigen.

  >[!NOTE]
  >
  > Das kleine ![](images/global-preset-icon.svg) -Symbol zeigt eine Vorgabe auf Ordnerprofilebene an.

- **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wurde. Basierend auf diesen Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Zuordnung aktivieren möchten.
- **Veröffentlicht**: Zeigt das Datum und die Uhrzeit der letzten veröffentlichten (oder aktivierten) Ausgabe an. Wenn Sie den Link auswählen, wird die Seite Aktivierungsergebnisse angezeigt, die die Protokolle mit Informationen zum Stammpfad enthält, in dem der Inhalt aktiviert ist.
  ![ erstellte Registerkarte für den Verlauf der Massenaktivierung-Erfassung ](images/bulk-collection-audit-history.png){width="800" align="left"}

  *Zeigen Sie die Informationen zu den aktivierten Zuordnungsausgaben auf der Registerkarte **Audit History**an.*


  >[!NOTE]
  >
  > Die Ausgaben auf der Registerkarte **Audit History** werden anhand der Spalte **Veröffentlicht** sortiert.



## Linke Leiste

Die folgenden Filteroptionen sind im linken Bereich verfügbar:

- **Geändert**: Sie können &quot;Ja&quot;oder &quot;Nein&quot;auswählen. Wenn Sie &quot;Ja&quot;auswählen, werden nur die modifizierten DITA-Maps angezeigt. Eine geänderte Karte ist eine Karte, die seit der letzten Veröffentlichung erstellt wurde.
- **Vorgabe**: Wählen Sie eine Vorgabe aus, für die Sie die Zuordnungsdateien herausfiltern möchten. Diese Spalte zeigt den Titel der in der Zuordnungsdatei konfigurierten Ausgabevorgabe. Wenn Sie beispielsweise die Vorgabe *AEM Site* auswählen, werden nur die Karten angezeigt, für die die Ausgabevorgabe *AEM Site* konfiguriert ist.
- **Sprache**: Sie können einen der verfügbaren Sprachcodes auswählen und auf der Registerkarte &quot;Karten und Vorgaben&quot;nur die ausgewählte Sprache anzeigen.

Die Filter werden aktualisiert, wenn Sie von der Registerkarte **Maps und Vorgaben** zur Registerkarte **Audit History** wechseln und umgekehrt.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
