---
title: Upgrade von AEM Guides für Cloud Service
description: Erfahren Sie, wie Sie AEM Guides aktualisieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: b416334318a83e882c32318bc4769d24268cdd1c
workflow-type: tm+mt
source-wordcount: '103'
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
> Weitere Informationen zur Verwendung der CI/CD-Pipeline finden Sie unter [Verwenden der CI/CD-Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html?lang=de).

## Löschen Sie den Browsercache.

Nach Abschluss des Aktualisierungsprozesses müssen alle Benutzer den Browsercache löschen, bevor sie die aktualisierte Version von AEM Guides verwenden können.
