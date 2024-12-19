---
title: Anzeige von UUID-basierten Links konfigurieren
description: Erfahren Sie, wie Sie die Anzeige von UUID-basierten Links konfigurieren
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# Anzeige von UUID-basierten Links konfigurieren {#id2035G20M0QN}

Wenn Sie einen Link mit der Option Verweis einfügen oder Wiederverwenden von Inhalten einfügen im Web-Editor erstellen, wird der Link standardmäßig mit der UUID des referenzierten Inhalts erstellt. Die **Link**-Eigenschaft \(im Eigenschaftenbereich\) des referenzierten Inhalts kann so konfiguriert werden, dass der relative Dateipfad des referenzierten Inhalts oder der UUID angezeigt wird. Standardmäßig wird die UUID des referenzierten Inhalts im Bedienfeld Eigenschaften angezeigt.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um den relativen Pfad oder die UUID des referenzierten Inhalts im Web-Editor anzuzeigen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolescher Wert \(true/false\). Wenn Sie den relativen Pfad des verknüpften Inhalts anzeigen möchten, legen Sie diese Eigenschaft auf „false“ fest. <br> **Standardwert**: true |

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
