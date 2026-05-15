---
title: Inhalte übersetzen
description: Erfahren Sie, wie Sie Inhalte übersetzen
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/WjrAoZplwWbFYxySm-faIIda81AWTYnqhvbdsRk8tjU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 877
ht-degree: 11%

---

# Inhalte übersetzen {#id181GB0400UI}

Automatisieren Sie die Übersetzung von Seiteninhalten, Assets und benutzergenerierten Inhalten, um mehrsprachige Websites zu erstellen und zu pflegen. Um Übersetzungs-Workflows zu automatisieren, integrieren Sie Übersetzungsdienstleister in AEM und erstellen Sie Projekte für die Übersetzung von Inhalten in mehrere Sprachen. AEM unterstützt Workflows für menschliche und maschinelle Übersetzungen.

- Menschliche Übersetzung: Inhalte werden an Ihren Übersetzungsdienstleister gesendet und von professionellen Übersetzern übersetzt. Wenn die Inhalte übersetzt wurden, werden sie zurückgesendet und in AEM importiert. Wenn Ihr Übersetzungsanbieter mit AEM integriert ist, werden die Inhalte automatisch zwischen AEM und dem Übersetzungsanbieter ausgetauscht

- Maschinelle Übersetzung: Der maschinelle Übersetzungs-Service übersetzt sofort Ihre Inhalte


Die Übersetzung der Inhalte umfasst die folgenden Schritte:

1. Verbinden Sie AEM mit Ihrem [Übersetzungsdienstleister](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=de) und erstellen Sie Konfigurationen für die Integration des Übersetzungs-Frameworks.

1. Verknüpfen Sie die Seiten Ihres Sprachstamms mit dem Übersetzungsdienstleister und den Framework-Konfigurationen.

1. Identifizieren Sie den Typ des [zu übersetzenden Inhalts](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=de).

1. [Bereiten Sie die Inhalte für die Übersetzung vor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en), indem Sie den Sprachstamm und die Stammseiten der Sprachkopien erstellen.

1. Erstellen Sie [Übersetzungsprojekte](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=de) um die zu übersetzenden Inhalte zusammenzustellen und den Übersetzungsprozess vorzubereiten.

1. Verwenden Sie die Übersetzungsprojekte, um [den Prozess zur Übersetzung der Inhalte &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=de) verwalten.


Wenn Ihr Übersetzungsdienstleister keinen Connector für die Integration mit AEM bereitstellt, unterstützt AEM den manuellen Export und Import übersetzter Inhalte im XML-Format.

>[!TIP]
>
> Im Abschnitt *Übersetzung* des Best Practices-Handbuchs finden Sie Best Practices für die Übersetzung von Inhalten.

## Konfigurieren der Registerkarte Übersetzung im Dashboard für DITA-Zuordnungen

Gehen Sie wie folgt vor, um die Registerkarte Übersetzung im DITA-Zuordnungs-Dashboard auszublenden:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um die Registerkarte Übersetzung im Zuordnungs-Dashboard zu konfigurieren:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolescher Wert \( true/false\).<br> **Standardwert**: `true` |

   >[!NOTE]
   >
   > Diese Konfiguration ist standardmäßig aktiviert und die Registerkarte Übersetzung ist im Zuordnungs-Dashboard nicht verfügbar.


## Konfigurieren eines komponentenbasierten Übersetzungs-Workflows

Wenn der Connector für den Übersetzungsanbieter DITA-Inhalte nicht unterstützt, muss der komponentenbasierte Übersetzungs-Workflow aktiviert werden. Nach der Aktivierung werden die übersetzbaren Inhalte als Asset-Metadaten gesendet. Der Connector muss jedoch die Übersetzung von Asset-Metadaten unterstützen, damit dieser Workflow funktioniert.

Basierend auf dem in Ihrem Setup verwendeten Übersetzungs-Workflow sollte die Option Komponentenbasierter Übersetzungs-Workflow konfiguriert werden. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um den komponentenbasierten Übersetzungs-Workflow zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolescher Wert: <br> - Wenn Sie die menschliche Übersetzung verwenden, *Deaktivieren* \( `false`\) die Option **Komponentenbasierter Übersetzungs-Workflow**. <br> - Wenn Sie maschinelle Übersetzung verwenden, aktivieren *die Option \( `true`\* der **Komponentenbasierter Übersetzungs-Workflow**. |



## Konfigurieren des alten Übersetzungs-Workflows

>[!IMPORTANT]
>
> Es wird empfohlen, für eine verbesserte Leistung den neuesten Übersetzungs-Workflow zu verwenden, der in AEM Guides 2024.06.0 und höher verfügbar ist. Wenn Sie jedoch eine Anpassung im Übersetzungsprozess aktiviert haben und dieser durch den neuen Workflow beeinflusst wird, sollten Sie zur Problemumgehung den alten Übersetzungs-Workflow wiederherstellen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) zum Konfigurieren des Legacy-Übersetzungs-Workflows an:


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Boolescher Wert: <br> - Wenn Sie den neuesten Übersetzungs-Workflow verwenden, wählen *Deaktivieren* \( `false`\) die Option **Legacy-Übersetzungs-Workflow ausführen** aus.  <br> - Wenn Sie die alte Übersetzung verwenden, aktivieren *\( `true`\)* die Option **Legacy-Übersetzungs-Workflow ausführen**. <br> **Standardwert**: false |




>[!NOTE]
>
> Wenn Sie einen Übersetzungs-Connector verwenden, stellen Sie sicher, dass Sie den Connector konfiguriert haben, wie in der Dokumentation *[Konfigurieren des Translation Integration Framework](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=de)* beschrieben.

>[!IMPORTANT]
>
> Nachdem Sie die Übersetzungskonfigurationen eingerichtet haben, stellen Sie sicher, dass Sie die entsprechende Cloud-Konfiguration in den Sprachordnern eingerichtet haben.

## Konfigurieren der Nachbearbeitung von temporären Sprachkopien

Wenn Sie den Übersetzungs-Workflow starten, erstellt das System temporäre Sprachkopien der Quellinhalte. Sie können den Nachbearbeitungsvorgang für diese temporären Dateien aktivieren oder deaktivieren. Bei der Nachbearbeitung werden die ein- und ausgehenden Verweise aus den Dateien aufgelöst und der Dokumentstatus zusammen mit anderen Vorgängen festgelegt. Wenn Sie die Nachbearbeitung dieser temporären Dateien aktivieren, kann der Abschluss des Übersetzungsprozesses länger dauern. Daher wird empfohlen, die Nachbearbeitungsoption deaktiviert zu lassen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die Nachbearbeitung von temporären Sprachkopien zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolescher Wert: <br> - Wenn Sie den Nachbearbeitungsvorgang für die temporären Dateien nicht ausführen möchten, wählen Sie *Deaktivieren* \( false\) die Option **Sprachkopien nachverarbeiten** aus.<br> - Wenn Sie den Nachbearbeitungsvorgang für die temporären Dateien ausführen möchten, wählen Sie *Aktivieren* \( true\) die Option **Sprachkopien nachverarbeiten** aus.<br> **Standardwert**: false |

