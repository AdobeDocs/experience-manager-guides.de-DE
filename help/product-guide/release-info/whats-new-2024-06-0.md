---
title: Versionshinweise | Neue Funktionen in den Adobe Experience Manager-Handbüchern, Version 2024.06.0
description: Lernen Sie die neuen und verbesserten Funktionen in der Version 2024.06.0 der Adobe Experience Manager-Handbücher as a Cloud Service kennen.
source-git-commit: cf60d11f483fdd663bd5decccb63f8ed7d6fff51
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 2%

---

# Neue Funktionen in Version 2024.06.0

Dieser Artikel behandelt die neuen und verbesserten Funktionen der Version 2024.06.0 von Adobe Experience Manager-Handbüchern.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2024.06.0](fixed-issues-2024-06-0.md).

Informationen zu [Upgrade-Anweisungen für die Version 2024.06.0](upgrade-instructions-2024-06-0.md).


## Veröffentlichen eines Themas oder seiner Elemente in einem Experience Fragment

Ein Experience Fragment ist eine modulare Inhaltseinheit in Adobe Experience Manager, die Inhalte und Layouts integriert. Experience Fragments sind hilfreich bei der Erstellung konsistenter und ansprechender Erlebnisse, die über mehrere Kanäle hinweg wiederverwendet werden können.


Mit den Experience Manager-Handbüchern können Sie jetzt ein Thema oder dessen Elemente in einem Experience Fragment veröffentlichen. Sie können eine JSON-basierte Zuordnung zwischen einem Thema und seinen Elementen in einem Experience Fragment erstellen. Sie können beispielsweise Erlebnisfragmente für Kopf- oder Fußzeilen mit Branding-Elementen, Werbebannern, Kundenaussagen und Ereignispromotionen erstellen.




Weitere Informationen finden Sie unter [Experience Fragments veröffentlichen](../user-guide/publish-experience-fragment.md).


## Verbesserungen bei der Veröffentlichung von Inhaltsfragmenten

Experience Manager-Handbücher bieten außerdem einige hilfreiche Verbesserungen in Inhaltsfragmenten:

- Sie können Inhalte einfach mit Bedingungen filtern, während Sie ein Inhaltsfragment veröffentlichen, indem Sie eine DITAVAL-Datei oder bedingte Attribute verwenden.

- Sie können die Inhaltsfragmente eines Themas auch im **Ausgaben** im Abschnitt **Dateieigenschaften**.

![Registerkarte &quot;Dateieigenschaften&quot;](./assets/file-properties-outputs-tab.png){width="300" align="left"}

Weitere Informationen finden Sie unter [Inhaltsfragmente veröffentlichen](../user-guide/publish-content-fragment.md).


## Möglichkeit, Metadaten aus Themendateieigenschaften an die native PDF-Ausgabe zu übergeben

Jetzt können Sie mit Experience Manager Guides die Metadaten aus den Dateieigenschaften eines Themas zu den Seitenlayouts hinzufügen, während Sie die native PDF-Ausgabe generieren. Verwenden Sie diese Funktion, um den Seitenlayouts themenspezifische Metadaten wie Titel, Tags und Beschreibung hinzuzufügen. Sie können auch Ihre veröffentlichte PDF auf Grundlage der Metadaten des Themas anpassen, z. B. das Hinzufügen eines Wasserzeichens zum Hintergrund des Themas basierend auf dem Dokumentstatus des Themas.

![Hinzufügen von nativen Metadaten-PDF](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Fügen Sie den Feldern in Ihren Seitenlayouts Metadaten hinzu.*

Erfahren Sie, wie [Felder und Metadaten hinzufügen](../native-pdf/design-page-layout.md#add-fields-metadata) in einem Seitenlayout.

## Teilinhalt über Elemente hinweg für Vorgänge auswählen

Experience Manager-Handbücher verbessern Ihre Erfahrung bei der Auswahl von Inhalten für alle Elemente im Web Editor. Sie können Inhalte mühelos über verschiedene Elemente hinweg auswählen und Vorgänge wie Fettdruck, Kursiv und Unterstrichen durchführen. Mit dieser Funktion können Sie die Formatierung für teilweise ausgewählten Inhalt nahtlos anwenden oder entfernen. Sie können auch schnell den Inhalt löschen, den Sie über mehrere Elemente hinweg ausgewählt haben. Nach dem Löschen des Inhalts wird der verbleibende Inhalt bei Bedarf automatisch unter einem einzigen gültigen Element zusammengeführt.

Sie können auch Teilinhalte über Elemente hinweg auswählen und den Inhalt dann unter einem gültigen DITA-Element umgeben.
![Dialogfeld &quot;Umgehendes Element&quot;](./assets/surround-element.png) {width="300" align="left"}

*Richten Sie den ausgewählten Inhalt mit einem gültigen Element ein.*

Insgesamt bieten diese Verbesserungen ein besseres Erlebnis und helfen Ihnen, Ihre Effizienz bei der Bearbeitung Ihrer Dokumente zu verbessern.

Weitere Informationen finden Sie unter [Teilauswahl von Inhalten über ein Element hinweg](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).

## Unterstützung für Markdown-Dokumente in nativer PDF-Veröffentlichung

Experience Manager-Handbücher unterstützen auch Markdown-Dokumente bei der nativen PDF-Veröffentlichung. Diese Funktion ist praktisch und hilft Ihnen beim Generieren von PDF für die Markdown-Dateien in Ihrer DITA-Zuordnung. Markdown-Unterstützung bei der nativen PDF-Veröffentlichung erleichtert das einfache Erstellen, Verwalten und Freigeben von Dokumenten.

Weitere Informationen finden Sie unter [Unterstützung für Markdown-Dokumente](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


## Verbesserte Leistung und Skalierbarkeit für große Übersetzungsprojekte

Die Übersetzungsfunktion ist schneller und skalierbarer als je zuvor. Es verfügt über eine neue Architektur, die eine verbesserte Leistung bietet. Die Projekterstellungszeit ist jetzt schneller als früher und die Konflikte während des Prozesses sind fast nicht vorhanden. Diese verbesserte Leistung hilft Ihnen bei schnelleren Übersetzungen und sorgt für einen reibungslosen Betrieb auch bei großen Übersetzungsprojekten.

Diese Verbesserung ist sehr vorteilhaft, da sie die Produktivität und die Gesamterfahrung verbessert.

Erfahren Sie mehr über das [Übersetzen von Dokumenten aus dem Web Editor](../user-guide/translate-documents-web-editor.md).
