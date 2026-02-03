---
title: Benutzerdefinierte Indizierungsbereitstellung für On-Premise-Einrichtung
description: Erfahren Sie, wie Sie benutzerdefinierte Indexinhalte für die On-Premise-Einrichtung erstellen.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Neuindizierung für die Funktion „Suchen und Ersetzen“ (Source-Ansicht)

Die Neuindizierung ist erforderlich, um die Funktion **Suchen und Ersetzen (Source-Ansicht)** zu aktivieren, mit der Sie den gesamten in der Autorenansicht sichtbaren Inhalt sowie den zugrunde liegenden Source-Inhalt (XML-Struktur, einschließlich Elemente, Tags und Attributwerte) für die gesuchte Zeichenfolge überprüfen können.

## Neuindizierung

Bei On-Premise-Setups ist die Indexdefinition im Paket enthalten. Um die Funktion zu aktivieren, müssen Sie den Inhalt neu indizieren.

Beginnen Sie die Neuindizierung, indem Sie die Eigenschaft `reindex=true (Boolean)` auf dem Knoten festlegen: ` /oak:index/guidesAssetLucene` zuvor erfasste Inhalte neu indiziert werden.

Die Neuindizierung wird fortgesetzt, bis das System diese Eigenschaft automatisch wieder in „false“ ändert. Sie können den Fortschritt des Neuindizierungsvorgangs in den Systemprotokollen überwachen.