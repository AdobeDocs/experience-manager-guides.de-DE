---
title: Neue PDF-Engine aktivieren
description: Erfahren Sie, wie Sie die neue PDF-Engine in Experience Manager Guides aktivieren
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: f89becea89888f7dec81e18c9220dcabda8f4e7d
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 4%
---

# Konfigurieren der nativen PDF Engine v2

Die neue Publishing-Engine für Native PDF, d. h. _native PDF-Engine v2_, bietet aktualisierte PDF-Rendering-Funktionen und Fehlerbehebungen für _native PDF-Engine v1_-Probleme.

>[!BEGINTABS]
>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../install-conf-guide/download-install-config-override.md), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Standardwert: `v1` |

>[!TAB On-Premise]


Bei On-Premise-Bereitstellungen hängt die Verfügbarkeit von den AEM- und Java-Versionen ab.

Die _native PDF-Engine v2_ erfordert **Java 17 oder höher**.

- **AEM 6.5:** Die native PDF-Publishing-Engine v2 wird nicht unterstützt, da AEM 6.5 auf Java 8 ausgeführt wird.
- **AEM 6.5 LTS:** Native PDF Publishing Engine v2 ist standardmäßig aktiviert. Es ist keine spezielle Konfiguration notwendig.

Wenn Sie lieber zur _nativen PDF Engine v2_ mit AEM 6.5 LTS zurückkehren möchten, deinstallieren Sie das PDF Publisher-Paket:
`/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` aus dem CRX Package Manager.

>[!ENDTABS]

