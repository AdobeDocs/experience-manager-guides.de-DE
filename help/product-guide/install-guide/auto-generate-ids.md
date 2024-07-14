---
title: Element-IDs automatisch generieren
description: Erfahren Sie, wie Sie Element-IDs automatisch generieren
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Element-IDs automatisch generieren {#id20CIL40016I}

AEM Guides generiert eine Dokument-ID für jedes neue Dokument, das Sie erstellen. Wenn Sie beispielsweise eine DITA-Zuordnung erstellen, wird der ID der Zuordnung eine ID wie `map.ditamap_random_digits` zugewiesen. Sie können auch Elemente definieren, für die automatisch eine ID generiert und zugewiesen wird.

AEM Guides bietet einfache Konfigurationseinstellungen, bei denen Sie die Elemente definieren müssen, für die eine ID automatisch generiert wird, sowie ein Muster für die ID. Standardmäßig sind einige Elemente wie `section`, `table`, `ul`, `ol` für die automatische Generierung der ID konfiguriert. Sie können weitere Elemente zu dieser Liste hinzufügen, sodass AEM Guides bei jedem Einfügen dieser Elemente in ein Dokument eine Kennung generiert und zuweist, die auf dem angegebenen Muster basiert

Führen Sie die folgenden Schritte aus, um Elemente so zu konfigurieren, dass sie eine automatisch generierte ID aufweisen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Geben Sie in den Einstellungen *XmlEditorConfig* ein oder mehrere Elemente im Feld **IDs für Element-Tags automatisch generieren** an.

   >[!NOTE]
   >
   > Element-Tags sind die DITA-Elementnamen wie `body`, `title`, `codeblock` usw. Um mehrere Elemente anzugeben, trennen Sie Elementnamen durch ein Komma.

1. Geben Sie im Feld **Muster für das Generieren von IDs** ein Muster zum Generieren einer ID an.

   Der Standardwert für dieses Feld ist auf `${elementName}_${id}` festgelegt. Der Wert `${elementName}` wird durch den Namen des Elements ersetzt. Die Variable `${id}` generiert eine sequenzielle Zahl für das Element. Wenn Sie beispielsweise das Absatzelement mit automatisch generierten IDs zuweisen, erhält der erste Absatz im Thema oder Dokument eine ID wie p\_1, der nächste Absatz erhält p\_2 usw. In einem anderen Dokument wird der ID-Generierungsprozess jedoch neu gestartet. Das bedeutet, dass in einem anderen Dokument IDs wie p\_1 und p\_2 Absatzelementen zugewiesen werden können.

   Wenn Ihr Dokument bereits IDs im angegebenen Muster enthält, weist der Prozess der automatischen Generierung diese IDs neuen Elementen nicht zu.

1. Klicken Sie auf **Speichern**.


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
