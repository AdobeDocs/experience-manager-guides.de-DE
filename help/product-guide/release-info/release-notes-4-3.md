---
title: Versionshinweise zu | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides Version 4.3.0
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version 4.3.0 von Adobe Experience Manager Guides
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---

# Version 4.3.0 von Adobe Experience Manager Guides (Juli 2023)

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version 4.3.0 von Adobe Experience Manager Guides (später als *AEM Guides* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.3.0 von Adobe Experience Manager Guides](./whats-new-4-3-release.md).

## Upgrade auf Version 4.3.0 von AEM Guides


Sie können Ihre aktuelle Version von AEM Guides einfach auf Version 4.3.0 aktualisieren. Bevor Sie mit dem Upgrade auf Version 4.3.0 von AEM Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:
Sie können Ihre aktuelle Version von AEM Guides auf Version 4.3.0 aktualisieren

- Wenn Sie Version 4.2 oder 4.2.x verwenden, können Sie direkt auf Version 4.3.0 aktualisieren.
- Wenn Sie Version 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.2 oder 4.2.x aktualisieren, bevor Sie auf Version 4.3.0 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.0 aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt Upgrade von AEM Guides im produktspezifischen Installationshandbuch.



>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die AEM Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von AEM Guides Version 4.3.0 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**4.3.0 non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 oder 14

**4.3.0 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 oder 14

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im Handbuch zur Installation und Konfiguration von Adobe Experience Manager Guides.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (non-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.3.0 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.3.0 (non-UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.0 (UUID) | 3.0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Die Themendatei wird nicht im Web-Editor entsperrt, obwohl die Optionen Datei entsperren und Nicht speichern ausgewählt sind. 12558)
- Eine Datei kann nicht im Web-Editor ausgecheckt werden, obwohl die Option NEIN ausgewählt wurde, um die Änderungen vor dem Einchecken zu verwerfen. 12557)
- Die QuickInfos für die Dateisymbole „Sperren und Entsperren“ in der Hauptsymbolleiste im Web-Editor stimmen nicht mit den in der Repository-Ansicht angezeigten Symbolen überein.12555)
- Die Option Auschecken abbrechen und Entsperren wird für eine Datei im Web-Editor angezeigt, die noch nicht in der Kartenansicht ausgecheckt wurde. 12556)
- Die PDF-Assets in den vorhandenen Links „topicref“ können nicht ausgewählt werden. (12477).
- Beim Zusammenführen und Aufteilen in den Tabellen generiert AEM Guides 4.2 zusätzliche Tabellenzellen. 11793)
- In der Repository-Ansicht können die Themen oder Bilder nach Verwendung der Such-/Filterfunktion nicht verschoben werden. 12396)
- Suchergebnisse werden im Bedienfeld Suchen und Ersetzen deaktiviert, nachdem eine durchsuchte Datei geöffnet wurde. 12142)
- Die Zifferntaste „8“ auf der seitlichen Tastatur funktioniert im AEM Guides-Editor nicht. 12106)
- Inline-/Anzeigeattribute werden in der Layout-Ansicht des Web-Editors nicht angezeigt. 12498)
- Die Konfiguration der globalen Profilbenutzeroberfläche stimmt nicht mit der Konfiguration des Ordnerprofils überein. 11970)
- Inhaltsreferenzen sind fehlerhaft, wenn DITA-Dateien kopiert und eingefügt werden. 11959)
- Inhaltsfragment kann nicht in der Spaltenansicht bearbeitet werden, wenn AEM Guides installiert ist. (7342)
- Der Inhalt geht verloren, wenn sich eine entpackte XRef unter einem Unterelement-Tag befindet. 12532)
- Der Genehmigungs-Workflow funktioniert nicht, wenn der Dokumentstatus in den Dateieigenschaften des rechten Bedienfelds in den „Endstatus“ geändert wird. 11026)
- Asset-Benutzeroberfläche | In der Listenansicht können die überlagerten verfügbaren Spalten nicht zusammengeführt werden. 11528)
- Keyref wird in der Zuordnungsansicht nicht aufgelöst. 11490)
- Beim Navigieren durch den XML-Editor wird das obere Menü nicht angezeigt. 10868)
- `conref` in pH-Tag | Das angezeigte Dialogfeld zum Durchsuchen ist falsch. (9481)
- Lokale Links zu anderen Elementen werden im Web-Editor nicht aufgelöst. (8790)
- Die Funktion Matches() funktioniert nicht in der Schematron-Funktion. 11224)



### Verwaltung

- Das Feld „Titel“ in den Metadateneigenschaften der DITA-Zuordnung wird durch `<title>` -Element für die Zuordnung überschrieben. 10702)
- Beim Versuch, die Version der Themen in der Baseline zu öffnen oder zu aktualisieren, wird der Lader „Informationen vom Server abrufen“ unbegrenzt ausgeführt.12478)


### Überprüfung

- Neue UI-Überprüfung | Die Bedingungen heben Arbeit in den Bereichen „Hervorheben“, „Anzeigen“ und „Ausblenden“ anders hervor als in der Funktionsweise im Web-Editor. 11628)

### Publishing

- Die Veröffentlichung schlägt beim Umbenennen einer nativen PDF-Vorgabe fehl. 12564)
- Das Duplizieren einer nativen PDF-Vorlage wird am Standardvorlagenspeicherort anstelle des bereitgestellten benutzerdefinierten Vorlagenspeicherorts dupliziert. 12563)
- Native PDF | Die Sprach-Metadaten können im generierten PDF nicht auf WCAG 2.0 eingestellt werden. 12407)
- Das Veröffentlichen auf der AEM-Site schlägt fehl, wenn temporäre Dateien vom Pod gelesen werden, die möglicherweise aktualisiert oder neu gestartet wurden. 12113)
- Native PDF | Benutzerdefinierte Attribute werden nicht an die temporäre HTML- oder PDF-Engine weitergegeben. (DXML-12005)
- Native PDF |  Java OutOfMemoryError tritt beim Veröffentlichen großer Inhalte auf. 11789)
- Native PDF | Xref druckt den Inhalt des href-Thementitels anstelle der Xref-Beschriftung. 11322)
- Native PDF | Die PDF-Vorlageneinstellungen können nicht gespeichert werden. 10751)
- Native PDF | Der Text überschreitet die Spaltenbreite, wenn mehrere XRefs eingeschlossen werden. 10876)
- Native PDF | `<note>``</note>` Element erzeugt keinen zusätzlichen span-Titel seines Typs. 10549)
- JSON-Ausgabe | Die `fmUuid` Eigenschaft im jcr:content-Knoten von JSON unterscheidet sich von der „id“ in JSON. 11564)
- JSON-Ausgabe | Wenn Zuordnung und Thema mit demselben Dateinamen vorhanden sind, wird JSON für die Zuordnung entfernt. 11524)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem in AEM Guides Version 4.3.0 festgestellt:

- Das in der Basisvorlage definierte allgemeine Seitenlayout wird nicht als Standardvorlage angewendet.

  Problemumgehung:
Fügen Sie ein gemeinsames Seitenlayout als Vorder- und Rückseite hinzu, dann wird es für jede Seite angezeigt.
- Problem bei der Site-Suche bei der Suche auf der AEM-Site-Ausgabeseite in AEM Service Pack 16 oder 17.

  Problemumgehung:

   1. Öffnen Sie die Datei mit dem Pfad `/libs/foundation/components/search/search.jsp` in `crx/de`
   1. Ersetzen Sie die Zeilennummer 234 durch folgenden Code:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Speichern Sie die Datei.
