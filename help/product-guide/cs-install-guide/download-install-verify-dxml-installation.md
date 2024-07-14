---
title: Überprüfen der AEM Guides-Installation
description: Erfahren Sie, wie Sie die Installation von AEM Guides überprüfen
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Überprüfen der AEM Guides-Installation {#id213BD030FBE}

Nachdem Sie AEM Guides installiert haben, müssen Sie überprüfen, ob die Installation erfolgreich war oder nicht. Führen Sie die folgenden Schritte aus, um die Installation zu überprüfen:

1. Greifen Sie auf die Developer Console Ihres Cloud Service zu.

   Weitere Informationen zum Zugriff auf Developer Console finden Sie unter [Zugriff auf Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=de) in AEM Dokumentation.

1. Rufen Sie die Liste der OSGi-Pakete in AEM auf.

   Weitere Informationen zum Zugriff auf Bundles finden Sie unter [Bundles](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) in AEM Dokumentation.

1. Suchen Sie in der Liste der Bundles nach &quot;format&quot;und überprüfen Sie den Status.

   Der Status sollte für erfolgreich bereitgestellte Bundles *Aktiv* anzeigen. Wenn eines der Bundles keinen Status &quot;Aktiv&quot;aufweist, überprüfen Sie die AEM, um das Installationsproblem zu beheben.


**Übergeordnetes Thema:**[ Herunterladen und Installieren](download-install.md)
