---
title: Inhalte übersetzen
description: Erfahren Sie, wie Sie Inhalte übersetzen
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 13%

---

# Inhalte übersetzen {#id181GB0400UI}

Automatisieren Sie die Übersetzung von Seiteninhalten, Assets und benutzergenerierten Inhalten, um mehrsprachige Websites zu erstellen und zu pflegen. Um Übersetzungs-Workflows zu automatisieren, integrieren Sie Übersetzungsdienstleister in AEM und erstellen Sie Projekte für die Übersetzung von Inhalten in mehrere Sprachen. AEM unterstützt Workflows für menschliche und maschinelle Übersetzungen.

- Menschliche Übersetzung: Inhalte werden an Ihren Übersetzungsdienstleister gesendet und von professionellen Übersetzern übersetzt. Wenn die Inhalte übersetzt wurden, werden sie zurückgesendet und in AEM importiert. Wenn Ihr Übersetzungsanbieter mit AEM integriert ist, werden die Inhalte automatisch zwischen AEM und dem Übersetzungsanbieter ausgetauscht

- Maschinelle Übersetzung: Der maschinelle Übersetzungs-Service übersetzt sofort Ihre Inhalte


Die Übersetzung der Inhalte umfasst die folgenden Schritte:

1. Verbinden Sie AEM mit Ihrem [Übersetzungsdienstleister](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=de) und erstellen Sie Konfigurationen für die Integration des Übersetzungs-Frameworks.

1. Verknüpfen Sie die Seiten Ihres Sprachstamms mit dem Übersetzungsdienstleister und den Framework-Konfigurationen.

1. Identifizieren Sie den Typ des [zu übersetzenden Inhalts](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=de).

1. [Bereiten Sie die Inhalte für die Übersetzung vor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=de), indem Sie den Sprachstamm und die Stammseiten der Sprachkopien erstellen.

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
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolesch: <br> -   Wenn Sie die menschliche Übersetzung verwenden, *Sie die Option* Komponentenbasierter Übersetzungs **Workflow** auf \( `false`\). <br> -   Wenn Sie die maschinelle Übersetzung verwenden, aktivieren *\( `true`\)* die Option **Komponentenbasierter Übersetzungs-Workflow**. |



## Konfigurieren des alten Übersetzungs-Workflows

>[!IMPORTANT]
>
> Es wird empfohlen, für eine verbesserte Leistung den neuesten Übersetzungs-Workflow zu verwenden, der in AEM Guides 2024.06.0 und höher verfügbar ist. Wenn Sie jedoch eine Anpassung im Übersetzungsprozess aktiviert haben und dieser durch den neuen Workflow beeinflusst wird, sollten Sie zur Problemumgehung den alten Übersetzungs-Workflow wiederherstellen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) zum Konfigurieren des Legacy-Übersetzungs-Workflows an:


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Boolescher Wert: <br> - Wenn Sie den neuesten Übersetzungs-Workflow verwenden, wählen *Deaktivieren* \( `false`\) die Option **Legacy-Übersetzungs-Workflow ausführen** aus.  <br> -   Wenn Sie die alte Übersetzung verwenden, aktivieren *\( `true`\)* die Option **Legacy-Übersetzungs-Workflow**. <br> **Standardwert**: false |




>[!NOTE]
>
> Adobe Experience Manager Wenn Sie einen Übersetzungs-Connector verwenden, stellen Sie sicher, dass Sie den Connector konfiguriert haben, wie in der Dokumentation *[Konfigurieren des Translation Integration Framework](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=de)* beschrieben.

>[!IMPORTANT]
>
> Nachdem Sie die Übersetzungskonfigurationen eingerichtet haben, stellen Sie sicher, dass Sie die entsprechende Cloud-Konfiguration in den Sprachordnern eingerichtet haben.

## Konfigurieren der Nachbearbeitung von temporären Sprachkopien

Wenn Sie den Übersetzungs-Workflow starten, erstellt das System temporäre Sprachkopien der Quellinhalte. Sie können den Nachbearbeitungsvorgang für diese temporären Dateien aktivieren oder deaktivieren. Bei der Nachbearbeitung werden die ein- und ausgehenden Verweise aus den Dateien aufgelöst und der Dokumentstatus zusammen mit anderen Vorgängen festgelegt. Wenn Sie die Nachbearbeitung dieser temporären Dateien aktivieren, kann der Abschluss des Übersetzungsprozesses länger dauern. Daher wird empfohlen, die Nachbearbeitungsoption deaktiviert zu lassen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die Nachbearbeitung von temporären Sprachkopien zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolesch: <br> -   Wenn Sie den Nachbearbeitungsvorgang für die temporären Dateien nicht ausführen möchten, wählen Sie *Deaktivieren* \( false\) die Option **Sprachkopien nachverarbeiten**.<br> -   Wenn Sie den Nachbearbeitungsvorgang für die temporären Dateien ausführen möchten, wählen Sie *Aktivieren* \( true\) die Option **Sprachkopien nachverarbeiten** aus.<br> **Standardwert**: false |

