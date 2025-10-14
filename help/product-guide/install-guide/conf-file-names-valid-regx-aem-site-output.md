---
title: Konfigurieren gültiger Dateinamen für die AEM-Site-Ausgabe
description: Erfahren Sie, wie Sie gültige Dateinamen für die AEM-Site-Ausgabe konfigurieren
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---

# Konfigurieren gültiger Dateinamen für die AEM-Site-Ausgabe {#id214GK0X0KXA}

Ähnlich wie bei der Liste gültiger Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM-Site-Ausgabe konfigurieren. Zu den bekannten Zeichen, die in einer URL nicht zulässig sind, zählen: ```'<>`@$```. Diese Zeichen werden so konfiguriert, dass sie automatisch in einen Unterstrich „_“ konvertiert werden, wenn sie beim Generieren von AEM Site-Ausgabedateinamen gefunden werden. Die Konfiguration, mit der Sie gültige Zeichen in der AEM-Site-Ausgabe festlegen können, ist im `com.adobe.fmdita.common.SanitizeNodeNameImpl`-Bundle vorhanden. **Legen Sie die Einstellung Nicht zulässiger Zeichensatz für die Veröffentlichung in AEM Sites** fest, um Zeichen einzuschließen, die Sie in den Ausgabedateinamen der AEM-Site durch einen Unterstrich ersetzen möchten.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
