---
title: Element-IDs automatisch generieren
description: Erfahren Sie, wie Sie Element-IDs automatisch generieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: c3c59eb3-a00a-46db-a264-db44d5cd4943
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 1%

---

# Element-IDs automatisch generieren {#id20CIL40016I}

AEM Guides generiert für jedes neue Dokument, das Sie erstellen, eine Dokument-ID. Wenn Sie beispielsweise eine DITA-Zuordnung erstellen, wird der Zuordnungs-ID eine ID wie `map.ditamap_random_digits` zugewiesen. Sie können auch Elemente definieren, für die automatisch eine ID generiert und zugewiesen wird.

AEM Guides bietet einfache Konfigurationseinstellungen, bei denen Sie die Elemente, für die eine ID automatisch generiert wird, und ein Muster für die ID definieren müssen. Standardmäßig sind einige Elemente wie `section`, `table`, `ul`, `ol` für die automatische Generierung von IDs konfiguriert. Sie können dieser Liste weitere Elemente hinzufügen, sodass AEM Guides jedes Mal, wenn diese Elemente in ein Dokument eingefügt werden, eine ID basierend auf dem angegebenen Muster generiert und zuweist.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren von -Elementen für eine automatisch generierte ID basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die automatisch generierten Element-IDs zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Geben Sie eine kommagetrennte Liste von Elementen an. <br> **Standardwert**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Um ein Muster für eine automatisch generierte ID zu konfigurieren, erstellen Sie eine Konfigurationsdatei mit den folgenden Eigenschaften:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | Der Standardwert für dieses Feld ist auf `${elementName}_${id}` festgelegt. Der `${elementName}` wird durch den Namen des Elements ersetzt. Die Variable `${id}` generiert eine fortlaufende Nummer für das Element. Wenn Sie beispielsweise dem Absatzelement automatisch generierte IDs zuweisen, erhält der erste Absatz im Thema oder Dokument eine ID wie p\_1, der nächste Absatz erhält p\_2 usw. In einem anderen Dokument wird der ID-Generierungsprozess jedoch neu gestartet. Das bedeutet, dass in einem anderen Dokument IDs wie p\_1 und p\_2 Absatzelementen zugewiesen werden können. **Standardwert**: ``${elementName}_${id}`` |

>[!TAB On-Premise]

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

>[!ENDTABS]

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
