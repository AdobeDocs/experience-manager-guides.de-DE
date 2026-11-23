---
title: Versionshinweise | Versionshinweise zu Adobe Experience Manager Guides 5.2.0 Service Pack 4
description: Erfahren Sie mehr über den Upgrade-Prozess und Fehlerbehebungen in Version 5.2.0 Service Pack 4 von Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a232c8a03cda9b0ef7ae8114c3d901df5fb5bcb4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%
---
# Versionshinweise für Version 5.2.0 Service Pack 4 (November 2026)

Dieser Artikel enthält Informationen zu Upgrade-Anweisungen, zur Java SDK-Kompatibilität, zu behobenen Problemen und bekannten Problemen in Version 5.2.0 Service Pack 4 von Adobe Experience Manager Guides.

## Java SDK-Ressourcen

Verwenden Sie die folgenden Ressourcen, wenn Sie benutzerdefinierte Java-Plug-ins oder Integrationen mit Experience Manager Guides entwickeln. Stellen Sie sicher, dass die SDK-Version Ihrer installierten Experience Manager Guides-Version entspricht.

| Freigabe | Java SDK-Version | Maven Central | Java API-Referenz |
|---|---|---|----|
| 5.2.0 Service Pack 4 (UUID) | 5.2.2 | [AEM Guides SDK-API 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Weitere Informationen finden Sie unter [Konfigurieren und Verwenden der API-JAR-Datei aus dem Maven Central Repository](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/api-reference/introduction).

## Upgrade auf Version 5.2.0 Service Pack 4 von Experience Manager Guides

Erfahren Sie, wie Sie Experience Manager Guides Version 5.2.0 Service Pack 4 installieren.

>[!NOTE]
>
>Diese Version ist nur für AEM 6.5 LTS verfügbar. Das unterstützte Service Pack ist AEM 6.5 LTS Service Pack 2.

### Voraussetzungen

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 5.2.0 Service Pack 4 sicher, dass Sie Version 5.2.0 Service Pack 1 verwenden.

### Upgrade-Prozess für Version 5.2.0 Service Pack 4

1. Laden Sie das Experience Manager Guides-Paket Version 5.2.0 Service Pack 4 herunter.
1. Laden Sie mithilfe von Package Manager (`/crx/packmgr`) das Paket in Ihre Instanz hoch.
1. Installieren Sie das Paket . Überprüfen Sie dann, ob die `fmdita` Bundles in den Status **Aktiv** zurückgekehrt sind. Sie können den Bundle-Status unter `/system/console/bundles` überprüfen.
1. Löschen Sie den Browsercache.

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Wenn Sie ein Asset aus dem Explorer-Bedienfeld, das nicht aktualisiert wurde, nachdem ein anderer Autor dieses Asset verschoben hat, per Drag-and-Drop in eine Zuordnung ziehen, wird der Zuordnung ein beschädigter Verweis hinzugefügt. (GUIDES-57869)

### Asset-Management

- Wenn Sie ein vorhandenes Nicht-DITA-Asset, z. B. ein Bild, mit der Option **Vorhandene Dateien überschreiben** überschreiben, wird die neue Version für das hochgeladene Bild nicht erstellt. Daher enthält die mit der Baseline generierte Ausgabe das ältere Asset. (GUIDES-59287)

- Wenn ein Nicht-DITA-Asset, z. B. ein Bild, das von einer Nicht-UUID-Einrichtung zu einer UUID-Einrichtung migriert wurde, zurückgesetzt oder auf eine andere Version verzweigt wird, ändert sich seine UUUID. Vorhandene Verweise auf das Asset werden nicht mehr aufgelöst, und das Bild erscheint in den Themen, die darauf verweisen, beschädigt. (GUIDES-58414)

### Publishing

- Beim Veröffentlichen einer Karte während andere Karten exportiert werden, verwendet die Ausgabe zeitweise ein Bildformat mit niedrigerer Qualität anstelle des ursprünglichen Vektorbilds. (GUIDES-55221)

## Bekannte Probleme

Adobe hat das folgende bekannte Problem in Version 5.2.0 Service Pack 4 erkannt:

- Wenn Sie ein Element per Drag-and-Drop an eine ungültige Position ziehen, verschiebt der Editor es an die nächste gültige Position, an der die Referenz ihren Repository-Pfad beibehalten kann. Wenn Sie einen vorhandenen Verweis in einer DITA-Zuordnung durch Ziehen und Ablegen ersetzen, behält der neue Verweis möglicherweise seinen Repository-Pfad bei. (GUIDES-60688)