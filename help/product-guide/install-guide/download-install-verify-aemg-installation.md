---
title: Überprüfen der AEM Guides-Installation
description: Erfahren Sie, wie Sie die AEM Guides-Installation überprüfen
exl-id: 8e0afe18-5675-4c7e-b216-6de1a752bd01
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '165'
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
> Es gibt eine Reihe von Empfehlungen zur Leistungsoptimierung, die Sie zur Verbesserung der Systemleistung in Betracht ziehen können. Weitere Informationen finden Sie unter [Recommendations ](download-install-recommend-perf-optimiz.md#) Leistungsoptimierung.

**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)
