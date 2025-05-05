---
title: Element-IDs automatisch generieren
description: Erfahren Sie, wie Sie Element-IDs automatisch generieren
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Element-IDs automatisch generieren {#id20CIL40016I}

AEM Guides generiert für jedes neue Dokument, das Sie erstellen, eine Dokument-ID. Wenn Sie beispielsweise eine DITA-Zuordnung erstellen, wird der Zuordnungs-ID eine ID wie `map.ditamap_random_digits` zugewiesen. Sie können auch Elemente definieren, für die automatisch eine ID generiert und zugewiesen wird.

AEM Guides bietet einfache Konfigurationseinstellungen, bei denen Sie die Elemente, für die eine ID automatisch generiert wird, und ein Muster für die ID definieren müssen. Standardmäßig sind einige Elemente wie `section`, `table`, `ul`, `ol` für die automatische Generierung von IDs konfiguriert. Sie können dieser Liste weitere Elemente hinzufügen, sodass AEM Guides jedes Mal, wenn diese Elemente in ein Dokument eingefügt werden, eine ID basierend auf dem angegebenen Muster generiert und zuweist

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die automatisch generierten Element-IDs zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Geben Sie eine kommagetrennte Liste von Elementen an. <br> **Standardwert**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Um ein Muster für eine automatisch generierte ID zu konfigurieren, erstellen Sie eine Konfigurationsdatei mit den folgenden Eigenschaften:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | Der Standardwert für dieses Feld ist auf `${elementName}_${id}` festgelegt. Der `${elementName}` wird durch den Namen des Elements ersetzt. Die Variable `${id}` generiert eine fortlaufende Nummer für das Element. Wenn Sie beispielsweise dem Absatzelement automatisch generierte IDs zuweisen, erhält der erste Absatz im Thema oder Dokument eine ID wie p\_1, der nächste Absatz erhält p\_2 usw. In einem anderen Dokument wird der ID-Generierungsprozess jedoch neu gestartet. Das bedeutet, dass in einem anderen Dokument IDs wie p\_1 und p\_2 Absatzelementen zugewiesen werden können. **Standardwert**: ``${elementName}_${id}`` |

**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
