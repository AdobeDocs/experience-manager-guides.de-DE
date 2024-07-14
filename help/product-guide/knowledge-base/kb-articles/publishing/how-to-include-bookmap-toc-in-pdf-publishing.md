---
title: Inhaltsveröffentlichung mit NativePDF
description: Veröffentlichen des Inhaltsverzeichnisses und anderer Leselisten für Ihre Datenbuchkarte mit NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
source-git-commit: 7638f3634ad45bbadda64ec6e3f706cbb65d696c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Generieren des Inhaltsverzeichnisses für Bookmap in der PDF-Veröffentlichung

## Einrichten Ihrer Lesekarte

Fügen Sie das Element `<toc>` hinzu:
Suchen Sie im `<frontmatter>` -Element Ihrer Bookmap nach dem Element `<booklists>` .  Verschachteln Sie ein `<toc>` -Element innerhalb von `<booklists>` wie folgt:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

Die DITA-Spezifikation ermöglicht auch die Platzierung des Inhaltsverzeichnisses und der Leselisten im Abschnitt `<backmatter>` .


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Beispielstruktur der Bookmap mit TOC , Figurliste und Tabellenliste in der Vorderseite und Indexliste im Hintergrund.

```
<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>
```

Das Inhaltsverzeichnis und die Leselisten werden automatisch basierend auf der in Ihrer Lesekarte definierten Struktur generiert.

Nachdem Ihre Bookmap eingerichtet wurde, verwenden Sie Native PDF , um die PDF-Ausgabe zu generieren. Es verarbeitet die Lesezeichenstruktur und Verweise, einschließlich des Inhaltsverzeichnisses und der Leselisten.

## Inhaltsverzeichnis-Design und seine Reihenfolge in PDF

Native PDF-Funktionen bieten eine praktische Methode zur Anpassung des Layouts und Designs Ihres Inhaltsverzeichnisses.

Sie können das Design über ein eigenes Seitenlayout für Inhaltsverzeichnis und Stile über layout.css steuern.

Die Bestellung von TOC und anderen Booklists in PDF basiert nur auf der Lesezeichenstruktur.

![toc](../assets/publishing/toc.png)


## Häufig gestellte Fragen

- ### Einbinden des Inhaltsverzeichnisses einer Ditamap in eine PDF

Ditamaps selbst verfügen nicht direkt über ein Inhaltsverzeichnis (TOC), wie es eine Lesekarte tut. Ditamaps spielen jedoch eine entscheidende Rolle bei der Definition der Struktur für Ihren Inhalt und tragen indirekt zum TOC-Generierungsprozess bei.

Wenn Sie Ditamap veröffentlichen, bietet Native PDF eine Funktion zum automatischen Generieren von TOC und Booklist . Sie können die Generierung von TOC in ditamap über die nativen PDF-Einstellungen aktivieren/deaktivieren.

![Aktiviert &quot;TOC deaktivieren&quot;](../assets/publishing/pageorder.png)

## Zusätzliche Ressourcen :

- [Dokumentation zum Layout nativer PDF-Designseiten](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Voraufgezeichnete native PDF-Grundlagen der Expertensitzung](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Post in der AEM Guides-Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) für alle Abfragen.



