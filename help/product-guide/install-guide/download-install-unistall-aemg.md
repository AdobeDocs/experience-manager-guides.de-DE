---
title: AEM Guides deinstallieren
description: Erfahren Sie, wie Sie AEM Guides deinstallieren
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/W6cpFBqAnriNXNYqP6r-GZm7tJhPWnlSI53q33iduvE'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
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
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '147'
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

**Übergeordnetes Thema:**&#x200B;[&#x200B; Herunterladen und installieren](download-install.md)
