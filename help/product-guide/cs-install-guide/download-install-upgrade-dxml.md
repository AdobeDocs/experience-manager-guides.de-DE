---
title: AEM Guides aktualisieren
description: Erfahren Sie, wie Sie AEM Guides aktualisieren
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/jGMljbRp60Wst7hVLeanMTLHY79Yhqo7yeUCCsLXx3k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 114
ht-degree: 2%

---

# AEM Guides aktualisieren {#id213BD050YPH}

1. Greifen Sie auf das Git-Repository Ihrer Cloud Manager zu.

1. Aktualisieren Sie die Datei dox/dox.installer/pom.xml.

1. Aktualisieren Sie den Wert der Variablen dox.version auf die von Adobe bereitgestellten Versionsdetails.

1. Übertragen Sie die Änderungen und führen Sie die Cloud Manager-Pipeline aus, um das aktualisierte Paket bereitzustellen.


>[!NOTE]
>
> Weitere Informationen zur Verwendung der CI/CD-Pipeline finden Sie unter [Verwenden der CI/CD-Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Löschen Sie den Browsercache.

Nach Abschluss des Aktualisierungsprozesses müssen alle Benutzer den Browsercache löschen, bevor sie die aktualisierte Version von AEM Guides verwenden können.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Herunterladen und installieren](download-install.md)
