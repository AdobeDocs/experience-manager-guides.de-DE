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

AEM Guides generiert für jedes neue Dokument, das Sie erstellen, eine Dokument-ID. Wenn Sie beispielsweise eine DITA-Zuordnung erstellen, wird der Zuordnungs-ID eine ID wie `map.ditamap_random_digits` zugewiesen. Sie können auch Elemente definieren, für die automatisch eine ID generiert und zugewiesen wird.

AEM Guides bietet einfache Konfigurationseinstellungen, bei denen Sie die Elemente, für die eine ID automatisch generiert wird, und ein Muster für die ID definieren müssen. Standardmäßig sind einige Elemente wie `section`, `table`, `ul`, `ol` für die automatische Generierung von IDs konfiguriert. Sie können dieser Liste weitere Elemente hinzufügen, sodass AEM Guides jedes Mal, wenn diese Elemente in ein Dokument eingefügt werden, eine ID basierend auf dem angegebenen Muster generiert und zuweist

Führen Sie die folgenden Schritte aus, um -Elemente so zu konfigurieren, dass sie eine automatisch generierte ID haben:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Geben Sie in *XmlEditorConfig*-Einstellungen ein oder mehrere Elemente im Feld **IDs für Element-Tags automatisch generieren** an.

   >[!NOTE]
   >
   > Element-Tags sind die DITA-Elementnamen wie `body`, `title`, `codeblock` usw. Um mehrere Elemente anzugeben, trennen Sie Elementnamen durch ein Komma.

1. Geben Sie **Feld Muster für das Generieren** IDs ein Muster an, um eine ID zu generieren.

   Der Standardwert für dieses Feld ist auf `${elementName}_${id}` festgelegt. Der `${elementName}` wird durch den Namen des Elements ersetzt. Die Variable `${id}` generiert eine fortlaufende Nummer für das Element. Wenn Sie beispielsweise dem Absatzelement automatisch generierte IDs zuweisen, erhält der erste Absatz im Thema oder Dokument eine ID wie p\_1, der nächste Absatz erhält p\_2 usw. In einem anderen Dokument wird der ID-Generierungsprozess jedoch neu gestartet. Das bedeutet, dass in einem anderen Dokument IDs wie p\_1 und p\_2 Absatzelementen zugewiesen werden können.

   Wenn Ihr Dokument bereits IDs im angegebenen Muster enthält, werden diese IDs vom automatischen Generierungsprozess nicht neuen Elementen zugewiesen.

1. Klicken Sie auf **Speichern**.


**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
