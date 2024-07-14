---
title: Hinzufügen von [!DNL Experience Manager Guides] zur [!DNL Experience Manager as a Cloud Service] Umgebung
description: Erfahren Sie, wie Sie  [!DNL AEM Guides] zur [!DNL AEM as a Cloud Service] Umgebung hinzufügen
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] as a Cloud Service Bereitstellung

Erfahren Sie, wie Sie Ihrer [!DNL Experience Manager as a Cloud Service]-Umgebung [!DNL Experience Manager Guides] hinzufügen.


>[!NOTE]
>
> Ab Version 2024.2.0 ist Experience Manager Guides nur noch als automatisiertes Add-on für Experience Manager as a Cloud Service verfügbar. Wenn Sie manuelle Bereitstellungen für Experience Manager Guides verwenden, entfernen Sie die Zeile &quot;`<module>dox.installer</module> from file dox/pom.xml`&quot;in Ihrer Cloud-Git-Codebasis, bevor Sie Experience Manager Guides für Ihr Programm aktivieren.

1. Melden Sie sich bei [!UICONTROL Cloud Manager] an.

1. Bearbeiten Sie das Programm, für das Sie [!DNL Experience Manager Guides] konfigurieren möchten.

1. Wechseln Sie zur Registerkarte **[!UICONTROL Lösungen und Add-ons]** .

1. Klicken Sie in der Tabelle **[!UICONTROL Lösungen und Add-ons]** auf **[!UICONTROL Assets]**.

1. Wählen Sie **[!UICONTROL Guides]** und dann **[!UICONTROL Speichern]** aus.

Sie haben Ihr Programm für die automatische Bereitstellung der Experience Manager Guides-Lösung erfolgreich konfiguriert.

![Konfigurieren der Experience Manager Guides-Lösung](assets/addon-configuration.png)

>[!NOTE]
>
>Um [!DNL Experience Manager Guides] in einer Umgebung unter dem integrierten Programm zu installieren, müssen Sie die mit der Umgebung verknüpfte Pipeline ausführen. Für die Installation von [!DNL Experience Manager Guides] ist keine zusätzliche Konfiguration in Ihrer CM-Git-Codebasis erforderlich.
