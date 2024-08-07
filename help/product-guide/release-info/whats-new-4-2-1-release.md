---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 4.2.1
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in Version 4.2.1 von Adobe Experience Manager Guides.
exl-id: 441aa7ec-d88c-42cb-83f0-d0f6e58bfa41
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Neue Funktionen in Version 4.2.1 von Adobe Experience Manager Guides (Mai 2023)

Dieser Artikel behandelt die neuen und verbesserten Funktionen in Version 4.2.1 von Adobe Experience Manager Guides (später als *AEM Guides* bezeichnet).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie im Artikel [Versionshinweise](release-notes-4-2-1.md) .

## Navigieren Sie vom Web Editor zur AEM Homepage

Jetzt können Sie einfach vom Web-Editor zur AEM Navigationsseite navigieren.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Klicken Sie auf das Symbol **Guides** (![](assets/aem-guides-icon.png) ), um zur AEM Navigationsseite zurückzukehren.


Weitere Informationen finden Sie unter [AEM Navigationsseite](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Erweiterte Metadatenunterstützung beim PDF-Publishing

AEM Guides bietet jetzt erweiterte Unterstützung für die Metadaten, die den Metadaten in Ihrer PDF-Ausgabe zugeordnet sind. Die Metadatenoptionen enthalten Informationen über das Dokument und seinen Inhalt, wie z. B. den Namen des Autors, den Dokumenttitel, Schlüsselwörter, Copyright-Informationen und andere Datenfelder.

<img src="assets/pdf-metadata.png" alt=" native PDF-Metadaten">

Sie können eine XMP-Datei importieren und AEM Guides kann die Informationen aus der Datei auswählen. Sie können die Metadatennamen und -werte auch über das Dropdown-Menü angeben. Sie können auch benutzerdefinierte Metadaten hinzufügen, indem Sie direkt in das Namensfeld eingeben.

Weitere Informationen finden Sie unter Beschreibung der Funktion **Metadaten** in [Erstellen einer PDF-Ausgabevorgabe](../web-editor/native-pdf-web-editor.md).

### Verbessertes Bedienfeld für die Gliederungsansicht

AEM Guides bietet ein verbessertes Bedienfeld für die Gliederungsansicht, in dem Sie die hierarchische Ansicht der im Dokument verwendeten Elemente erhalten.

<img src="assets/select-element-content-outline-view_cs.png" alt=" native PDF-Metadaten">

Die Gliederung bietet die folgenden Verbesserungen:

* Das Dropdown-Menü &quot;Anzeigeoptionen&quot;wird über dem Bedienfeld &quot;Konturansicht&quot;angezeigt. Wenn ein Element über eine ID, ein Attribut und Text verfügt, können Sie diese aus der Dropdown-Liste auswählen, um sie zusammen mit dem Element anzuzeigen. Die Attribute, die im Bedienfeld &quot;Umrissansicht&quot;angezeigt werden können, werden durch die Einstellungen für die Anzeigenattribute bestimmt, die von Ihrem Administrator in den **Editor-Einstellungen** konfiguriert wurden.

* Mithilfe der Suchfunktion können Sie nach einem Element anhand seines Namens, seiner ID, seines Textes oder seines Attributwerts suchen.

Weitere Informationen finden Sie in der Beschreibung der Funktion für die Gliederungsansicht im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Multimedia-Bericht aus dem Web-Editor generieren

AEM Guides bietet die Funktion zum Generieren der Berichte für Ihre technischen Dokumente.  Sie können diese Funktion verwenden, um die Themenliste anzuzeigen und die Metadaten Ihrer Dokumente zu verwalten. Jetzt können Sie auch die in allen Verweisen für die aktuelle Zuordnung verwendeten Multimedia-Dateien auf der Registerkarte **Berichte** im Web Editor sehen.

Sie können einen Multimedia-Bericht erstellen, der detaillierte Informationen über die in Ihren Referenzen verwendeten Multimedia-Dateien enthält. Sie haben die Flexibilität, die im Bericht aufgelisteten Multimedia-Dateien zu filtern und zu sortieren.
Sie können auch die CSV-Datei generieren, um die aktuelle Momentaufnahme der in der DITA-Map verwendeten Multimedia-Dateien herunterzuladen.

<img src="assets/web-editor-reports-multimedia.png" alt="Multimedia-Bericht" width="600">

Weitere Informationen finden Sie unter Funktionsbeschreibung für Multimedia-Bericht erstellen im Abschnitt [DITA-Zuordnung-Bericht vom Web-Editor](../user-guide/reports-web-editor.md) .

## Native PDF | Ändern Sie die Leiste, um geänderte Themen im Inhaltsverzeichnis anzugeben.

Mit AEM Guides können Sie jetzt die geänderten Themen im Inhaltsverzeichnis der PDF-Ausgabe schnell identifizieren.  Er zeigt eine Änderungsleiste links von den geänderten Themen im Inhaltsverzeichnis an. Sie können auf das Thema im Inhaltsverzeichnis klicken und die detaillierten Änderungen anzeigen.

<img src="assets/change-marker-toc.png" alt="Markierung im Inhaltsverzeichnis ändern " width="500">

Weitere Informationen finden Sie unter [Arbeiten mit benutzerdefinierten Änderungsbalkenstilen](../native-pdf/change-bar-style.md).



## Native PDF | Formatieren Sie die Seitenmarkierung in der Fußnoten-Komponente.

Jetzt können Sie die Seitenmarkierung in den Fußnoten gestalten. Sie können beispielsweise Klammern hinzufügen oder ihre Farbe ändern. Diese Stile helfen Benutzern, die Seitenmarkierungen im Dokument einfach zu identifizieren.

Weitere Informationen finden Sie unter [Verwenden benutzerdefinierter Stile in Fußnoten](../native-pdf/footnote-number-style.md).

## Öffnen und Abspielen von Video- oder Audiodateien im Web Editor

AEM Guides bietet jetzt die Funktion zum Öffnen und Abspielen der Audio- oder Videodateien im Web-Editor. Sie können die Lautstärke oder die Ansicht des Videos ändern. Im Kontextmenü haben Sie auch die Optionen zum **Herunterladen**, zum Ändern der **Rückspielgeschwindigkeit** oder zum Anzeigen des **Bild-im-Bild-Modus**.

<img src="assets/video-web-editor.png" alt="Abspielvideo" width="600">

Weitere Informationen finden Sie in der Beschreibung der Funktion &quot;Repository-Ansicht&quot;im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .
