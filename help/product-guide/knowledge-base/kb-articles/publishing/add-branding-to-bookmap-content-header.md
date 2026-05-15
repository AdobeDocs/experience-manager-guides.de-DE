---
title: Hinzufügen von Unternehmens-Branding zur ersten Seite einer DITA PDF
description: Erzielen Sie das Unternehmens-Branding, indem Sie die Titelseite und die Kapitelseite integrieren und so sicherstellen, dass die Identität des Unternehmens oben im Inhalt klar angezeigt wird.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: ab452529-3c7f-4057-a0f6-212b9f52a99d
TQID: https://experienceleague.adobe.com/6CGRK2QWFZ6nIXmIAQZy3lX7t4KYP2-HeyqlVW2-7eE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 422
ht-degree: 0%

---

# Hinzufügen von Unternehmens-Branding zur ersten Seite einer DITA PDF

## Dieser Artikel behandelt Folgendes:

Erreichen des Unternehmens-Brandings durch die nahtlose Zusammenführung der FrontCover-Seite mit der Kapitelseite, um sicherzustellen, dass die Identität des Unternehmens oben im Inhalt gut sichtbar ist.

- [Einrichten von Inhalten](#set-up-your-content)
- [Nehmen Sie die erforderlichen Änderungen in der PDF-Vorlage vor](#create-necessary-changes-in-pdf-template)

**before:**

![Vor der Behebung des Brandings: Screenshot mit dem PDF-Layout mit vordefiniertem Branding](../assets/publishing/branding-image1.png)
<br>
<br>

**after:**

![Nach der Korrektur des Brandings: Screenshot mit dem PDF-Layout nach dem Branding](../assets/publishing/branding-image2.png)

## Einrichten von Inhalten

Um Inhalte im PDF-Format zu veröffentlichen, müssen Sie eine Ditamap oder eine Bookmap erstellen.

Bookmap-Beispielstruktur :

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

Beispielstruktur für Ditamap:

```
<map title="My map Title">

  <topicref href="topic1.dita" >
  </topicref>
  <topicref href="topic2.dita">
  </topicref>
  
</map>
```

Das FrontCover von PDF wird automatisch generiert, wenn Bookmap `<frontmatter>` enthält.


## Nehmen Sie die erforderlichen Änderungen in der PDF-Vorlage vor

In diesem Abschnitt werden wir unsere Vorlage einrichten. (Sie können die High-Tech-Vorlage verwenden oder duplizieren, um zu beginnen.)

### Richten Sie Ihre Vorlage ein :

- Navigieren Sie zu Ihrer nativen PDF-Vorlage.
- Öffnen Sie das Layout der Titelseite und bearbeiten Sie es.
- Fügen Sie hier Ihr Branding-Bild in `data-region="content"` hinzu.
- Fügen Sie bei Bedarf weitere erforderliche Änderungen in Ihrer Kapitelvorlage hinzu.
- Führen Sie nun je nach Inhalt die folgenden Schritte aus.


#### Wenn Sie Ditamap für die PDF-Generierung verwenden:

Beim Veröffentlichen einer DITAMAP bietet Native PDF die Möglichkeit, automatisch eine FrontCover-Seite zu generieren. Die Option zum Aktivieren oder Deaktivieren der Frontend-Seitenerstellung kann in der nativen PDF-Vorlage konfiguriert werden.

Zusammenführen:
- Gehen Sie zu den Einstellungen Ihrer nativen PDF-Vorlage > Seitenlayout-Reihenfolge
- Fusioniert nun FrontCover mit der nächsten Seite, d.h. Kapitel &amp; Themen.
  ![Zusammenführen von FrontCover und Chapter: Screenshot mit den nativen Einstellungen der PDF-Vorlage](../assets/publishing/branding-image3.png)
- Vorlage speichern, diese Vorlage für Voreinstellung auswählen und veröffentlichen!


#### Wenn Sie die Generierung von Bookmap für PDF verwenden

Bei einer Bookmap wird die Reihenfolge der Seitenlayoutreihenfolge durch die Struktur der Bookmap und nicht durch die Reihenfolge der Vorlage gesteuert.

Um dies für Bookmap zu erreichen, verwenden wir die JavaScript-Funktion von NativePDF.

- Fügen Sie im Ressourcenordner Ihrer Vorlage unter JavaScript Folgendes hinzu

```
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onAfterPagination(function () {
        var frontMatterWrappers = document.querySelectorAll('.rh-front-matter-wrapper');

        frontMatterWrappers.forEach(function(wrapper) {
            var contentDiv = wrapper.querySelector('div[data-region="content"]');
            var chapterBody = document.querySelector('.chapter-body');

            if (contentDiv && chapterBody) {
                chapterBody.insertBefore(contentDiv, chapterBody.firstChild);
            }

            wrapper.remove();
        });
    });
});
```

- Fügen Sie diese JavaScript in Ihre Kapitelvorlage ein.
  ![JavaScript in Kapitelvorlage einbeziehen: Screenshot, der den Eintrag in der PDF-Seitenlayoutvorlage zeigt](../assets/publishing/branding-image4.png)

- Aktivieren von JavaScript über die Option „Voreinstellung“
  ![JavaScript-Vorgabeneinstellung aktivieren: Screenshot mit Vorgabeneinstellung zum Aktivieren von JavaScript](../assets/publishing/branding-image5.png)

- Veröffentlichen!

## Anlagen :

- [Laden Sie das PDF-Beispielvorlagenpaket herunter, um die angewendeten Änderungen anzuzeigen.](../assets/publishing/NativePDF_DemoTemplate.zip)
- [Laden Sie das Beispielpaket für PDF-Vorgaben herunter, um die angewendeten Änderungen anzuzeigen.](../assets/publishing/Preset_Package.zip)


## Weitere Ressourcen:

- [Einbinden des Inhaltsverzeichnisses von DITA Bookmap in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Expertenvideo zu nativen PDF](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
