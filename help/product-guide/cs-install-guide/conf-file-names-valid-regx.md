---
title: Konfigurieren von Regx für gültige Dateinamenzeichen
description: Erfahren Sie, wie Sie Regx für gültige Dateinamenzeichen konfigurieren.
exl-id: 05e9ca3c-28ff-4f82-8061-3d20307890ff
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Konfigurieren von Regx für gültige Dateinamenzeichen {#id214BD0550E8}

Ab AEM Guides-Version 3.8 können Sie als Administrator eine Liste gültiger Sonderzeichen definieren, die in Dateinamen zulässig sind. In früheren Versionen konnten Benutzer Dateinamen mit Sonderzeichen wie `@`, `$`, `>` und mehr definieren. Diese Sonderzeichen führten zu Problemen beim Öffnen von Themen über das DITA-Map-Dashboard oder beim Klicken auf den Themenlink im Inhaltsverzeichnis, was häufig dazu führte, dass die Seite aufgrund von Sonderzeichen in der URL nicht geöffnet wurde.

Mit der Konfiguration, die es Ihnen ermöglicht, eine REGX für gültige Dateinamenzeichen zu definieren, haben Sie vollständige Kontrolle darüber, wie die Dateien intern im System benannt werden. Sie können eine Liste von Sonderzeichen definieren, die in Dateinamen zulässig sind. Standardmäßig enthält die gültige Dateinamenkonfiguration &quot;`a-z A-Z 0-9 - _`&quot;. Beim Erstellen einer neuen Datei können Sie beliebige Sonderzeichen im Dateinamen haben, diese werden jedoch intern im Dateinamen durch &quot;`-`&quot; ersetzt. Beispielsweise können Sie den Titel der Datei als &quot;Einführung 1&quot;oder &quot;Introduction@1&quot;festlegen, wobei der entsprechende Dateiname, der für beide Fälle generiert wurde, &quot;Einführung-1&quot;lautet.

Beachten Sie bei der Definition einer Liste gültiger Zeichen, dass diese Zeichen &quot;`*/:[\]|#%{}?&<>"/+`&quot; immer durch &quot;`-`&quot; ersetzt werden.

Wenn Sie die Liste der gültigen Sonderzeichen nicht konfigurieren, kann der Dateierstellungsprozess zu unerwarteten Ergebnissen führen. Um solche Fehler zu vermeiden, wird dringend empfohlen, diese Konfiguration zu ändern.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um Regex für gültige Dateinamenzeichen zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | Der Wert ist ein Regex-Muster. Er muss drei grundlegende Zeichen enthalten und die Liste muss mit einem Bindestrich \(-\) beginnen.<br> **Standardwert**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Ähnlich wie bei der Liste gültiger Dateinamenzeichen können Sie auch eine Liste gültiger Dateinamenzeichen für AEM Site-Ausgabe angeben. Weitere Informationen finden Sie unter [Gültige Dateinamen für AEM Site-Ausgabe konfigurieren](conf-file-names-valid-regx-aem-site-output.md#).

**Übergeordnetes Thema:**[ Dateinamen konfigurieren](conf-file-names.md)
