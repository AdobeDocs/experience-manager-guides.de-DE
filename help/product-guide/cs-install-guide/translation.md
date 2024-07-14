---
title: Inhalte übersetzen
description: Erfahren Sie, wie Sie Inhalte übersetzen
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: bcb61127f5f69ac39860a90eac2e1a56ecd1de31
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 13%

---

# Inhalte übersetzen {#id181GB0400UI}

Automatisieren Sie die Übersetzung von Seiteninhalten, Assets und benutzergenerierten Inhalten, um mehrsprachige Websites zu erstellen und zu pflegen. Um Übersetzungs-Workflows zu automatisieren, integrieren Sie Übersetzungsdienstleister in AEM und erstellen Sie Projekte für die Übersetzung von Inhalten in mehrere Sprachen. AEM unterstützt Workflows für menschliche und maschinelle Übersetzungen.

- Menschliche Übersetzung: Inhalte werden an Ihren Übersetzungsdienstleister gesendet und von professionellen Übersetzern übersetzt. Wenn die Inhalte übersetzt wurden, werden sie zurückgesendet und in AEM importiert. Wenn Ihr Übersetzungsanbieter in AEM integriert ist, werden Inhalte automatisch zwischen AEM und dem Übersetzungsanbieter ausgetauscht

- Maschinelle Übersetzung: Der Dienst für maschinelle Übersetzung übersetzt Ihre Inhalte sofort.


Die Übersetzung der Inhalte umfasst die folgenden Schritte:

1. Verbinden Sie AEM mit Ihrem [Übersetzungsdienstleister](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) und erstellen Sie Framework-Konfigurationen für die Übersetzungsintegration.

1. Verknüpfen Sie die Seiten Ihres Sprach-Masters mit dem Übersetzungsdienst und den Framework-Konfigurationen.

1. Identifizieren Sie den Typ des zu übersetzenden [Inhalts](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Bereiten Sie die Inhalte für die Übersetzung vor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en), indem Sie den Sprachstamm und die Stammseiten der Sprachkopien erstellen.

1. Erstellen Sie [Übersetzungsprojekte](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) , um die zu übersetzenden Inhalte zusammenzustellen und den Übersetzungsprozess vorzubereiten.

1. Verwenden Sie die Übersetzungsprojekte, um den Prozess für die Inhaltsübersetzung zu verwalten.[](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en)


Wenn Ihr Übersetzungsanbieter keinen Connector zur Integration mit AEM bereitstellt, unterstützt AEM den manuellen Export und Import von übersetzten Inhalten im XML-Format.

>[!TIP]
>
> Best Practices zur Übersetzung von Inhalten finden Sie im Abschnitt *Übersetzung* des Best Practices-Handbuchs.

## Konfigurieren der Registerkarte &quot;Übersetzung&quot;im DITA-Map-Dashboard

So blenden Sie die Registerkarte Übersetzung im DITA Map-Dashboard aus:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um die Registerkarte &quot;Übersetzung&quot;im Zuordnungs-Dashboard zu konfigurieren:

   | PID | Eigenschaftenschlüssel | Eigenschaftswert |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolesch \( true/false\).<br> **Standardwert**: `true` |

   >[!NOTE]
   >
   > Diese Konfiguration ist standardmäßig aktiviert und die Registerkarte &quot;Übersetzung&quot;ist nicht im Landkarten-Dashboard verfügbar.


## Konfigurieren des komponentenbasierten Übersetzungs-Workflows

Wenn der Connector für den Übersetzungsanbieter keine DITA-Inhalte unterstützt, muss der komponentenbasierte Übersetzungs-Workflow aktiviert werden. Nach der Aktivierung wird der übersetzbare Inhalt als Asset-Metadaten gesendet. Der Connector muss jedoch die Übersetzung von Asset-Metadaten unterstützen, damit dieser Workflow funktioniert.

Basierend auf dem in Ihrem Setup verwendeten Übersetzungs-Workflow sollte die Option für komponentenbasierte Übersetzungs-Workflows konfiguriert werden. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um den komponentenbasierten Übersetzungs-Workflow zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolesch: <br> -   Wenn Sie eine menschliche Übersetzung verwenden, deaktivieren Sie die Option *komponentenbasierter Übersetzungs-Workflow **\( `false`\).*** <br> -   Wenn Sie maschinelle Übersetzung verwenden, aktivieren Sie die Option *Komponenten-basierter Übersetzungs-Workflow aktivieren \( `true`\)* .**** |



## Konfigurieren des alten Übersetzungs-Workflows

Es wird empfohlen, den neuesten Übersetzungs-Workflow zu verwenden, der die Leistung verbessert. Wenn Sie jedoch den alten Übersetzungs-Workflow verwenden möchten, können Sie ihn konfigurieren.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschaft-)Details an, um den alten Übersetzungs-Workflow zu konfigurieren:




| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Boolescher Wert: <br> - Wenn Sie den neuesten Übersetzungs-Workflow verwenden, deaktivieren Sie die Option *Deaktivieren* \( `false`\) und führen Sie den **alten Übersetzungs-Workflow ausführen** aus. Der neueste Übersetzungs-Workflow ist standardmäßig aktiviert. <br> -   Wenn Sie die alte Übersetzung verwenden, aktivieren Sie die Option *Enable \( `true`\)* the **Run Legacy translation workflow** . |



>[!NOTE]
>
> Wenn Sie Übersetzungs-Connector verwenden, stellen Sie sicher, dass Sie den Connector wie im Thema *[Konfigurieren des Übersetzungsintegrations-Frameworks](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* in der Adobe Experience Manager-Dokumentation beschrieben konfiguriert haben.

>[!IMPORTANT]
>
> Nachdem Sie die Übersetzungskonfigurationen eingerichtet haben, stellen Sie sicher, dass Sie die entsprechende Cloud-Konfiguration für die Sprachordner einrichten.

## Konfigurieren der Nachbearbeitung temporärer Sprachkopien

Wenn Sie den Übersetzungs-Workflow starten, erstellt das System temporäre Sprachkopien des Quellinhalts. Sie können die Nachbearbeitung für diese temporären Dateien aktivieren oder deaktivieren. Im Anschlussvorgang werden die eingehenden und ausgehenden Verweise aus den Dateien aufgelöst, der Dokumentstatus wird zusammen mit anderen Vorgängen festgelegt. Wenn Sie die Nachbearbeitung für diese temporären Dateien aktivieren, kann es länger dauern, bis der Übersetzungsprozess abgeschlossen ist. Daher wird empfohlen, die Option &quot;Nachbearbeitung&quot;deaktiviert zu lassen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um die Nachbearbeitung temporärer Sprachkopien zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolesch: <br> -   Wenn Sie den Nachbearbeitungsprozess nicht für die temporären Dateien ausführen möchten, aktivieren Sie die Option *Sprachkopien mit Post-Verarbeitung deaktivieren* \( false\)**-Prozess** .<br> -   Wenn Sie die Nachbearbeitung für die temporären Dateien ausführen möchten, aktivieren Sie die Option *Post-Prozesssprachkopien aktivieren* \( true\).<br>**** **Standardwert**: false |

