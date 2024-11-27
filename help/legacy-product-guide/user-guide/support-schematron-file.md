---
title: Unterstützung für Schematron-Dateien
description: Erfahren Sie, wie Sie ein DITA-Thema importieren und validieren, Assert-Berichtanweisungen verwenden, um nach Regeln zu suchen, Regex-Ausdrücke zu verwenden und abstrakte Muster in Schemateien von AEM Guides zu definieren.
exl-id: ed07a5ec-6adc-43a3-8f03-248b8c963e9a
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%

---

# Unterstützung für Schematron-Dateien

&quot;Schematron&quot;bezieht sich auf eine regelbasierte Validierungssprache, die zum Definieren von Tests für eine XML-Datei verwendet wird. Der Web Editor unterstützt Schematron-Dateien. Sie können die Schemadateien importieren und sie auch im Web-Editor bearbeiten. Mithilfe einer Schematron-Datei können Sie bestimmte Regeln definieren und sie dann für ein DITA-Thema oder eine Zuordnung validieren.

>[!NOTE]
>
> Der Webeditor unterstützt ISO-Schemata.


## Schemateien importieren

Führen Sie die folgenden Schritte aus, um die Schematron-Dateien zu importieren:

![](images/scematron-panel-add.png){width="300" align="left"}

1. Navigieren Sie in der *Repository-Ansicht* zum gewünschten Ordner (in den Sie die Dateien hochladen möchten).
1. Klicken Sie auf das Symbol **Optionen** , um das Kontextmenü zu öffnen und die Option **Assets hochladen** zu wählen.
1. Im Dialogfeld **Assets hochladen** können Sie den Zielordner im Feld **Asset-Ordner auswählen** ändern.
1. Klicken Sie auf **Dateien auswählen** und wählen Sie die Schematrondateien aus. Sie können eine oder mehrere Schemadateien auswählen und dann auf **Hochladen** klicken.

## Validieren eines DITA-Themas oder -Map mit Schematron

Nach dem Import von Schematron-Dateien können Sie diese im Web-Editor bearbeiten. Sie können die Schematron-Dateien verwenden, um die Themen oder eine DITA-Zuordnung zu validieren. Sie können beispielsweise die folgenden Regeln für eine DITA-Zuordnung oder ein Thema erstellen:

* Ein Titel wird für eine DITA-Zuordnung definiert.
* Eine kurze Beschreibung einer bestimmten Länge wurde hinzugefügt.
* Es sollte mindestens eine topicref in der Karte vorhanden sein.

Wenn Sie ein Thema im Web Editor öffnen, wird rechts ein Bedienfeld zur Schemavalidierung angezeigt. Führen Sie die folgenden Schritte aus, um ein Thema oder eine Zuordnung mit einer Schematron-Datei hinzuzufügen und zu validieren:
![](images/schematron-validate.png){width="300" align="left"}

1. Klicken Sie auf das Schematron -Symbol (), um das Bedienfeld &quot;Schematron&quot;zu öffnen.
1. Verwenden Sie Schematron-Datei hinzufügen , um Schematron-Dateien hinzuzufügen.
1. Wenn die Schematron-Datei keine Fehler aufweist, wird sie hinzugefügt und im Überprüfungsfenster aufgelistet. Für die Schematron-Datei mit Fehlern wird eine Fehlermeldung angezeigt.
   >[!NOTE]
   >
   >Sie können das Kreuzsymbol neben dem Schematron-Dateinamen verwenden, um es zu entfernen.
1. Klicken Sie auf Mit Schema validieren , um das Thema zu validieren.

   * Wenn das Thema keine Regeln unterbricht, wird die Validierungs-Erfolgsmeldung für die Datei angezeigt.
   * Wenn das Thema eine Regel beschädigt, z. B. wenn es keinen Titel enthält und für das oben angegebene Schema validiert wird, wird ein Validierungsfehler angezeigt.

1. Klicken Sie auf die Fehlermeldung, um das Element, das den Fehler enthält, im geöffneten Thema/in der geöffneten Zuordnung zu markieren.

Die Schemaunterstützung im Web Editor hilft Ihnen dabei, die Dateien anhand eines Regelsatzes zu validieren und Konsistenz und Korrektheit über die Themen hinweg zu gewährleisten.

## Verwenden Sie Assets und Berichtanweisungen, um nach Regeln zu suchen.{#schematron-assert-report}

AEM Guides unterstützt auch die Assert- und Berichtanweisungen in Schematron. Diese Anweisungen helfen Ihnen bei der Validierung Ihrer DITA-Themen.

### Assert-Anweisung

Eine Assert-Anweisung generiert eine Meldung, wenn eine Testanweisung als &quot;false&quot;ausgewertet wird. Wenn Ihr Titel beispielsweise fett sein soll, können Sie eine Assert-Anweisung dafür definieren.

```XML
<sch:rule context="title"> 
    <sch:assert test = "b"> Title should be bold </sch:assert>
  </sch:rule>
```

Wenn Sie Ihre DITA-Themen mit dem Schema validieren, erhalten Sie eine Nachricht für die Themen, bei denen der Titel nicht fett dargestellt wird.

### Berichtserklärung

Eine Berichtanweisung generiert eine Meldung, wenn eine Testanweisung als &quot;true&quot;ausgewertet wird. Wenn Sie beispielsweise eine Kurzbeschreibung von 150 Zeichen oder weniger wünschen, können Sie eine Berichtanweisung definieren, um die Themen zu überprüfen, bei denen die Kurzbeschreibung mehr als 150 Zeichen umfasst.
Wenn Sie Ihre DITA-Themen mit dem Schema validieren, erhalten Sie einen vollständigen Bericht der Regeln, für die die Berichtanweisung &quot;true&quot;ergibt. Sie erhalten also eine Nachricht für die Themen, bei denen die kurze Beschreibung mehr als 150 Zeichen umfasst.


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
> Verwenden Sie beim Schreiben der Schemaregeln nur Xpath 2.0-Ausdrücke.

## Verwenden von Regex-Ausdrücken{#schematron-regex-espressions}

Sie können auch Regex-Ausdrücke verwenden, um eine Regel mit der Funktion matches() zu definieren und dann mithilfe der Schematron-Datei eine Validierung durchzuführen.

Beispielsweise können Sie damit eine Nachricht anzeigen, wenn der Titel nur ein Wort enthält.

```XML
<assert test="not(matches(.,'^\w+$'))"> 
No one word titles.
</assert>  
```


## Abstrakte Muster definieren{#schematron-abstract-patterns}

AEM Guides unterstützt auch abstrakte Muster in Schematron. Sie können allgemeine abstrakte Muster definieren, um diese abstrakten Muster wiederzuverwenden.  Sie können Platzhalterparameter erstellen, die das tatsächliche Muster angeben.


Die Verwendung abstrakter Muster kann das Schema vereinfachen, indem die Duplizierung von Regeln reduziert und die Verwaltung und Aktualisierung Ihrer Validierungslogik vereinfacht wird. Außerdem kann es das Verständnis Ihres Schemas vereinfachen, da Sie komplexe Validierungslogik in einem einzigen abstrakten Muster definieren können, das im gesamten Schema wiederverwendet werden kann.


Beispielsweise erstellt der folgende XML-Code ein abstraktes Muster und das eigentliche Muster verweist mithilfe der ID auf dieses Muster.

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
