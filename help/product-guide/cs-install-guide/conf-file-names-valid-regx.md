---
title: Konfigurieren von RegX für gültige Dateinamenzeichen
description: Erfahren Sie, wie Sie RegX für gültige Dateinamenzeichen konfigurieren
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/fFZPer93bwekrR2a9mqGwLNm6CIpvGkuNn48xtExUv4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 0%

---

# Konfigurieren von RegX für gültige Dateinamenzeichen {#id214BD0550E8}

Ab AEM Guides Version 3.8 können Sie als Administrator eine Liste gültiger Sonderzeichen definieren, die in Dateinamen zulässig sind. In früheren Versionen durften Benutzende Dateinamen definieren, die Sonderzeichen wie `@`, `$`, `>` und mehr enthalten. Diese Sonderzeichen führten zu Problemen beim Öffnen von Themen über das DITA-Zuordnungs-Dashboard oder beim Klicken auf den Link des Themas im Inhaltsverzeichnis, was oft dazu führte, dass die Seite aufgrund von Sonderzeichen in der URL nicht geöffnet wurde.

Durch Verwendung der -Konfiguration, mit der Sie einen Regex für gültige Dateinamenzeichen definieren können, haben Sie die volle Kontrolle darüber, wie die Dateien intern im System benannt werden. Sie können eine Liste von Sonderzeichen definieren, die in den Dateinamen zulässig sind. Standardmäßig enthält die gültige Dateinamenkonfiguration &quot;`a-z A-Z 0-9 - _`&quot;. Beim Erstellen einer neuen Datei können Sie ein beliebiges Sonderzeichen im Titel der Datei haben, aber intern wird es im Dateinamen durch &quot;`-`&quot; ersetzt. Wenn Sie beispielsweise den Titel der Datei als „Einführung 1“ oder &quot;Introduction@1&quot; haben, würde der entsprechende Dateiname für beide Fälle „Einführung-1“ lauten.

Beachten Sie beim Definieren einer Liste gültiger Zeichen, dass diese Zeichen &quot;`*/:[\]|#%{}?&<>"/+`&quot; immer durch ein &quot;`-`&quot; ersetzt werden.

Wenn Sie die Liste der gültigen Sonderzeichen nicht konfigurieren, kann der Prozess der Dateierstellung zu unerwarteten Ergebnissen führen. Um solche Fehler zu vermeiden, wird dringend empfohlen, diese Konfigurationsänderung vorzunehmen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um Regex für gültige Dateinamenzeichen zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | Der Wert ist ein Regex-Muster. Sie muss drei einfache Zeichen enthalten und die Liste muss mit einem Bindestrich \(-\) beginnen.<br> **Standardwert**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Ähnlich wie bei der Liste der gültigen Dateinamenzeichen können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM Site-Ausgabe angeben. Weitere Informationen finden Sie unter [Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe](conf-file-names-valid-regx-aem-site-output.md#).

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
