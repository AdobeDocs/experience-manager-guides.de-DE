---
title: Hinzufügen von [!DNL Experience Manager Guides] auf [!DNL Experience Manager as a Cloud Service] Umgebung
description: Erfahren Sie, wie Sie [!DNL AEM Guides] auf [!DNL AEM as a Cloud Service] Umgebung
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
feature: Installation
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# [!DNL Adobe Experience Manager Guides] as a Cloud Service Implementierung

Erfahren Sie, wie Sie [!DNL Experience Manager Guides] auf [!DNL Experience Manager as a Cloud Service] Umgebung.


>[!NOTE]
>
> Ab Version 2024.2.0 sind Experience Manager-Handbücher nur noch als automatisiertes Add-on für Experience Manager as a Cloud Service verfügbar. Wenn Sie manuelle Bereitstellungen für Experience Manager-Handbücher verwenden, entfernen Sie die Zeile `<module>dox.installer</module> from file dox/pom.xml` in Ihrer Cloud Git-Codebase verwalten, bevor Sie Experience Manager-Handbücher für Ihr Programm aktivieren.

1. Anmelden bei [!UICONTROL Cloud Manager].

1. Bearbeiten Sie das Programm, für das Sie konfigurieren möchten [!DNL Experience Manager Guides].

1. Wechseln zu **[!UICONTROL Lösungen und Add-ons]** Registerkarte.

1. Im **[!UICONTROL Lösungen und Add-ons]** Tabelle, auf **[!UICONTROL Assets]**.

1. Auswählen **[!UICONTROL Handbücher]** und wählen **[!UICONTROL Speichern]**.

Sie haben Ihr Programm erfolgreich für die automatische Bereitstellung der Experience Manager Guides-Lösung konfiguriert.

![Konfigurieren der Experience Manager Guides-Lösung](assets/addon-configuration.png)

>[!NOTE]
>
>Installieren [!DNL Experience Manager Guides] in jeder Umgebung des integrierten Programms müssen Sie die mit der Umgebung verknüpfte Pipeline ausführen. Für die Installation von CM-Git-Codebase ist keine zusätzliche Konfiguration erforderlich [!DNL Experience Manager Guides].
