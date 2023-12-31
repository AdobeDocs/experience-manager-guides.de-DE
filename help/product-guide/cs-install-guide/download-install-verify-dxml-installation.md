---
title: Installation AEM Guides überprüfen
description: Erfahren Sie, wie Sie die Installation AEM Guides überprüfen
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---

# Installation AEM Guides überprüfen {#id213BD030FBE}

Nach der Installation AEM Guides müssen Sie überprüfen, ob die Installation erfolgreich war oder nicht. Führen Sie die folgenden Schritte aus, um die Installation zu überprüfen:

1. Rufen Sie die Entwicklerkonsole Ihres Cloud Service auf.

   Weitere Informationen zum Zugriff auf die Developer Console finden Sie unter [Zugriff auf die Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=de) in AEM Dokumentation.

1. Rufen Sie die Liste der OSGi-Pakete in AEM auf.

   Weitere Informationen zum Zugriff auf Bundles finden Sie unter [Bundles](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) in AEM Dokumentation.

1. Suchen Sie in der Liste der Bundles nach &quot;format&quot;und überprüfen Sie den Status.

   Der Status sollte *Aktiv* für erfolgreich bereitgestellte Bundles. Wenn eines der Bundles keinen Status &quot;Aktiv&quot;aufweist, überprüfen Sie die AEM, um das Installationsproblem zu beheben.


**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)
