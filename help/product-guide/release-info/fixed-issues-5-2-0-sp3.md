---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 5.2.0 Service Pack 3
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.2.0 Service Pack 3 von Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a3144f0078b2073289043befacc5e2358b9c0e02
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%
---
# Es wurden Probleme in Version 5.2.0 Service Pack 3 (November 2026) behoben

Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.2.0 Service Pack 3 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für Version 5.2.0 Service Pack 3](upgrade-instructions-5-2-0-sp3.md).

## Editor 2.0

- Wenn Sie eine Tabelle aus dem Autorenmodus kopieren und in den Autorenmodus einfügen, werden Attribute wie `colwidth` und alle anderen in `colspec` definierten Attribute entfernt, wodurch die Spaltenbreiteneinstellungen verloren gehen. (GUIDES-52916)
- Wenn eine Tabelle aus Microsoft Word eingefügt wird, werden die Kopfzeilenzellen erstellt, ihr Inhalt geht jedoch verloren. (GUIDES-49847)
- Wenn Code mithilfe von Strg+V aus Microsoft Word oder ähnlichen Texteditoren in ein `codeblock`-Element eingefügt wird, gehen Zeilenumbrüche und führende Leerzeichen verloren und der Code wird in eine einzelne Zeile reduziert. (GUIDES-33247)

## Asset-Management

- Die Asset-Status-API gibt nicht den richtigen Status für Assets zurück, deren Pfad ein Komma enthält. (GUIDES-49065)

## Publishing

- Beim Veröffentlichen einer DITA-Zuordnung mit `processing-role=resource-only` in AEM Sites (mit Zuordnung veralteter Komponenten) werden für diese Elemente in zusätzlichen Szenarien, wie z. B. `topicgroup` und bestimmten Inhaltskonfigurationen, verwaiste Sites-Seiten generiert. (GUIDES-37650)
- Die Verzweigungsfilterung erzeugt zusätzliche Seiten für unerwünschte Themen, die als `keydef` verwendet werden (die durch DITA-OT `resource-only ="true"` sind). (GUIDES-19701)
- Wenn Sie im Zuordnungs-Dashboard eine andere Voreinstellung auswählen, wird ein Aufruf zum Abrufen von Peer-Links ausgeführt, was zu einer zusätzlichen Verarbeitung führt. (GUIDES-53703)
- In der nativen PDF-Ausgabe sind Themenverweise, die mit `toc="no"` Attribut gekennzeichnet sind, weiterhin im Inhaltsverzeichnis enthalten, was zu einem langen und überladenen Inhaltsverzeichnis führt. (GUIDES-20156)
- In einigen Fällen, in denen eine vollständige DITA-Zuordnung mithilfe einer dynamischen Basislinie generiert und in AEM Sites veröffentlicht wird, werden bestimmte Themen mit früheren oder nicht genehmigten Versionen anstelle der aktuellen genehmigten Versionen veröffentlicht. (GUIDES-55646)
- Bei der Verarbeitung einer großen Anzahl von Assets tritt `PurgePresetExecutionDataJob` manchmal auf ein nicht verarbeitetes `RuntimeNodeTraversalException`, wodurch der Auftrag in einer Endlosschleife stecken bleibt und übermäßige Protokolle generiert. (GUIDES-53897)
- In der nativen PDF-Ausgabe wird das für ein `topichead`- oder `topicgroup`-Element festgelegte `outputclass`-Attribut nicht auf den resultierenden PDF-Abschnitt angewendet oder übertragen. (GUIDES-22950)
- In einigen Fällen ist bei der Veröffentlichung mit der nativen PDF-Engine v1 die Leserichtung von Inhalten mit Barrierefreiheits-`settingsenabled` falsch. Seitenzahlen in Fußzeilen werden vor dem Hauptinhalt und nicht am Ende gelesen. (GUIDES-27790)


## Übersetzung

- Das Anwenden einer Grundlinie auf eine Zuordnung mit vielen Assets verzögert das Laden des Übersetzungsberichts für die ausgewählte Sprache, was manchmal zu einer Zeitüberschreitung der Anfrage führt, bevor der Bericht gerendert wird. (GUIDES-45508)
- Sprachgruppen in der Registerkarte Übersetzung in den Workspace-Einstellungen werden nicht beibehalten, wenn der ausgewählte Sprachordner einen Code mit Trennzeichen für das Gebietsschema (z. B. `da-DK`) anstelle eines Unterstrichs (`da_dk`) verwendet. (GUIDES-37843)
- Beim Starten einer Übersetzung mit einem XLIFF-Projekt wird ein leeres Projekt erstellt, das nie in den Status „In Bearbeitung“ wechselt. (GUIDES-51759)
- Die `propagateVersionLabel` im globalen Ordnerprofil wird gelegentlich auf `false` zurückgesetzt, wenn ein Benutzer mit nur der Rolle Mitwirkende auf den Editor zugreift. (GUIDES-51870)

## Grundlinie

- Die gespeicherte Baseline-Auswahl einer Voreinstellung wird fälschlicherweise als *Keine Baseline* angezeigt, nachdem die Baseline gelöscht wurde oder während eine dynamische Baseline noch erstellt wird. (GUIDES-52690)
- In einigen Fällen bleiben dynamische Baselines nach einem fehlgeschlagenen Neustart im Verarbeitungsstatus stecken, was dazu führt, dass die Export- und Ausgabegenerierung veraltete Themen- und Zuordnungsversionen verwendet, ohne dass ein Fehler angezeigt wird. (GUIDES-56739)

## Überprüfung

- In Szenarien mit einer großen Anzahl von Prüfungsaufgaben dauert das Öffnen des Prüfungsbereichs oder das Anwenden eines Projektfilters länger als erwartet, um die Aufgabenliste zu laden. (GUIDES-48893)
- Der Inhaltsbereich in der Review-Benutzeroberfläche zeigt auf bestimmten Bildschirmauflösungen, einschließlich der empfohlenen Auflösung von 1600 Pixel, eine horizontale Bildlaufleiste an, sodass Überprüfungskommentare ausgeblendet werden, wenn der Inhalt die Fensterbreite überschreitet. (GUIDES-44082)

## Plattform

- Die API zum Verschieben, die API zum Umbenennen und die Benutzeroberfläche von Assets verhindern das Umbenennen eines DITA-Assets mit einem GUID-basierten Dateinamen in einen von Menschen lesbaren Dateinamen. Assets kann jetzt in für Menschen lesbare Dateinamen umbenannt werden. Das Umbenennen eines GUID-basierten Dateinamens in einen anderen GUID-basierten Dateinamen ist jedoch weiterhin nicht zulässig. (GUIDES-43006, GUIDES-59684)
- Wenn ein Nicht-DITA-Asset, z. B. ein Bild, das von einer Nicht-UUID-Einrichtung zu einer UUID-Einrichtung migriert wurde, zurückgesetzt oder auf eine andere Version verzweigt wird, ändert sich seine UUUID. Vorhandene Verweise auf das Asset werden nicht mehr aufgelöst, und das Bild erscheint in den Themen, die darauf verweisen, beschädigt. (GUIDES-58414)
- Durch die Installation des Experience Manager Guides Service Packs werden zuvor installierte externe Tools wie ACS Commons aus dem Abschnitt AEM **Tools** entfernt. (GUIDES-60365)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 5.2.0 Service Pack 3 erkannt:

- Nach der Installation des Service Packs schlägt die Validierung des Schematrons möglicherweise mit einer `NoClassDefFoundError` Ausnahme fehl, und Sie können keine Themen im Editor speichern. (GUIDES-60062)<br>**Problemumgehung:** Aktualisieren Sie das `com.adobe.fmdita.schematron-wrapper`-Bundle über die AEM Web Console (`/system/console/bundles`).
