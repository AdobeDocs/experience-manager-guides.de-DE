---
title: Unterstützung für Schematron-Dateien
description: Erfahren Sie, wie Sie ein DITA-Thema importieren und validieren, mithilfe von Assert-Berichtsanweisungen nach Regeln suchen, Regex-Ausdrücke verwenden und abstrakte Muster in Schematron-Dateien von AEM Guides definieren.
exl-id: ed07a5ec-6adc-43a3-8f03-248b8c963e9a
feature: Authoring, Features of Web Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%

---

# Unterstützung für Schematron-Dateien

„Schematron“ bezieht sich auf eine regelbasierte Validierungssprache, die zum Definieren von Tests für eine XML-Datei verwendet wird. Der Web-Editor unterstützt Schematron-Dateien. Sie können die Schematron-Dateien importieren und auch im Web-Editor bearbeiten. Mithilfe einer Schematron-Datei können Sie bestimmte Regeln definieren und diese dann für ein DITA-Thema oder eine Zuordnung validieren.

>[!NOTE]
>
> Web-Editor unterstützt ISO Schematron.


## Schematron-Dateien importieren

Führen Sie die folgenden Schritte aus, um die Schematron-Dateien zu importieren:

![](images/scematron-panel-add.png){width="300" align="left"}

1. Navigieren Sie zum erforderlichen Ordner (in den Sie die Dateien hochladen möchten) in der *Repository-Ansicht*.
1. Klicken Sie auf das **Optionen**-Symbol, um das Kontextmenü zu öffnen und **Assets hochladen**.
1. Im Dialogfeld **Assets hochladen** können Sie den Zielordner im Feld **Asset-Ordner auswählen** ändern.
1. Klicken Sie **Dateien auswählen** und durchsuchen Sie die Schematron-Dateien, um sie auszuwählen. Sie können eine oder mehrere Schematron-Dateien auswählen und dann auf &quot;**&quot;**.

## Validieren eines DITA-Themas oder einer DITA-Zuordnung mit Schematron

Nach dem Import von Schematron-Dateien können Sie diese im Web-Editor bearbeiten. Sie können die Schematron-Dateien verwenden, um die Themen oder eine DITA-Zuordnung zu validieren. Sie können beispielsweise die folgenden Regeln für eine DITA-Zuordnung oder ein Thema erstellen:

* Ein Titel wird für eine DITA-Zuordnung definiert.
* Eine kurze Beschreibung einer bestimmten Länge wurde hinzugefügt.
* Es muss mindestens eine TopicRef in der Karte vorhanden sein.

Wenn Sie ein Thema im Web-Editor öffnen, wird rechts ein Bedienfeld für die Schematronvalidierung angezeigt. Führen Sie die folgenden Schritte aus, um ein Thema oder eine Zuordnung mit einer Schematron-Datei hinzuzufügen und zu validieren:
![](images/schematron-validate.png){width="300" align="left"}

1. Klicken Sie auf das Schematron-Symbol (), um das Schematron-Bedienfeld zu öffnen.
1. Verwenden Sie Schematrondatei hinzufügen , um Schematrondateien hinzuzufügen.
1. Wenn die Schematron-Datei keine Fehler enthält, wird sie hinzugefügt und im Validierungsfenster aufgeführt. Für die Schematron-Datei mit Fehlern wird eine Fehlermeldung angezeigt.
   >[!NOTE]
   >
   >Sie können das Kreuz-Symbol neben dem Namen der Schematron-Datei verwenden, um sie zu entfernen.
1. Klicken Sie auf Mit Schematron validieren , um das Thema zu validieren.

   * Wenn beim Thema keine Regeln verletzt werden, wird die Erfolgsmeldung für die Datei angezeigt.
   * Wenn das Thema eine Regel umgeht, z. B. wenn es keinen Titel enthält und für das oben angegebene Schematron validiert wurde, wird ein Validierungsfehler angezeigt.

1. Klicken Sie auf die Fehlermeldung, um das Element mit dem Fehler im geöffneten Thema/in der geöffneten Zuordnung hervorzuheben.

Die Unterstützung von Schematronen im Web-Editor hilft Ihnen bei der Validierung der Dateien anhand eines Regelsatzes und der Aufrechterhaltung der Konsistenz und Korrektheit über die Themen hinweg.

## Verwenden Sie Assert- und Report-Anweisungen, um auf Regeln zu prüfen{#schematron-assert-report}

AEM Guides unterstützt auch die Assert- und Report-Anweisungen in Schematron. Mithilfe dieser Anweisungen können Sie Ihre DITA-Themen überprüfen.

### Bestätigung

Eine Assert-Anweisung erzeugt eine Meldung, wenn eine Testanweisung als „false“ ausgewertet wird. Wenn Ihr Titel beispielsweise fett formatiert sein soll, können Sie eine Assert-Anweisung dafür definieren.

```XML
<sch:rule context="title"> 
    <sch:assert test = "b"> Title should be bold </sch:assert>
  </sch:rule>
```

Wenn Sie Ihre DITA-Themen mit dem Schematron überprüfen, erhalten Sie eine Meldung für die Themen, bei denen der Titel nicht fett gedruckt ist.

### Berichtsanweisung

Eine Berichtsanweisung erzeugt eine Meldung, wenn eine Testanweisung als „true“ ausgewertet wird. Wenn Sie beispielsweise möchten, dass die Kurzbeschreibung maximal 150 Zeichen lang ist, können Sie eine Berichtsanweisung definieren, um die Themen zu überprüfen, bei denen die Kurzbeschreibung mehr als 150 Zeichen lang ist.
Wenn Sie Ihre DITA-Themen mit dem Schematron überprüfen, erhalten Sie einen vollständigen Bericht der Regeln, in denen die Berichtsanweisung als „true“ ausgewertet wird. So erhalten Sie eine Nachricht für die Themen, bei denen die Kurzbeschreibung mehr als 150 Zeichen umfasst.


```XML
<sch:rule context="shortdesc"> 
        <sch:let name="characters" value="string-length(.)"/> 
        <sch:report test="$characters &gt; 150">  
        The short description has <sch:value-of select="$characters"/> characters. It should contain more than 150 characters.      
        </sch:report>   
    </sch:rule> 
```

>[!NOTE]
>
> Verwenden Sie beim Schreiben der Schematron-Regeln nur XPath 2.0-Ausdrücke.

## Verwenden von Regex-Ausdrücken{#schematron-regex-espressions}

Sie können auch Regex-Ausdrücke verwenden, um eine Regel mit matches()-Funktion zu definieren und dann eine Validierung mithilfe der Schematron-Datei durchzuführen.

Beispielsweise können Sie damit eine Meldung anzeigen, wenn der Titel nur ein Wort enthält.

```XML
<assert test="not(matches(.,'^\w+$'))"> 
No one word titles.
</assert>  
```


## Abstrakte Muster definieren{#schematron-abstract-patterns}

AEM Guides unterstützt auch abstrakte Muster in Schematron. Sie können generische abstrakte Muster definieren, um diese abstrakten Muster wiederzuverwenden.  Sie können Platzhalterparameter erstellen, die das tatsächliche Muster angeben.


Die Verwendung abstrakter Muster kann Ihr Schematron-Schema vereinfachen, indem die Duplizierung von Regeln reduziert wird und die Verwaltung und Aktualisierung Ihrer Validierungslogik erleichtert wird. Dies kann auch Ihr Schema verständlicher machen, da Sie komplexe Validierungslogik in einem einzigen abstrakten Muster definieren können, das im gesamten Schema wiederverwendet werden kann.


Beispielsweise erstellt der folgende XML-Code ein abstraktes Muster und das eigentliche Muster verweist dann mithilfe der ID darauf.

```XML
<sch:pattern abstract="true" id="LimitNoOfWords"> 

<sch:rule context="$parentElement"> 

<sch:let name="words" value="string-length(.)"/> 

<sch:assert test="$words &lt; $maxWords"> 

You have <sch:value-of select="$words"/> letters. This should be lesser than <sch:value-of select="$maxWords"/>. 

</sch:assert>  

<sch:assert test="$words &gt; $minWords"> 

You have <sch:value-of select="$words"/> letters. This should be greater than <sch:value-of select="$minWords"/>. 

</sch:assert>  

</sch:rule> 

</sch:pattern> 

<sch:pattern is-a="LimitNoOfWords" id="extend-LimitNoOfWords"> 

<sch:param name="parentElement" value="title"/> 

<param name="minWords" value="1"/> 

<param name="maxWords" value="8"/> 

</sch:pattern> 
```
