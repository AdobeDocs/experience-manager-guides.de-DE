---
title: Versionshinweise | Versionshinweise für die Version 2026.11.0 Service Pack 1 | AEM Guides
description: Erfahren Sie mehr über die Fehlerbehebungen, bekannten Probleme und die Java-SDK-Kompatibilität für die Version 2026.11.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e21e39b2acf48c4115101ab806e97b45844fa191
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%
---
# Versionshinweise für die Version 2026.11.0 Service Pack 1 (November 2026)

Dieser Artikel enthält Informationen zu den behobenen Problemen, zur Java SDK-Kompatibilität und zu bekannten Problemen in der Version 2026.11.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service.

## Java SDK-Kompatibilität

Verwenden Sie die folgenden Ressourcen, wenn Sie benutzerdefinierte Java-Plug-ins oder Integrationen mit Experience Manager Guides entwickeln. Stellen Sie sicher, dass die SDK-Version Ihrer installierten Experience Manager Guides-Version entspricht.

| Freigabe | Java SDK-Version | Maven Central | Java API-Referenz |
|---|---|---|----|
| 2026.11.0 Service Pack 1 | 2026.11.0 | [AEM Guides SDK API 2026.11.0](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.11.0) | [Javadoc 2026.11.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) |

Weitere Informationen finden Sie unter [Konfigurieren und Verwenden der API-JAR-Datei aus dem Maven Central Repository](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/api-reference/introduction).


## Behobene Probleme

Die folgenden Probleme treten bei der Veröffentlichung in AEM Sites auf (mit der Zuordnung zusammengesetzter Komponenten):

- Das erneute Generieren ausgewählter Themen oder einer Unterzuordnung mit `microservice-based` Veröffentlichung dauert etwa so lange wie das Generieren der vollständigen Zuordnung. (GUIDES-59322)
- Durch das erneute Generieren einer Unterzuordnung, die unterteilte Themen enthält, werden im Inhaltsverzeichnis falsche Titel und Links angezeigt. Jeder Themenblock-Eintrag zeigt den Titel des letzten Themenblocks an. (GUIDES-58650)

Die folgenden Probleme treten bei der Veröffentlichung in AEM Sites mit einer dynamischen Baseline auf, entweder Baseline (alt) oder Neue Baseline:

- Die Baseline wird während desselben Veröffentlichungsvorgangs mehrmals neu erstellt, was die Veröffentlichungszeit verlängert und in einigen Fällen dazu führt, dass die Wiederherstellung verzögert wird. Bei der neuen Baseline verwendet die inkrementelle Veröffentlichung auch eine veraltete Baseline anstelle der aktuellen, sodass die Ausgabe möglicherweise nicht den neuesten Inhalt widerspiegelt. (GUIDES-60189)
- Bei Verwendung des Zuordnungs -Dashboards treten einige Leistungsprobleme auf. (GUIDES-60189, GUIDES-55646)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.11.0 Service Pack 1 identifiziert:

- Bei Verwendung von Experience Manager Guides as a Cloud Service 2026.11.0 oder höher schlägt die Veröffentlichung mit einem Anwendungsfehler fehl, wenn AEM bestimmte interne Services während des Veröffentlichungsprozesses neu startet, z. B. beim Starten einer Server-Instanz. (GUIDES-60804)<br>**Problemumgehung:** Um das Problem zu beheben, wiederholen Sie die Veröffentlichung.
- Beim Generieren einer Ausgabe für mehrere AEM Sites-Vorgaben (unter Verwendung der Zuordnung zusammengesetzter Komponenten) oder native PDF-Vorgaben mit derselben Baseline über **Zuordnungssammlung** oder API schlägt die Ausgabenerstellung mit einer `Rebuild the Baseline` Ausnahme fehl. (GUIDES-60877) <br>**Problemumgehung:** Veröffentlichen Sie die Vorgaben sequenziell anstatt gleichzeitig, um das Problem zu vermeiden.

