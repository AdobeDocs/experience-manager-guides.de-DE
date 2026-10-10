---
title: Upgrade von AEM Guides für Cloud Service
description: Erfahren Sie, wie Sie AEM Guides aktualisieren
feature: Installation
role: Admin
level: Experienced
exl-id: 9d48a7c4-384d-4ad4-a1d3-4c50d97e5d5b
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 2%
---
# Upgrade von AEM Guides für Cloud Service {#id213BD050YPH}

Führen Sie die folgenden Schritte für das Upgrade von AEM Guides durch:

1. Greifen Sie auf das Git-Repository Ihrer Cloud Manager zu.

1. Aktualisieren Sie die `dox/dox.installer/pom.xml`.

1. Aktualisieren Sie den Wert `dox.version` Variablen auf die von Adobe bereitgestellten Versionsdetails.

1. Übertragen Sie die Änderungen und führen Sie die Cloud Manager-Pipeline aus, um das aktualisierte Paket bereitzustellen.


>[!NOTE]
>
> Weitere Informationen zur Verwendung der CI/CD-Pipeline finden Sie unter [Verwenden der CI/CD-Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Löschen Sie den Browsercache.

Nach Abschluss des Aktualisierungsprozesses müssen alle Benutzer den Browsercache löschen, bevor sie die aktualisierte Version von AEM Guides verwenden können.
