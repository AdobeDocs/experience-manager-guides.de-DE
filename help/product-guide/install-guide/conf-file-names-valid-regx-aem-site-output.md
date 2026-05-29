---
title: Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe
description: Erfahren Sie, wie Sie gültige Dateinamen für die AEM Site-Ausgabe konfigurieren
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vGe4--XJ9VL5q74J7hVFCmD0vrBRnUkBAdZDCFcUxeU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 179e9016b12edb14c09ce9352a318e06a4fc628a
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 0%

---

# Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe {#id214GK0X0KXA}

Ähnlich wie bei der Liste der gültigen Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM Site-Ausgabe konfigurieren. Zu den bekannten Zeichen, die in einer URL nicht zulässig sind, zählen: `<>` `@$`. Diese Zeichen sind so konfiguriert, dass sie automatisch in einen Unterstrich „_“ konvertiert werden, wenn sie beim Generieren von Ausgabedateinamen der AEM-Site gefunden werden. Die Konfiguration, mit der Sie gültige Zeichen in der AEM-Site-Ausgabe festlegen können, ist im `com.adobe.fmdita.common.SanitizeNodeNameImpl`-Bundle vorhanden. **Legen Sie die Einstellung Nicht zulässiger Zeichensatz für die Veröffentlichung in AEM Sites fest** um Zeichen einzuschließen, die Sie in den Ausgabedateinamen der AEM-Site durch einen Unterstrich ersetzen möchten.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
