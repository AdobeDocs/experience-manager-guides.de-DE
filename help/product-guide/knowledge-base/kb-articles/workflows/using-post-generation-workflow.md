---
title: Nachgenerierungs-Workflow
description: Ein Überblick über den Nachgenerierungs-Workflow mit einem Beispiel
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
TQID: https://experienceleague.adobe.com/GmpUvIwR5aDOIQ4RNUXoeOeQB3MrueRuxpvYBwYev4I
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b455a250-64c4-4598-b015-7b6b6dc528b1
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 2%

---

# AEM Guides-Veröffentlichung - Workflow nach der Generierung

AEM Guides bietet Ihnen die Flexibilität, einen Workflow nach der Ausgabe anzugeben. Sie können einige Nachbearbeitungsaufgaben für die Ausgabe ausführen, die mit AEM Guides generiert wird.
Beispielsweise können Sie bestimmte Eigenschaften für die PDF-Ausgabe festlegen oder eine E-Mail an eine Benutzergruppe senden, sobald die Ausgabe generiert wurde.


## Welche Schritte sind bei der Verwendung von Workflows nach der Generierung erforderlich?

### Erstellen eines Workflow-Prozesses

Erstellen Sie einen Java- oder ECMA-basierten Workflow-Prozess, der den Vorgang an der generierten Ausgabe ausführt. Kopieren Sie beispielsweise einige Metadaten aus der Quelle in den generierten Inhalt oder bearbeiten Sie Metadaten der generierten Ausgabe.
- Wir werden ein Beispiel für die Erstellung eines solchen Prozesses mit ECMA-Skript nehmen (Sie können das angehängte Paket lesen)
- Informationen zu Java-basierten Workflow-Prozessen finden Sie im Abschnitt *Anpassen des Workflows nach* Generierung“ [Installations- und Konfigurationshandbuch](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Erstellen Sie ein Workflow-Modell

Erstellen Sie mit dem benutzerdefinierten Workflow-Prozess, den Sie im vorherigen Schritt erstellt haben, ein Workflow-Modell und fügen Sie ihm diesen Prozessschritt hinzu.
- Sie müssen außerdem den obligatorischen Prozessschritt &quot;*Nachgenerierung abschließen* als letzten Schritt des Workflows hinzufügen.

Siehe Beispiel-Workflow-Modell unten:

![Workflow-Modell nach der Generierung](../assets/workflows/pgwf-workflow-model.png)


### Diesen Nachgenerierungs-Workflow auf einer Zuordnung verwenden

Der Nachgenerierungs-Workflow ist eine Eigenschaft, die für jede Ausgabevorgabe innerhalb des AEM Guides-Veröffentlichungsmechanismus konfiguriert werden kann. Zum Beispiel:

![Nachgenerierungs-Workflow für Ausgabevorgabe](../assets/workflows/pgwf-preset-settings.png)


Angenommen, das ausgewählte Modell wurde bereits erstellt.


### Testen

Jetzt können Sie die Veröffentlichung mit dieser Voreinstellung ausführen und die Ausgabe des Prozessschritts überprüfen


## Beispiel

Als Referenz können Sie das folgende Paket verwenden und über Package Manager installieren, um den Beispiel-Workflow nach der Generierung zu testen (*oben in Screenshots beschrieben*)

[Beispiel für ein ECMA-basiertes Workflow-Modell nach der Generierung](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
