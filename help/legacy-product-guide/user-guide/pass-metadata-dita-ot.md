---
title: Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT
description: Erfahren Sie, wie Sie die Metadaten mithilfe der DITA-OT-Veröffentlichung in AEM Guides an die Ausgabe weitergeben.
feature: Publishing, Metadata Management
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT {#id21BJ00QD0XA}

Metadaten sind zusätzliche Informationen zur Ausgabe. In AEM Guides können Sie die vorhandenen Metadaten weitergeben oder benutzerdefinierte Metadaten-Tags erstellen. Sie können Metadaten mithilfe der DITA-OT-Veröffentlichung an AEM-, PDF-, HTML5-, EPUB- und benutzerdefinierte Formatausgaben übergeben.

Führen Sie die folgenden Schritte aus, um die Metadaten mithilfe der DITA-OT-Veröffentlichung an die Ausgabe zu übergeben:

1. Navigieren Sie in der **Assets-Benutzeroberfläche** zur DITA-Map-Datei, für die Sie die Metadaten an DITA-OT übergeben möchten, und klicken Sie darauf.
1. Wählen Sie eine Ausgabevorgabe aus und bearbeiten Sie sie, an die Sie die Metadatenfelder übergeben möchten. Wählen Sie beispielsweise eine PDF-Ausgabevorgabe aus.
1. Wählen Sie **DITA-OT** unter Generate &lt;output\> Using (Generieren von &lt;output\> mithilfe) in der ausgewählten Ausgabevorgabe aus.

   ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. Wählen Sie in der Dropdown-Liste Eigenschaften die Metadaten aus, die Sie an die DITA-OT-Veröffentlichung übergeben möchten.

   In der Dropdown-Liste &quot;Eigenschaften&quot;werden sowohl die benutzerdefinierten als auch die Standardeigenschaften aufgelistet. Im obigen Screenshot-Autor ist beispielsweise die benutzerdefinierte Eigenschaft, während `dc:description`, `dc:language`, `dc:title` und `docstate` die Standardeigenschaften sind.

   >[!NOTE]
   >
   > Diese Eigenschaften werden aus der Metadatenlisten-Datei ausgewählt, die am folgenden Speicherort verfügbar ist:`/libs/fmdita/config/metadataList`. Standardmäßig sind in dieser Datei vier Eigenschaften aufgeführt: `dc:description`, `dc:language`, `dc:title` und `docstate`.

   Diese Datei kann überlagert werden unter: `/apps/fmdita/config/metadataList`.

   Informationen zum Übergeben einer benutzerdefinierten Eigenschaft, für die Sie die Werte bereits definiert haben, finden Sie unter [Verwenden AEM Metadaten in der DITA-OT-PDF-Ausgabe](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Wählen Sie aus der Dropdown-Liste **Eigenschaften** die erforderlichen benutzerdefinierten und standardmäßigen Eigenschaften aus. Wählen Sie beispielsweise `author`, `dc:title` und `dc:description` aus. Dies sind die standardmäßigen `metadata/properties` , die erstellt werden, sobald wir eine Datei erstellen. Die ausgewählten Eigenschaften werden unter dem Dropbox-Menü aufgelistet.

   ![](images/selected-metadata-properties.png){width="300" align="left"}

1. Klicken Sie oben links auf **Fertig** , um die Änderungen zu speichern.
1. Generieren Sie die Ausgabe.

Die ausgewählten Metadateneigenschaften werden an die mit DITA-OT generierte Ausgabe übergeben.

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
