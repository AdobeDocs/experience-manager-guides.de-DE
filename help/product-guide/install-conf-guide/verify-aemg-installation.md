---
title: Überprüfen der AEM Guides-Installation
description: Erfahren Sie, wie Sie die AEM Guides-Installation überprüfen
feature: Installation
role: Admin
level: Experienced
exl-id: 19cded6f-6545-42af-8511-7c32cf4ddf2d
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 5%
---
# Überprüfen der AEM Guides-Installation {#id213BD030FBE}

Nachdem Sie AEM Guides installiert haben, müssen Sie überprüfen, ob die Installation erfolgreich war oder nicht.

Die folgenden Registerkarten enthalten Anweisungen zum Überprüfen der AEM Guides-Installation basierend auf Ihrem Experience Manager Guides-Setup: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Führen Sie die folgenden Schritte aus, um die Installation zu überprüfen:

1. Greifen Sie auf die Developer Console Ihrer Cloud Service zu.

   Weitere Informationen zum Zugriff auf Developer Console finden Sie unter [Zugriff auf Developer Console](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=de) in der Dokumentation zu AEM.

1. Rufen Sie die Liste der OSGi-Bundles in AEM auf.

   Weitere Informationen zum Zugriff auf Bundles finden Sie unter [Bundles](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) in der AEM-Dokumentation.

1. Suchen Sie in der Liste der Bundles nach „fmdita“ und überprüfen Sie den Status.

   Der Status sollte für *erfolgreich bereitgestellte Bundles &quot;*&quot; anzeigen. Wenn eines der Bundles nicht den Status Aktiv hat, überprüfen Sie die AEM-Protokolle, um das Installationsproblem zu beheben.

>[!TAB On-Premise]

Führen Sie die folgenden Schritte aus, um die Installation zu überprüfen:

1. Melden Sie sich bei Ihrer AEM-Instanz an und navigieren Sie zur Seite AEM Web Console Bundles . Die Standard-URL für den Zugriff auf die Seite „Bundles“ lautet:

   ```http
   http://<server name>:<port>/system/console/bundles
   ```

   Eine Liste mit Bundles wird angezeigt.

1. Filtern Sie die Liste der Bundles, indem Sie fmdita in das Textfeld Filtern eingeben und die **Eingabetaste** drücken.

   Die Liste der Bundles wird gefiltert, um die von AEM Guides installierten Bundles anzuzeigen. Wenn die Installation erfolgreich war, haben alle installierten Bundles den **Status** von **Active**.

   Wenn eines der Bundles nicht den Status **Aktiv** aufweist, überprüfen Sie die AEM-Protokolle, um das Installationsproblem zu beheben.


>[!IMPORTANT]
>
> Es gibt eine Reihe von Empfehlungen zur Leistungsoptimierung, die Sie zur Verbesserung der Systemleistung in Betracht ziehen können. Weitere Informationen finden [&#x200B; unter „Empfehlungen &#x200B;](perf-optimization-on-prem.md#) Leistungsoptimierung“.

>[!ENDTABS]
