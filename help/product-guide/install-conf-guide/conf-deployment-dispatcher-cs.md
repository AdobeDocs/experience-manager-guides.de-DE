---
title: Bereitstellung und Dispatcher-Konfiguration
description: Erfahren Sie mehr über die Bereitstellung und Dispatcher-Konfiguration in Experience Manager Guides as a Cloud Service
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: 657a42be-36e7-4657-83d5-e866f8e55f09
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
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
source-wordcount: '347'
ht-degree: 6%
---
# Bereitstellung und Dispatcher-Konfiguration

Dieser Artikel enthält Informationen zum Bereitstellen von Experience Manager Guides as a Cloud Service und Konfigurieren des Dispatchers.

## Bereitstellen von Experience Manager Guides as a Cloud Service

Sie können Experience Manager Guides zunächst über die Cloud Manager bereitstellen. Um das Modul bereitzustellen, befolgen Sie die unter [Bereitstellung von AEM Guides as a Cloud Service](../release-info/deploy-xml-on-aemaacs.md) erwähnten Anweisungen.

>[!NOTE]
>
> Ab Version 2024.2.0 ist Experience Manager Guides nur noch als automatisiertes Add-on für Experience Manager as a Cloud Service verfügbar. Wenn Sie die Version vom Dezember 2023 oder frühere Versionen verwenden, können Sie die Adobe Experience Manager Guides aus dem GitHub-Repository herunterladen und installieren. Wenn Sie manuelle Bereitstellungen für Experience Manager Guides verwenden, entfernen Sie die `<module>dox.installer</module> from file dox/pom.xml` in Ihrer Cloud Manager-Git-Codebasis, bevor Sie Experience Manager Guides für Ihr Programm aktivieren.

Führen Sie die folgenden Schritte aus, um das Experience Manager Guides-Modul bereitzustellen:

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


## Dispatcher konfigurieren

Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich. Weitere Informationen finden Sie unter [Dispatcher in der Cloud](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=de).

1. Informationen zum Migrieren der Dispatcher-Konfiguration von AMS zu Cloud Service finden Sie unter [Migrieren der Dispatcher-Konfiguration von AMS zu AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=de).
1. Weitere Informationen zum Konfigurieren des Dispatchers finden Sie unter [Konfigurieren von Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=de).

>[!NOTE]
>
> AEM as a Cloud Service unterstützt keinen Dispatcher für Autoreninstanzen.
