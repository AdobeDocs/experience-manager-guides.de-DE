---
title: Überprüfen der AEM Guides-Installation
description: Erfahren Sie, wie Sie die AEM Guides-Installation überprüfen
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/sniTYknUIyJH0D1moIL3olj3AeBT08kLH52Gba27sqs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 0%

---

# Überprüfen der AEM Guides-Installation {#id213BD030FBE}

Nachdem Sie AEM Guides installiert haben, müssen Sie überprüfen, ob die Installation erfolgreich war oder nicht. Führen Sie die folgenden Schritte aus, um den Installationsprozess zu überprüfen:

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
> Es gibt eine Reihe von Empfehlungen zur Leistungsoptimierung, die Sie zur Verbesserung der Systemleistung in Betracht ziehen können. Weitere Informationen finden [&#x200B; unter „Empfehlungen &#x200B;](download-install-recommend-perf-optimiz.md#) Leistungsoptimierung“.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Herunterladen und installieren](download-install.md)
