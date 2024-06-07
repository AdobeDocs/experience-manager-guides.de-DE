---
title: Native PDF-Veröffentlichungsfunktion | Barcode hinzufügen
description: Erfahren Sie, wie Sie Barcodes hinzufügen.
source-git-commit: a766353908829ab433173f8fd003ecad0c9d1bf1
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---


# Barcode zur PDF-Ausgabe hinzufügen

Ein Barcode ist ein Datenmuster, das Maschinen lesen können. Kunden können Barcodes mit einem Barcode-Scanner oder ihrer Smartphone-Kamera scannen. Kodierungsinformationen wie Produktdetails, Inventarnummern oder Website-URLs können hilfreich sein. Das Hinzufügen von Barcodes hilft Ihnen, die Daten einfach zu erfassen, das Kundenerlebnis zu verbessern und ein besseres Datenmanagement und bessere Sicherheit zu gewährleisten.

Sie können einen Stil für den Barcode erstellen. und verwenden Sie ihn zum Einfügen eines Barcodes in ein Seitenlayout. Sie können den Stil auf einen Beispiel-Barcode im gewünschten Seitenlayout anwenden.


Dieses Tutorial hilft Ihnen beim Hinzufügen von Barcodes in der PDF-Ausgabe.

## Schritte zum Generieren eines Barcodes

Führen Sie die folgenden Schritte aus, um einen Barcode zu generieren:

### CSS der Vorlage aktualisieren, um einen Barcode-Wert zu rendern

Ändern Sie die `layout.css` -Datei, um einen Barcode während der PDF-Erstellung wiederzugeben. Es werden verschiedene Barcode-Typen wie &quot;qrcode&quot;und &quot;pdf417&quot;unterstützt.  Weitere Informationen finden Sie unter [Barcode-Typen](#barcode-types).



```css
...
.barcode { 
-ro-replacedelement: barcode;   
-ro-barcode-type: code128;   
-ro-barcode-size: 100%;   
-ro-barcode-content: content();   
object-fit: contain;   
margin-top: 2mm;
 
}
...
```

### Verwenden Sie den CSS-Stil, um den Barcode zu generieren

Sie können den Barcode auf unterschiedliche Weise generieren. Einige der Beispiele sind:

**Beispiel 1**

Fügen Sie einen Barcode-Platzhalter in der Vorlagenkopfzeile hinzu und wenden Sie den Stil an:

1. Bearbeiten **Vorlagen** > **Seitenlayouts**
1. Wählen Sie ein Seitenlayout aus. Sie können beispielsweise das Seitenlayout &quot;BackCover&quot;auswählen, das die Kopf- oder Fußzeile enthält.
1. Fügen Sie den folgenden Bereich an der Stelle hinzu, an der Sie den Barcode einfügen möchten.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Verwenden Sie denselben Klassennamen, den Sie in der `layout.css`.

1. Ersetzen `<Sample barcode>` mit dem Wert, den der Barcode-Scanner lesen soll.

Sie können den Barcode beim Generieren der Ausgabe-PDF mithilfe der Vorlage anzeigen, die das Seitenlayout enthält. Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie die PDF-Ausgabe mit einem Barcode generieren.

Der folgende Screenshot zeigt einen Beispiel-Barcode in einer PDF-Ausgabe.

<img src="./assets/barcode-output-sample.png" alt="Beispielausgabe mit Barcode" width="700" border="2px">

**Beispiel 2**

Ändern Sie die `Common.plt` in der Datei **Allgemein** Vorlage , um einen Barcode nach dem Projekttitel hinzuzufügen.

Um einen Barcode für eine ISBN-Nummer zu erstellen, fügen Sie eine ISBN-Nummer hinzu. Verwenden Sie dann die ISBN-Nummer, um den Barcode zu generieren.

```html
...

  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode">978-1-56619-909-4</span></p>
  </div>
} 
...
```

**Beispiel 3**

So erstellen Sie einen Barcode mit den Zuordnungsmetadaten:

Verwenden Sie alle im Abschnitt `<topicmeta>` -Element einer DITA-Zuordnung, die als Barcode angezeigt werden soll. Stellen Sie sicher, dass Sie den richtigen XPath verwenden. Sie können beispielsweise eine `<resourceid>` im `<topicmeta>` einer DITA-Zuordnung.

Im folgenden Beispiel dient die Ressourcen-ID als Haupteingabe zum Generieren des Barcodes.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```



Sie können die Ressourcen-ID wie folgt in einem Seitenlayout verwenden:


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Barcode-Typen {#barcode-types}

Einige der häufig verwendeten Barcodes sind wie folgt:

| Typ | -ro-barcode-type | Zusätzliche Details |
| ---| --- | --- |
| QR-Code | qrcode | Die QR-Code-Strichcode-Symbole nach ISO/IEC 18004:2015. |
| Code 128 | code128 | Die Code 128-Barcode-Symbologie gemäß ISO/IEC 15417:2007. |
| Code 32 | code32 | Code 32, auch als italienischer Armakode bezeichnet. |
| Code 49 | code49 | Code 49 nach ANSI/AIM-BC6-2000. |
| Code 11 | code11 |                            |
| Code 93 | code93 |                            |
| Code16k | code16k |                            |
| PDF417 | pdf417 | Die Barcode-Symbole PDF417/MicroPDF417 gemäß ISO/IEC 15438:2006 und ISO/IEC 24728:2006. |
| Code 3 von 9 | code39 | Code 3 von 9 Strichcode-Symbologien nach ISO/IEC 16388:2007. |
| MSI Plessey | msiplessey |                            |
| Kanalcode | channelcode | Kanalcode nach ANSI/AIM BC12-1998. |
| Codabar | codabar | Codabar Barcode Symbologie nach BS EN 798:1996. |
| EAN-8 | ean-8 | EAN-Strichcode-Symbole nach BS EN 797:1996. |
| EAN-13 | ean-13 | EAN-Strichcode-Symbole nach BS EN 797:1996. |
| UPC-A | upc-a | UPC-Strichcode-Symbole nach BS EN 797:1996. |
| UPC-E | upc-e | UPC-Strichcode-Symbole nach BS EN 797:1996. |
| Ean/UPC Addon | addon | EAN/UPC Add-On Barcode Symbologie nach BS EN 797:1996. |
| Telepen | telepen | Wird auch als Telepen-Alpha bezeichnet. |
| GS1 Datenbank/Datenbank 14 | Datenbank | GS1 DataBar nach ISO/IEC 24724:2011. |
| GS1-Datenbank erweitert/Datenbank 14 erweitert | datenbankerweitert | GS1 DataBar erweitert gemäß ISO/IEC 24724:2011. |
| GS1 Databar Limited | datenbankgebunden | GS1 DataBar Limited nach ISO/IEC 24724:2011. |
| POSTNET (Postal Numeric Encoding Technique) | postnet | Die vom US Postal Service verwendeten Strichcodetypen POSTNET (Postal Numeric Encoding Technique). |
| Pharmazie-Zentralnummer (PZN-8) | pzn8 | Eine auf Code 39 basierende Symbologie, die von der Pharmaindustrie in Deutschland verwendet wird. |
| Pharmakovigilanz | Pharmakokinetik |                            |
| Codablock F | codablockf | Symbole nach AIM Europe &quot;Uniform Symbology Specification Codablock F&quot;, 1995. |
| Logmars | logmars | Der vom US-Verteidigungsministerium verwendete Standard LOGMARS (Logistics Applications of Automated Marking and Reading Symbols). |
| Aztec Runes | aztec-runes | Aztec Runes-Strichcode-Symbole nach ISO/IEC 24778:2008 Anhang A. |
| Aztec Code | aztec-code | Aztec Code Strichcode-Symbole gemäß ISO/IEC 24778:2008. |                            |
| DataMatrix | data-matrix | Datenmatrix ECC 200 Strichcode-Symbologien nach ISO/IEC 16022:2006. |
| Code 1 | code-one |                            |



