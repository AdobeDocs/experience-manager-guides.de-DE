---
title: Wiederverwendung von DITA-Inhalten in AEM Guides
description: In diesem kurzen Artikel erfahren Sie, wie Sie mit AEM Guides und DITA Zeit und Mühe sparen, wenn Sie die Wiederverwendbarkeit von Inhalten verwenden
role: User, Admin
author: Pulkit Nagpal(punagpal)
exl-id: 1522ebf5-2aea-4d8f-ade7-367227b31dd9
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Wiederverwendbarkeit von Inhalten in AEM Guides

Adobe AEM Guides nutzt die Stärken von DITA, um eine benutzerfreundliche Oberfläche für die Wiederverwendung von Inhalten bereitzustellen.

In diesem Artikel wird Folgendes besprochen:

1. [Wiederverwendbarkeit mithilfe der Themenreferenz (](#reusability-using-topic-referencestopicref)
2. [Wiederverwendbarkeit mithilfe der Inhaltsreferenz (](#reusability-using-content-reference-conref--conkeyref)
3. [Bonustipp zur Wiederverwendung von Inhalten mit Drag &amp; Drop in AEM Guides](#reuse-content-with-a-single-click-in-aem-guides)

## Wiederverwendbarkeit mit Themenverweisen (topicref)



Nehmen wir an, Sie sind ein Hersteller und haben allgemeine Themen für Sicherheitsvorkehrungen oder Fehlerbehebungstechniken.

Diese können in spezifischen Benutzerhandbüchern für jedes Maschinenmodell referenziert und angepasst werden, wodurch Redundanz reduziert und sichergestellt wird, dass die grundlegenden Sicherheitsinformationen konsistent bleiben.

```
<map id="user_manual_model 100" title="ABC Model 100 User Manual ">


<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
</map>
```


Ähnlich für Modell 200

```
<map id="user_manual_model 200" title="ABC Model 200 User Manual ">

<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
  
</map>
```

## Wiederverwendbarkeit mithilfe der Inhaltsreferenz (conref &amp; conkeyref)

Mit dem Attribut content reference (conref) können Sie Links zu anderen Teilen Ihres Inhalts erstellen. Dies fördert die Wiederverwendbarkeit und reduziert die Redundanz.

Zum Beispiel:

Nehmen wir einmal an, Sie sind ein Finanzunternehmen und haben ein allgemeines Thema für KYC, das KYC-Verfahren für Einzelpersonen, Unternehmen usw. enthält.

Sie möchten ein einzelnes KYC-Fragment für Ihre Themen &quot;Konto speichern&quot;und &quot;Konto abrufen&quot;wiederverwenden.

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>
```

Hier ist `conref=kyc_procedures.dita#indvidual_kyc` kyc_operations.dita die Dateikennung und #individuelle_kyc die Fragmentkennung.

Kyc_procedure.dita ist weiterhin die einzige Informationsquelle. Wenn regulatorische Änderungen Aktualisierungen des KYC-Prozesses erfordern, aktualisieren Sie den Themenpfad mit dem neuen. Die Änderungen werden automatisch in allen Themen übernommen, die darauf verweisen.

Mit AEM Guides werden die beiden Klicks

Schritt 1: Klicken Sie auf Wiederverwendbaren Inhalt einfügen
![toolbar](../../assets/publishing/content-reusability_image1.png)

<br>

Schritt 2: Wählen Sie die Datei und das Fragment aus, die wiederverwendet werden sollen.
![conref](../../assets/publishing/content-reusability_image2.png)

Ähnlich wie &quot;conref&quot;können Sie auch &quot;conkeyref&quot;verwenden, wobei Sie, anstatt einen Inhaltspfad anzugeben, auf Inhalte über Schlüssel verweisen.

Codebeispiel :

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>
```

Die Schlüsseldefinition sieht wie folgt aus:

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Schlüssel - &#39;Kyc_procedure&#39; ist weiterhin die einzige Informationsquelle. Wenn es Änderungen am KYC-Prozess gibt, wie es von Verordnungen gefordert wird, müssen Sie einfach einen Themenpfad mit einem neuen Themenpfad aktualisieren. Diese Änderungen werden automatisch in allen Themen übernommen, die darauf verweisen.

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Hier wird der Themenpfad aufgrund aktueller Änderungen der Verordnung von &quot;kyc_procedure_2020.dita&quot;zu &quot;kyc_procedure_2024.dita&quot;geändert.

Mit AEM Guides werden die beiden Klicks

Schritt 1: Klicken Sie auf Wiederverwendbaren Inhalt einfügen
![toolbar](../../assets/publishing/content-reusability_image1.png)

Schritt 2: Wählen Sie die Stammzuordnung (optional), den Schlüssel und das Fragment aus, die wiederverwendet werden sollen.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

Hier wurde die Stammzuordnung automatisch ausgewählt, da sie bereits in der Kartenansicht geöffnet war.


## Wiederverwenden von Inhalten mit nur einem Klick in AEM Guides

AEM Guides bietet die Funktion &quot;Wiederverwendbare Inhalte&quot;, mit der Inhaltsverweise durch einen Klick hinzugefügt werden können.

Schritt 1: Hinzufügen eines allgemeinen Themas zu wiederverwendbaren Inhalten

![Wiederverwendbaren Inhalt hinzufügen](../../assets/publishing/content-reusability_image4.png)

Schritt 2: Ziehen Sie das Fragment, das Sie in einem Ihrer Zielthemen wiederverwenden möchten, nach dem Hinzufügen per Drag-and-Drop.

![Hinzufügen wiederverwendbarer Inhaltsgif](../../assets/publishing/content-reusability_image5.gif)



## Häufig gestellte Fragen

- ### Nach Auswahl der Datei/des Schlüssels im Dialogfeld Inhalt wiederverwenden werden nicht alle Inhalte angezeigt

Zuweisen von IDs zu Fragmenten (DITA-Elementen), die Sie in anderen Themen wiederverwenden möchten

- ## Schlüssel werden im Dialogfeld &quot;Inhalt wiederverwenden&quot;nicht angezeigt

  Stellen Sie sicher, dass Sie die Stammzuordnung/die übergeordnete Zuordnung in der Zuordnungsansicht geöffnet haben, die über eine Schlüsseldefinition verfügt, oder fügen Sie den Pfad der Stammzuordnung manuell im selben Dialogfeld hinzu.


<br>
<br>
<br>


Posten Sie für Abfragen im AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) .
