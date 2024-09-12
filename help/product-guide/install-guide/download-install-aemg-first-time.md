---
title: AEM Guides zum ersten Mal herunterladen und installieren
description: Erfahren Sie, wie Sie AEM Guides zum ersten Mal herunterladen und installieren
exl-id: 830a4381-303c-419c-b87f-9563352a7eeb
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 8e43e76e22d1d8b7251c73f813e2e56f65633a5f
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# AEM Guides zum ersten Mal herunterladen und installieren {#id213BCL00KEV}

Führen Sie die folgenden Schritte aus, um AEM Guides zum ersten Mal auf einem Computer herunterzuladen und zu installieren:

>[!IMPORTANT]
>
> Wenn Sie Livefyre zusammen mit AEM Guides verwenden möchten, stellen Sie sicher, dass Sie die Livefyre-Versionen vor Version 3.0 installieren, bevor Sie AEM Guides installieren. Wenn Sie Livefyre Version 3.0 oder höher verwenden, gibt es keine solche Einschränkung.

1. Laden Sie AEM Guides vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) herunter.
   >[!NOTE]
   >
   >Stellen Sie vor der Installation von Experience Manager Guides sicher, dass Ihr System die [technischen Anforderungen](../install-guide/download-install-technical-requirements.md) erfüllt.
1. Melden Sie sich bei Ihrer AEM-Instanz an und navigieren Sie zum CRX Package Manager. Die Standard-URL für den Zugriff auf den Paketmanager lautet:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Der Package Manager verwaltet die Pakete in Ihrer lokalen AEM-Installation. Weitere Informationen zum Arbeiten mit Package Manager finden Sie unter [Arbeiten mit Paketen](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/package-manager.html) in AEM Dokumentation.

   ![](assets/package-manager.png){width="650" align="left"}

1. Um das AEM Guides-Paket hochzuladen, klicken Sie auf **Paket hochladen**.

1. Navigieren Sie im Dialogfeld Paket hochladen zur AEM Guides-Datei, die Sie in Schritt 1 heruntergeladen haben, und klicken Sie auf **OK**.

   Das Paket wird in Ihre AEM-Instanz hochgeladen.

1. Klicken Sie zum Installieren des Pakets auf **Installieren**.

   ![](assets/install-package.png){width="650" align="left"}

1. Klicken Sie im Dialogfeld &quot;Paket installieren&quot;auf **Installieren**.

1. Um mit AEM Guides zu beginnen, klicken Sie links oben im CRX Package Manager auf die Schaltfläche &quot;Startseite&quot;![](assets/home-button.png) .


>[!NOTE]
>
> Führen Sie den Installationsvorgang für alle Instanzen von AEM-Servern in Ihrer Einrichtung durch.

**Übergeordnetes Thema:**[ Herunterladen und Installieren](download-install.md)
