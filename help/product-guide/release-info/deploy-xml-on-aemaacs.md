---
title: 'Hinzufügen von  [!DNL Experience Manager Guides]  zu Ihrer  [!DNL Experience Manager as a Cloud Service] '
description: Erfahren Sie, wie Sie  [!DNL AEM Guides]  Ihrer Umgebung  [!DNL AEM as a Cloud Service] .
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] as a Cloud Service-Bereitstellung

Erfahren Sie, wie Sie [!DNL Experience Manager Guides] zu Ihrer [!DNL Experience Manager as a Cloud Service] hinzufügen.


>[!NOTE]
>
> Ab Version 2024.2.0 ist Experience Manager Guides nur noch als automatisiertes Add-on für Experience Manager as a Cloud Service verfügbar. Wenn Sie manuelle Bereitstellungen für Experience Manager Guides verwenden, entfernen Sie die `<module>dox.installer</module> from file dox/pom.xml` in Ihrer Cloud Manager-Git-Codebasis, bevor Sie Experience Manager Guides für Ihr Programm aktivieren.

1. Bei [!UICONTROL Cloud Manager anmelden].

1. Bearbeiten Sie das Programm, für das Sie [!DNL Experience Manager Guides] konfigurieren möchten.

1. Wechseln Sie zur Registerkarte **[!UICONTROL Lösungen und Add-ons]**.

1. Klicken Sie in **[!UICONTROL Tabelle „Lösungen und Add]** ons“ auf **[!UICONTROL Assets]**.

1. Wählen Sie **[!UICONTROL Guides]** und klicken Sie auf **[!UICONTROL Speichern]**.

Sie haben Ihr Programm erfolgreich für die automatische Bereitstellung der Experience Manager Guides-Lösung konfiguriert.

![Konfigurieren der Experience Manager Guides-Lösung](assets/addon-configuration.png)

>[!NOTE]
>
>Um [!DNL Experience Manager Guides] in einer beliebigen Umgebung unter dem integrierten Programm zu installieren, müssen Sie die mit der Umgebung verknüpfte Pipeline ausführen. Für die Installation von [!DNL Experience Manager Guides] ist in Ihrer CM-Git-Codebasis keine zusätzliche Konfiguration erforderlich.
