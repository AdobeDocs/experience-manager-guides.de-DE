---
title: Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT
description: Erfahren Sie, wie Sie die Metadaten mithilfe der DITA-OT-Veröffentlichung in AEM Guides an die Ausgabe übergeben.
feature: Publishing, Metadata Management
role: User
hide: true
exl-id: 55d70c6d-feb0-43f7-9f18-6d1ccdd1e728
TQID: https://experienceleague.adobe.com/I-DddG1Wq9cXsF1IZt6B0XFzbR1gbtvtKPoO-g2nLM0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 330
ht-degree: 0%

---

# Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT {#id21BJ00QD0XA}

Metadaten sind zusätzliche Informationen zur Ausgabe. In AEM Guides können Sie die vorhandenen Metadaten übergeben oder benutzerdefinierte Metadaten-Tags erstellen. Mit der DITA-OT-Veröffentlichung können Sie Metadaten an AEM, PDF, HTML5, EPUB und benutzerdefinierte Formatausgaben übergeben.

Führen Sie die folgenden Schritte aus, um die Metadaten mithilfe von DITA-OT-Publishing an die Ausgabe zu übergeben:

1. Navigieren Sie in der **Assets**-Benutzeroberfläche zu der DITA-Zuordnungsdatei, für die Sie die Metadaten an das DITA-OT übergeben möchten, und klicken Sie darauf.
1. Wählen Sie eine Ausgabevorgabe aus, an die Sie die Metadatenfelder übergeben möchten, und bearbeiten Sie sie. Wählen Sie beispielsweise die PDF-Ausgabevorgabe aus.
1. Wählen Sie **DITA-OT** unter der Option &lt;output\> mit generieren in der ausgewählten Ausgabevorgabe aus.

   ![](images/custom-meta-data-output-preset.png){width="800"}

1. Wählen Sie aus der Dropdown-Liste Eigenschaften die Metadaten aus, die Sie an die DITA-OUT-Veröffentlichung übergeben möchten.

   Das Dropdown-Menü „Eigenschaften“ listet sowohl die benutzerdefinierten als auch die Standardeigenschaften auf. Im obigen Screenshot ist Autor beispielsweise die benutzerdefinierte Eigenschaft, während `dc:description`, `dc:language`, `dc:title` und `docstate` die Standardeigenschaften sind.

   >[!NOTE]
   >
   > Diese Eigenschaften werden aus der Datei „metadataList“ ausgewählt, die unter dem folgenden Speicherort verfügbar ist:`/libs/fmdita/config/metadataList`. Standardmäßig werden in dieser Datei vier Eigenschaften aufgelistet: `dc:description`, `dc:language`, `dc:title` und `docstate`.

   Diese Datei kann überlagert werden unter: `/apps/fmdita/config/metadataList`.

   Informationen zum Übergeben einer benutzerdefinierten Eigenschaft, für die Sie bereits die Werte definiert haben, finden Sie unter [Verwenden von AEM-Metadaten in der DITA-OT-PDF-Ausgabe](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880?profile.language=de).

1. Wählen Sie **Dropdown-** „Eigenschaften“ die erforderlichen benutzerdefinierten und Standardeigenschaften aus. Wählen Sie beispielsweise `author`, `dc:title` und `dc:description`. Dies sind die `metadata/properties`, die erstellt werden, sobald wir eine Datei erstellen. Die ausgewählten Eigenschaften werden unter der Dropbox aufgelistet.

   ![](images/selected-metadata-properties.png){width="300"}

1. Klicken **oben links** Fertig“, um die Änderungen zu speichern.
1. Ausgabe generieren.

Die ausgewählten Metadateneigenschaften werden an die mit DITA-OT generierte Ausgabe übergeben.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Ausgabegenerierung](generate-output.md)
