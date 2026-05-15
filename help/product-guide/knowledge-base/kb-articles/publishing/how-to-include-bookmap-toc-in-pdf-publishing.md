---
title: Veröffentlichung von Inhaltsverzeichnissen (Table of Contents, TOC) mit NativePDF
description: Veröffentlichen des Inhaltsverzeichnisses und anderer Booklists für Ihre Datenbookmap mit NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
TQID: https://experienceleague.adobe.com/GyB4TpCF64rEGNgHVPKq4fUCBQsJjqh4jWA0CJC4A-0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 0%

---

# Generieren des Inhaltsverzeichnisses von Bookmap in PDF Publishing

## Einrichten der Lesekarte

`<toc>` Element einschließen:
Suchen Sie in dem Element `<frontmatter>`der Lesekarte“ das Element `<booklists>` .  Verschachteln Sie ein `<toc>` Element in `<booklists>` wie folgt:

```
<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>
```

Mit der DITA-Spezifikation können Sie das Inhaltsverzeichnis und die Leselisten auch im `<backmatter>` Abschnitt platzieren.


```
<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>
```

Beispielstruktur von Bookmap mit Inhaltsverzeichnis , Figurenliste und Tabellenliste in Frontmatter und Indexliste in Backmatter.

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

Nachdem Sie Ihre Lesekarte eingerichtet haben, verwenden Sie native PDF , um die PDF-Ausgabe zu generieren. Es verarbeitet die Bookmap-Struktur und Referenzen, einschließlich Inhaltsverzeichnis und Leselisten.

## Inhaltsverzeichnisdesign und -bestellung in PDF

Die native PDF-Funktion bietet eine praktische Methode zur Anpassung des Layouts und Designs Ihres Inhaltsverzeichnisses.

Sie können den Entwurf über ein separates Seiten-Layout für Inhaltsverzeichnisse und Stile über layout.css steuern.

Das Inhaltsverzeichnis und die Reihenfolge anderer Booklists in PDF basieren nur auf der Bookmap-Struktur.

![Inhaltsverzeichnis](../assets/publishing/toc.png)


## Häufig gestellte Fragen

### Einbinden des Inhaltsverzeichnisses einer Ditamap in eine PDF

Ditamaps selbst haben kein direktes Inhaltsverzeichnis (Table of Contents, TOC) wie eine Bookmap. Allerdings spielen Diagramme eine entscheidende Rolle bei der Definition der Struktur für Ihre Inhalte und tragen indirekt zum Generierungsprozess des Inhaltsverzeichnisses bei.

Wenn Sie Ditamap veröffentlichen, bietet Native PDF Funktionen zum automatischen Generieren von Inhaltsverzeichnissen und Leselisten . Sie können die Generierung von Inhaltsverzeichnissen in Ditamap in den nativen Einstellungen von PDF aktivieren/deaktivieren.

![Inhaltsverzeichnis deaktivieren](../assets/publishing/pageorder.png)

## Zusätzliche Ressourcen :

- [Native Dokumentation zum Seitenlayout des PDF-Designs](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Native aufgezeichnete Expertensitzung von PDF Essentials](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

Posten Sie bei der AEM Guides Community [Forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation?profile.language=de) für alle Fragen.



