---
title: Überprüfen der AEM Guides-Installation
description: Erfahren Sie, wie Sie die AEM Guides-Installation überprüfen
feature: Installation
role: Admin
level: Experienced
exl-id: 19cded6f-6545-42af-8511-7c32cf4ddf2d
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
> Es gibt eine Reihe von Empfehlungen zur Leistungsoptimierung, die Sie zur Verbesserung der Systemleistung in Betracht ziehen können. Weitere Informationen finden [ unter „Empfehlungen ](perf-optimization-on-prem.md#) Leistungsoptimierung“.

>[!ENDTABS]
