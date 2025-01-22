---
title: Aktivieren von kontextuellen Inhaltsvariablen (CCVAR) in AEM Sites über AEM Guides
description: Arbeiten mit kontextuellen Inhaltsvariablen (CCVAR) in AEM Sites über AEM Guides
exl-id: null
feature: Web Editor
role: User, Admin
source-git-commit: ac40ab63b691ea31dfa1a3c9f7644b357b3167a4
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 2%

---

# Aktivieren von kontextuellen Inhaltsvariablen (CCVAR) in AEM Sites über AEM Guides

Kontextuelle Inhaltsvariablen (CCVAR) sind eine Funktion von ACS Commons, mit der Autoren dynamische Inhaltsvariablen direkt in ihrem erstellten Text verwenden können. Während CCVAR häufig in AEM Sites verwendet wird, wird in diesem Artikel erläutert, wie Sie ähnliche Funktionen über Seiten erreichen können, die aus in **AEM Guides** erstellten Inhalten generiert wurden (*primär mithilfe von in der DITA-Zuordnung definierten Schlüsselwörtern*.


## Was sind kontextuelle Inhaltsvariablen (CCVAR)?

Mit CCVAR können Autoren dynamische Variablen in ihren Inhalt einfügen, die zur Laufzeit kontextabhängig aufgelöst werden. Beispielsweise können Variablen wie `((page_properties.pageTitle))` den Seitentitel beim Rendern von Inhalten dynamisch abrufen.


## Wie wird CCVAR in AEM Sites aktiviert, das aus AEM Guides generiert wurde?

Da AEM Guides als Quelle aller Inhalte (einschließlich AEM Sites, PDF oder HTML5) verwendet wird, müssen Sie zum Aktivieren von CCVARs auf aus AEM Guides generierten Seiten Schlüsselwörter verwenden, um den CCVAR-Namen zu definieren. Definieren Sie dazu in den Handbüchern **Keywords** in Ihrer DITA-Zuordnung mithilfe `<keydef>` Elemente. Diese Schlüsselwörter können dynamischen Werten (oder CCVAR-Namen) entsprechen, sodass Sie in Ihren DITA-Themen darauf verweisen können.


## Voraussetzungen

Bevor Sie fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. **AEM ACS Commons installiert**:
   - Stellen Sie sicher **dass „ACS AEM**&quot; auf Ihrer AEM-Instanz installiert ist. Dies ist für die Verwendung von CCVAR erforderlich.

2. **Konfiguration von kontextuellen Inhaltsvariablen**:
   - Schließen Sie die Einrichtung für **Kontextuelle Inhaltsvariablen** in AEM mithilfe der [offiziellen Dokumentation](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html) ab. Hierzu gehört Folgendes:
      - Aktivieren **Eigenschaftenaggregation**.
      - Konfigurieren von **HTML-Neuschreibungen** (bei Verwendung der HTML-Ausgabe).
      - Konfigurieren von **JSON-Rewriting** (bei Verwendung der JSON-Ausgabe).



## Schritte zum Aktivieren von CCVAR in AEM Guides

### 1. Definieren von Keywords in der DITA-Zuordnung

- Definieren Sie in AEM Guides Schlüsselwörter mithilfe `<keydef>` Elemente in der DITA-Zuordnung, die der CCVAR entsprechen.
- Zum Beispiel:

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```

- Das `keys`-Attribut (in diesem Beispiel `product`) wird verwendet, um in Ihren DITA-Themen auf diese Variable zu verweisen.


## 2. Verwenden von Keywords in DITA-Themen

- Verwenden Sie in diesem Thema das Keyword überall dort, wo die CCVar verwendet werden soll.
- Zum Beispiel:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- Das `keyref`-Attribut verweist auf den im `<keydef>`-Element definierten `keys` (in diesem `product`).
- Während der Ausgabegenerierung wird das Keyword durch den entsprechenden CCVar-Wert ersetzt.


## 3. Ausgabe generieren

- Wenn Sie eine Ausgabe für AEM Sites generieren, werden die Schlüsselwortverweise in die entsprechenden dynamischen Werte aufgelöst.
- Zum Beispiel:
   - Wenn `((page_properties.pageTitle))` zu `My Product` aufgelöst wird, wird die Ausgabe angezeigt:

```xml
   This is the title of the product: My Product.
```


## Anwendungsbeispiel

Angenommen, Sie möchten die Sprache der Seite dynamisch in Ihre DITA-Themen einfügen. So können Sie dies erreichen:

**Definieren Sie das Keyword in der DITA-Zuordnung**:

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

**Referenzieren Sie das Keyword in einem DITA-Thema**:

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

**Erzeugte Ausgabe**:

Wenn `((inherited_page_properties.jcr:language))` zu `en` aufgelöst wird, wird die Ausgabe angezeigt:

```
     The language of this page is: en.
```


### Ressourcen

Weitere Informationen zu **kontextuellen Inhaltsvariablen** finden Sie in der offiziellen Dokumentation:\
[Kontextuelle Inhaltsvariablen in AEM Commons](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)