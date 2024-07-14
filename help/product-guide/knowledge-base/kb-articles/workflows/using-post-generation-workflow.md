---
title: Post-Generierungsarbeitsablauf
description: Eine Übersicht über den Nachbearbeitungs-Workflow mit einem Beispiel
exl-id: e19fdc0b-0ec6-46ce-81ed-e9490d12c029
feature: Workflow Configuration
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 2%

---

# AEM Guides Publishing - Workflow zur Post-Generierung

AEM Guides bietet Ihnen die Flexibilität, einen Workflow zur Erstellung nach der Ausgabe festzulegen. Sie können einige Nachbearbeitungsaufgaben für die Ausgabe ausführen, die mit AEM Guides generiert wird.
Sie können beispielsweise bestimmte Eigenschaften für die PDF-Ausgabe festlegen oder eine E-Mail an eine Benutzergruppe senden, sobald die Ausgabe generiert wurde.


## Was sind die erforderlichen Schritte zur Nutzung der Workflows zur Post-Generierung?

### Workflow-Prozess erstellen

Erstellen Sie einen Java- oder ECMA-basierten Workflow-Prozess, der den Vorgang für die generierte Ausgabe ausführt. Beispiel: Kopieren einiger Metadaten aus der Quelle in den generierten Inhalt oder Bearbeiten von Metadaten der generierten Ausgabe.
- Wir werden ein Beispiel für die Erstellung eines solchen Prozesses mit ECMA-Skript verwenden (siehe angehängtes Paket).
- Informationen zum Java-basierten Workflow-Prozess finden Sie im Abschnitt &quot;*Arbeitsablauf für die Generierung nach der Ausgabe anpassen*&quot; des [Installations- und Konfigurationshandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_Installation-Configuration-Guide_EN.pdf#page=119)


### Erstellen Sie ein Workflow-Modell

Erstellen Sie mit dem benutzerdefinierten Workflow-Prozess, den Sie im vorherigen Schritt erstellt haben, ein Workflow-Modell und fügen Sie diesen Prozessschritt hinzu.
- Als letzten Schritt des Workflows müssen Sie außerdem einen obligatorischen Prozessschritt &quot;*Post-Generierung abschließen*&quot;hinzufügen.

Siehe Beispiel-Workflow-Modell unten:

![Workflow-Modell für die Post-Generierung](../assets/workflows/pgwf-workflow-model.png)


### Verwenden Sie diesen Nachbearbeitungs-Workflow auf einer Karte

Der Post-Generierungs-Workflow ist eine Eigenschaft, die für jede Ausgabevorgabe im AEM Guides-Veröffentlichungsmechanismus konfiguriert werden kann. Beispiel:

![Post-Generierungs-Workflow für die Ausgabevorgabe](../assets/workflows/pgwf-preset-settings.png)


Vorausgesetzt, das ausgewählte Modell wurde bereits erstellt.


### Testen

Jetzt können Sie die Veröffentlichung mit dieser Vorgabe ausführen und die Ausgabe des Prozessschritts überprüfen


## Beispiel

Als Referenz können Sie das folgende Paket verwenden und es über den Paketmanager installieren, um den Beispielworkflow nach der Generierung zu testen (*wie in den Screenshots oben*)

[Beispiel für ein ECMA-basiertes Workflow-Modell nach der Generierung](../assets/workflows/sample-pgwf-ecma-test-wfmetadata.zip)
