---
title: Benutzerdefinierte Indizierungsbereitstellung für On-Premise-Einrichtung
description: Erfahren Sie, wie Sie benutzerdefinierte Indexinhalte für die On-Premise-Einrichtung erstellen.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 5b9e4936-f674-41d3-a7b2-3d42a2523693
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 0%
---
# Neuindizierung für die Funktion „Suchen und Ersetzen“ (Source-Ansicht)

Die Neuindizierung ist erforderlich, um die Funktion **Suchen und Ersetzen (Source-Ansicht)** zu aktivieren, mit der Sie den gesamten in der Autorenansicht sichtbaren Inhalt sowie den zugrunde liegenden Source-Inhalt (XML-Struktur, einschließlich Elemente, Tags und Attributwerte) für die gesuchte Zeichenfolge überprüfen können.

## Neuindizierung

Bei On-Premise-Setups ist die Indexdefinition im Paket enthalten. Um die Funktion zu aktivieren, müssen Sie den Inhalt neu indizieren.

Beginnen Sie die Neuindizierung, indem Sie die Eigenschaft `reindex=true (Boolean)` auf dem Knoten festlegen: ` /oak:index/guidesAssetLucene` zuvor erfasste Inhalte neu indiziert werden.

Die Neuindizierung wird fortgesetzt, bis das System diese Eigenschaft automatisch wieder in „false“ ändert. Sie können den Fortschritt des Neuindizierungsvorgangs in den Systemprotokollen überwachen.
