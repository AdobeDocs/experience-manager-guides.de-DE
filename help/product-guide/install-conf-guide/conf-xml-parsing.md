---
title: Konfigurieren der XML-Analyseentität für Cloud Service und On-Premise
description: Erfahren Sie, wie Sie die XML-Analyseentität für Cloud Service und On-Premise konfigurieren
feature: Output Generation
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%
---
# Größenbeschränkung für XML-Parser-Entitäten konfigurieren

Mit Experience Manager Guides können Sie eine Begrenzung der Gesamtgröße der Entität konfigurieren, die der XML-Parser bei der Veröffentlichung akzeptiert. Dadurch werden Probleme wie XML-Entitätserweiterungsangriffe und die Verarbeitung übergroßer Payloads verhindert.

>[!NOTE]
>
>Sie können eine Begrenzung der Gesamtgröße der Entitäten konfigurieren, die vom XML-Parser während der Veröffentlichung akzeptiert werden, um Risiken wie Angriffe auf die XML-Entitätserweiterung und die Verarbeitung übergroßer Payloads zu minimieren. Die Handhabung von Entitätsgrößenbeschränkungen unterscheidet sich zwischen Java 21 und Java 25. Daher wird Umgebungen, die auf Java 25 aktualisieren, empfohlen, ihre Konfiguration zu überprüfen und zu validieren, um sicherzustellen, dass Veröffentlichungs-Workflows weiterhin fehlerfrei funktionieren.

Diese Konfiguration umfasst zwei verwandte Eigenschaften:

* **Gesamte Entitätsgrößenbeschränkung des XML-Parsers anwenden** (`dxml.publish.xml.apply.total.entity.size.limit`): Aktiviert oder deaktiviert die Prüfung der Gesamtentitätsgröße.
* **XML Parser Total Entity Size Limit** (`dxml.publish.xml.total.entity.size.limit`): Gibt den JAXP-`totalEntitySizeLimit` (Zeichen) an, der auf sichere XML-Parser angewendet wird, wenn das Anwenden-Flag aktiviert ist.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren dieser Eigenschaften basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.apply.total.entity.size.limit` | **Standardwert:** „true“ |
   | `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService` | `dxml.publish.xml.total.entity.size.limit` | **Standardwert:** „50000000“ |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService* und wählen Sie es aus.

1. Konfigurieren Sie die folgenden Einstellungen entsprechend Ihren Anforderungen:

   * **Gesamte Entitätsgrößenbeschränkung des XML-Parsers anwenden** (`dxml.publish.xml.apply.total.entity.size.limit`): Diese Einstellung ist standardmäßig deaktiviert.
   * **XML Parser Total Entity Size Limit** (`dxml.publish.xml.total.entity.size.limit`): Dieser Wert ist standardmäßig auf `50000000` Zeichen festgelegt. Diese Einstellung wird nur wirksam, wenn die Einstellung **Gesamtgröße für XML-Parser anwenden** aktiviert ist.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]



