---
title: Konfigurieren des Anhang-Renderings für Zuordnungsreferenzen in der nativen PDF-Ausgabe
description: Erfahren Sie, wie Sie Experience Manager Guides so konfigurieren, dass Themen, die unter einer Unterzuordnung innerhalb eines Anhangs hinzugefügt wurden, als Anhang in der nativen PDF-Ausgabe gerendert werden.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 63ae0f947d50646bed34cd815db6b9fb585fc015
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%
---

# Konfigurieren des Anhang-Renderings für Zuordnungsreferenzen in der nativen PDF-Ausgabe

In der nativen PDF-Ausgabe können Themen, auf die in einer Unterzuordnung innerhalb eines `<appendix>` verwiesen wird, als Kapitel anstatt als Anhänge gerendert werden. Standardmäßig klassifiziert Experience Manager Guides Zuordnungsverweise nach Elementnamen, und diese Informationen gehen verloren, sobald die Zuordnungen bei der Verarbeitung reduziert werden.

Verwenden Sie diese Einstellung, um Zuordnungsverweise stattdessen mit dem von DITA-OT generierten `class`-Attribut zu klassifizieren. Themen in einer Anhang-Unterzuordnung werden dann als Anhänge gerendert.

>[!NOTE]
>
>Diese Einstellung ändert die Art und Weise, wie Zuordnungsreferenzen klassifiziert werden. Sie ist standardmäßig deaktiviert. Aktivieren Sie sie nur, wenn Ihr Inhalt Themen in einer Unterzuordnung innerhalb eines `<appendix>` platziert und Sie sie als Kapitel in der nativen PDF-Ausgabe gerendert sehen.

## Verwendung dieser Konfiguration

Betrachten wir das folgende Beispiel einer Buchzuordnung:

- Ein `<appendix>`-Element verweist direkt auf Themen. Diese Themen werden in der generierten PDF als Anhänge gerendert.

  ```XML
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix href="topics/appendix-reference-tables.dita">
    </appendix>
    <appendix href="topics/appendix-troubleshooting.dita">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>`
  ```

- Ein anderes `<appendix>`-Element verweist auf eine Unterzuordnung, und die Unterzuordnung verweist auf Themen mit `<topicref>`.

  ```xml
  <booktitle>
      <mainbooktitle>Product Guide</mainbooktitle>
    </booktitle>
    <frontmatter>
      <booklists>
        <toc/>
        <tablelist/>
      </booklists>
      <preface href="topics/preface.dita">
      </preface>
    </frontmatter>
    <chapter class="foo" href="topics/getting-started.dita">
    </chapter>  
    <appendix format="ditamap" href="submap-for-appendix.ditamap" type="map">
    </appendix>
    <backmatter>
      <booklists>
        <indexlist/>
      </booklists>
    </backmatter>
  </bookmap>
  ```

  Die submap-for-Appendix:

  ```xml
  <map id="GUID-cc306264-825c-455e-89db-d27af9197a2f">
    <title>submap-for-appendix</title>
    <topicref href="topics/appendix-reference-tables.dita" type="reference">
    </topicref>
    <topicref href="topics/appendix-troubleshooting.dita" type="topic">
    </topicref>
  </map>
  ```

Ohne diese Konfiguration werden Themen aus dem ersten Anhang als Anhänge gerendert, Themen aus der Unterzuordnung jedoch als Kapitel. Nur die Themen werden veröffentlicht. Die Unterzuordnung selbst wird für die Hierarchie verwendet und wird nicht in der Ausgabe angezeigt.

## Konfigurieren der Einstellung

Im Folgenden finden Sie Anweisungen zum Konfigurieren dieser Einstellung:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../install-conf-guide/download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

2. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   | --------------------------------------- | -------------------------------- | ----------------------------- |
   | `com.adobe.fmdita.config.ConfigManager` | `guides.publish.config` | &lbrace;USE_DITA_OT_GENERATED_CLASS“: {false} |

3. Legen Sie den Wert auf `true` fest, um die Einstellung zu aktivieren, und stellen Sie die Konfiguration mithilfe von Cloud Manager bereit.