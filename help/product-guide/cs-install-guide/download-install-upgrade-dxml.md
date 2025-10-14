---
title: AEM Guides aktualisieren
description: Erfahren Sie, wie Sie AEM Guides aktualisieren
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# AEM Guides aktualisieren {#id213BD050YPH}

1. Greifen Sie auf das Git-Repository Ihrer Cloud Manager zu.

1. Aktualisieren Sie die Datei dox/dox.installer/pom.xml.

1. Aktualisieren Sie den Wert der Variablen dox.version auf die von Adobe bereitgestellten Versionsdetails.

1. Übertragen Sie die Änderungen und führen Sie die Cloud Manager-Pipeline aus, um das aktualisierte Paket bereitzustellen.


>[!NOTE]
>
> Weitere Informationen zur Verwendung der CI/CD-Pipeline finden Sie unter [Verwenden der CI/CD-Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html?lang=de).

## Browser-Cache löschen

Nach Abschluss des Aktualisierungsprozesses müssen alle Benutzer den Browsercache löschen, bevor sie die aktualisierte Version von AEM Guides verwenden können.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Herunterladen und installieren](download-install.md)
