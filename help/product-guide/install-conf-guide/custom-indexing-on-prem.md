---
title: Benutzerdefinierte Indizierungsbereitstellung für On-Premise-Einrichtung
description: Erfahren Sie, wie Sie benutzerdefinierte Indexinhalte für die On-Premise-Einrichtung erstellen.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Neuindizierung für die Funktion „Suchen und Ersetzen“ (Source-Ansicht) für On-Premise

Die Neuindizierung ist erforderlich, um die Funktion **Suchen und Ersetzen (Source-Ansicht)** zu aktivieren, mit der Sie den gesamten in der Autorenansicht sichtbaren Inhalt sowie den zugrunde liegenden Source-Inhalt (XML-Struktur, einschließlich Elemente, Tags und Attributwerte) für die gesuchte Zeichenfolge überprüfen können.

## Neuindizierung

Bei On-Premise-Setups ist die Indexdefinition im Paket enthalten. Um die Funktion zu aktivieren, müssen Sie den Inhalt neu indizieren.

Beginnen Sie die Neuindizierung, indem Sie die Eigenschaft `reindex=true (Boolean)` auf dem Knoten festlegen: ` /oak:index/guidesAssetLucene` zuvor erfasste Inhalte neu indiziert werden.

Die Neuindizierung wird fortgesetzt, bis das System diese Eigenschaft automatisch wieder in „false“ ändert. Sie können den Fortschritt des Neuindizierungsvorgangs in den Systemprotokollen überwachen.
