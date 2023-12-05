---
title: AEM deinstallieren
description: Erfahren Sie, wie Sie AEM deinstallieren.
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# AEM deinstallieren {#id21BHG0C0SXA}

Sie können AEM Handbücher mit dem CRX Package Manager deinstallieren. Während der Deinstallation werden die Inhalte des Repositorys auf den Schnappschuss zurückgesetzt, der unmittelbar vor der Installation des Pakets erstellt wurde.

Führen Sie die folgenden Schritte aus, um AEM Handbücher zu deinstallieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an und navigieren Sie zum CRX Package Manager. Die Standard-URL für den Zugriff auf den Paketmanager lautet:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Suchen Sie nach dem com.adobe.fmdita -Paket.
1. Klicken Sie auf das Paket, um es zu erweitern.
1. Klicks **Mehr** , um das Dropdown-Menü zu öffnen.
1. Klicks **Deinstallieren** und warten Sie, bis die Deinstallation abgeschlossen ist.
1. Wenn Sie dieses Paket nicht mehr benötigen, klicken Sie auf **Löschen** nach der Deinstallation des Pakets.

## Nach der Deinstallation

Führen Sie die folgenden Schritte aus, um die Restdateien nach der Deinstallation zu bereinigen:

1. Reinigen Sie den Skript-Cache mit:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Sie können den Cache wie folgt invalidieren:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Klicks **Ungültiger Cache**.
1. Bereinigen Sie den Cache des Browsers.

**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)
