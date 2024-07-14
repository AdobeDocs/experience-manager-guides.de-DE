---
title: Gültige Dateinamen für AEM Site-Ausgabe konfigurieren
description: Erfahren Sie, wie Sie gültige Dateinamen für AEM Site-Ausgabe konfigurieren.
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Gültige Dateinamen für AEM Site-Ausgabe konfigurieren {#id214GK0X0KXA}

Ähnlich wie bei der Liste gültiger Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für AEM Site-Ausgabe konfigurieren. Einige der bekannten Zeichen, die in einer URL nicht zulässig sind, sind: ```'<>`@$```. Diese Zeichen werden so konfiguriert, dass sie automatisch in einen Unterstrich (_) umgewandelt werden, wenn sie beim Generieren AEM Site-Ausgabedateinamen gefunden werden. Die Konfiguration, mit der Sie gültige Zeichen in AEM Site-Ausgabe festlegen können, ist im Bundle `com.adobe.fmdita.common.SanitizeNodeNameImpl` vorhanden. **Setzen Sie die Einstellung &quot;Unzulässiger Zeichensatz für Veröffentlichung in AEM Sites**&quot;so, dass Zeichen, die Sie durch einen Unterstrich ersetzen möchten, in die Namen der Ausgabedateien der AEM Site aufgenommen werden.

**Übergeordnetes Thema:**[ Dateinamen konfigurieren](conf-file-names.md)
