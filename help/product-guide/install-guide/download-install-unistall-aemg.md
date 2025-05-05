---
title: AEM Guides deinstallieren
description: Erfahren Sie, wie Sie AEM Guides deinstallieren
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# AEM Guides deinstallieren {#id21BHG0C0SXA}

Sie können AEM Guides mit dem CRX Package Manager deinstallieren. Während der Deinstallation wird der Inhalt des Repositorys auf den Schnappschuss zurückgesetzt, der unmittelbar vor der Installation des Pakets erstellt wurde.

Führen Sie die folgenden Schritte aus, um AEM Guides zu deinstallieren:

1. Melden Sie sich bei Ihrer AEM-Instanz an und navigieren Sie zum CRX Package Manager. Die Standard-URL für den Zugriff auf den Package Manager lautet:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Suchen Sie nach dem com.adobe.fmdita-Paket.
1. Klicken Sie auf das Paket, um es zu erweitern.
1. Klicken Sie auf **Mehr**, um das Dropdown-Menü zu öffnen.
1. Klicken Sie **Deinstallieren** und warten Sie, bis die Deinstallation abgeschlossen ist.
1. Wenn Sie dieses Paket nicht mehr benötigen, klicken Sie nach **Deinstallation** Pakets auf „Löschen“.

## Nach der Deinstallation

Führen Sie die folgenden Schritte aus, um die restlichen Dateien nach der Deinstallation zu bereinigen:

1. Bereinigen Sie den Skript-Cache mit:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. Der Cache kann wie folgt invalidiert werden:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Klicken Sie **Cache ungültig machen**.
1. Löschen Sie den Cache des Browsers.

**Übergeordnetes Thema:**&#x200B;[ Herunterladen und installieren](download-install.md)
