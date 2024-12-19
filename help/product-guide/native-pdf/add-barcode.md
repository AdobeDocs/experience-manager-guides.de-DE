---
title: Native PDF Publish-Funktion | Strichcode hinzufügen
description: Erfahren Sie, wie Sie Barcodes hinzufügen.
exl-id: 206bdcf9-2bcd-4bf1-815a-c97cdf0dc415
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---

# Hinzufügen eines Barcodes zur PDF-Ausgabe

Ein Barcode ist ein Datenmuster, das Maschinen lesen können. Kunden können Barcodes mit einem Barcodescanner oder ihrer Smartphone-Kamera scannen. Kodierungsinformationen wie Produktdetails, Inventarnummern oder Website-URLs können hilfreich sein. Durch das Hinzufügen von Barcodes können Sie die Daten einfach erfassen, das Kundenerlebnis verbessern und ein besseres Daten-Management und mehr Sicherheit ermöglichen.

Sie können einen Stil für den Barcode erstellen. und fügen Sie damit einen Barcode in ein Seiten-Layout ein. Sie können den Stil auf einen Beispiel-Barcode im gewünschten Seiten-Layout anwenden.


In diesem Tutorial erfahren Sie, wie Sie Barcodes in der PDF-Ausgabe hinzufügen.

## Schritte zum Generieren eines Barcodes

Um einen Barcode zu generieren, führen Sie die folgenden Schritte aus:

### Aktualisieren des CSS der Vorlage, um einen Barcodewert zu rendern

Ändern Sie die `layout.css` Datei, um während der PDF-Generierung einen Barcode zu rendern. Es werden verschiedene Barcodetypen wie „qrcode“ und „pdf417“ unterstützt.  Weitere Informationen finden Sie unter [Barcodetypen](#barcode-types).



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

### Verwenden des CSS-Stils zum Generieren des Barcodes

Sie können den Barcode auf verschiedene Arten generieren. Einige der Beispiele sind:

**Beispiel 1**

Fügen Sie einen Barcode-Platzhalter in der Vorlagenkopfzeile hinzu und wenden Sie den Stil an:

1. Bearbeiten **Vorlagen** > **Seiten-Layouts**
1. Wählen Sie ein Seiten-Layout aus. Sie können beispielsweise das Layout der Rückseite auswählen, das die Kopf- oder Fußzeile enthält.
1. Fügen Sie den folgenden Bereich an der Stelle hinzu, an der Sie den Barcode einfügen möchten.

   `<span class="barcode">Sample barcode</span></p>`.

   >[!NOTE]
   >
   > Verwenden Sie denselben Klassennamen, den Sie im `layout.css` definiert haben.

1. Ersetzen Sie `<Sample barcode>` durch den Wert, den der Barcode-Scanner lesen soll.

Sie können den Barcode beim Generieren der Ausgabe-PDF mithilfe der Vorlage anzeigen, die das Seiten-Layout enthält. Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie die PDF-Ausgabe mit einem Barcode generieren.

Der folgende Screenshot zeigt einen Beispiel-Barcode in einer PDF-Ausgabe.

<img src="./assets/barcode-output-sample.png" alt="Beispielausgabe mit Barcode" width="700" border="2px">

**Beispiel 2**

Ändern Sie die `Common.plt` in der **Basic**-Vorlage, um einen Barcode nach dem Projekttitel hinzuzufügen.

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

Verwenden Sie beliebige Metadaten, die im `<topicmeta>` Element einer DITA-Map vorhanden sind, um sie als Barcode anzuzeigen. Stellen Sie sicher, dass Sie den richtigen XPath verwenden. Sie können beispielsweise eine `<resourceid>` in der `<topicmeta>` einer DITA-Zuordnung hinzufügen.

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



Sie können die Ressourcen-ID in einem Seiten-Layout wie folgt verwenden:


```html
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
```

## Strichcodetypen {#barcode-types}

Einige der häufig verwendeten Barcodes sind die folgenden:

| Typ | Pro-Barcode-Typ | Zusätzliche Details |
| ---| --- | --- |
| QR-Code | qrcode | Die QR-Code-Strichcode-Symbologie gemäß ISO/IEC 18004:2015. |
| Code 128 | code128 | Der Code 128 Barcode Symbologie gemäß ISO/IEC 15417:2007. |
| Code 32 | code32 | Code 32, auch bekannt als italienischer Pharmakode. |
| Code 49 | code49 | Code 49 gemäß ANSI/AIM-BC6-2000. |
| Code 11 | Code11 |                            |
| Code 93 | Code93 |                            |
| Code16k | Code16K |                            |
| PDF417 | PDF417 | Die Strichcode-Symbologien PDF417/MicroPDF417 nach ISO/IEC 15438:2006 und ISO/IEC 24728:2006. |
| Code 3 von 9 | code39 | Der Code 3 der 9-Strichcode-Symbologie nach ISO/IEC 16388:2007. |
| MSI Plessey | Einfaches Set |                            |
| Kanalcode | channelCode | Kanalcode nach ANSI/AIM BC12-1998. |
| Codabar | Codabar | Codabar Barcode Symbologie nach BS EN 798:1996. |
| EAN-8 | EAN-8 | EAN-Barcode-Symbologie gemäß BS EN 797:1996. |
| EAN-13 | EAN-13 | EAN-Barcode-Symbologie gemäß BS EN 797:1996. |
| UPC-A | UPC-A | UPC-Strichcode-Symbologie nach BS EN 797:1996. |
| UPC-E | UPC-E | UPC-Strichcode-Symbologie nach BS EN 797:1996. |
| EAN/UPC-Add-on | Add-on | EAN/UPC-Add-on-Barcode-Symbologie gemäß BS EN 797:1996. |
| Telepen | telepen | Auch als Telepen-Alpha bekannt. |
| GS1-Datenbank / -Datenbank 14 | Datenbank | GS1 DataBar nach ISO/IEC 24724:2011. |
| GS1-Datenbank erweitert/Datenbank 14 erweitert | datenleistenerweitert | GS1 DataBar Expanded nach ISO/IEC 24724:2011. |
| GS1 DataBar Limited | datenbankbegrenzt | GS1 DataBar Limited nach ISO/IEC 24724:2011. |
| POSTNET (Postal Numeric Encoding Technique) | Postnetz | Die POSTNET-Barcode-Symbologie (Postal Numeric Encoding Technique) wird vom United States Postal Service verwendet. |
| Pharmazentralnummer (PZN-8) | pzn8 | Eine Code 39-basierte Symbologie, die von der Pharmaindustrie in Deutschland verwendet wird. |
| Pharmakode | Pharmakode |                            |
| Codablock F | Codablock | Symbologie nach AIM Europe „Uniform Symbology Specification Codablock F“, 1995. |
| Logmars | Logmars | Der vom US-Verteidigungsministerium verwendete LOGMARS-Standard (Logistics Applications of Automated Marking and Reading Symbols). |
| Aztec Runes | Azteken-Runen | Aztec Runes Strichcode Symbologie nach ISO/IEC 24778:2008 Anhang A. |
| Aztec Code | aztec-code | Aztec Code Strichcode Symbologie Nach ISO/IEC 24778:2008. |                            |
| DataMatrix | data-matrix | Data Matrix ECC 200 Barcode Symbologie Nach ISO/IEC 16022:2006. |
| Code 1 | Code-Eins |                            |
