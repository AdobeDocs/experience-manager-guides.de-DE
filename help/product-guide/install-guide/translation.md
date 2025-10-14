---
title: Übersetzen von Inhalten in AEM Guides
description: Erfahren Sie, wie Sie Inhalte übersetzen
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 12%

---

# Inhalte übersetzen {#id181GB0400UI}

Automatisieren Sie die Übersetzung von Seiteninhalten, Assets und benutzergenerierten Inhalten, um mehrsprachige Websites zu erstellen und zu pflegen. Um Übersetzungs-Workflows zu automatisieren, integrieren Sie Übersetzungsdienstleister in AEM und erstellen Sie Projekte für die Übersetzung von Inhalten in mehrere Sprachen. AEM unterstützt Workflows für menschliche und maschinelle Übersetzungen.

- Menschliche Übersetzung: Inhalte werden an Ihren Übersetzungsdienstleister gesendet und von professionellen Übersetzern übersetzt. Wenn die Inhalte übersetzt wurden, werden sie zurückgesendet und in AEM importiert. Wenn Ihr Übersetzungsanbieter mit AEM integriert ist, werden die Inhalte automatisch zwischen AEM und dem Übersetzungsanbieter ausgetauscht

- Maschinelle Übersetzung: Der maschinelle Übersetzungs-Service übersetzt sofort Ihre Inhalte


Die Übersetzung der Inhalte umfasst die folgenden Schritte:

1. Verbinden Sie AEM mit Ihrem [Übersetzungsdienstleister](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) und erstellen Sie [Framework-Konfigurationen für die Übersetzungsintegration](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Verknüpfen Sie die Seiten Ihres Sprachstamms mit dem [Übersetzungsdienstleister und den Framework-Konfigurationen](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifizieren Sie den Typ des [zu übersetzenden Inhalts](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Bereiten Sie die Inhalte für die Übersetzung vor](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-prep.html), indem Sie den Sprachstamm und die Stammseiten der Sprachkopien erstellen.

1. Erstellen Sie [Übersetzungsprojekte](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-manage.html) um die zu übersetzenden Inhalte zusammenzustellen und den Übersetzungsprozess vorzubereiten.

1. Verwenden Sie die Übersetzungsprojekte, um [den Prozess zur Übersetzung der Inhalte &#x200B;](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-manage.html) verwalten.


Wenn Ihr Übersetzungsdienstleister keinen Connector für die Integration mit AEM bereitstellt, unterstützt AEM den manuellen Export und Import übersetzter Inhalte im XML-Format.

>[!TIP]
>
> Im Abschnitt *Übersetzung* des Best Practices-Handbuchs finden Sie Best Practices für die Übersetzung von Inhalten.

## Konfigurieren der Registerkarte Übersetzung im Dashboard für DITA-Zuordnungen

Die Option Übersetzung ausblenden ist nicht standardmäßig aktiviert, und Sie müssen sie im configMgr aktivieren. Gehen Sie wie folgt vor, um die Registerkarte Übersetzung im DITA-Zuordnungs-Dashboard auszublenden:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die **Registerkarte Übersetzung ausblenden**, um die Registerkarte Übersetzung im Zuordnungs-Dashboard auszublenden.

   >[!NOTE]
   >
   > Diese Eigenschaft ist standardmäßig deaktiviert und die Registerkarte Übersetzung ist im Zuordnungs-Dashboard verfügbar.

1. Klicken Sie auf **Speichern**.

## Konfigurieren eines komponentenbasierten Übersetzungs-Workflows

Wenn der Connector für den Übersetzungsanbieter DITA-Inhalte nicht unterstützt, muss der komponentenbasierte Übersetzungs-Workflow aktiviert werden. Nach der Aktivierung werden die übersetzbaren Inhalte als Asset-Metadaten gesendet. Der Connector muss jedoch die Übersetzung von Asset-Metadaten unterstützen, damit dieser Workflow funktioniert.

Je nach dem in Ihrem Setup verwendeten Übersetzungs-Workflow sollte die Option Komponentenbasierter Übersetzungs-Workflow wie folgt konfiguriert werden:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Konfigurieren Sie **Option „Komponentenbasierter DITA-Übersetzungs** Workflow“ gemäß Ihrem Setup:

   - Wenn Sie die menschliche Übersetzung verwenden, *Sie* Option **Komponentenbasierter Übersetzungs-Workflow**.

   - Wenn Sie maschinelle Übersetzung verwenden, aktivieren *die Option* Komponentenbasierter Übersetzungs **Workflow**.

   >[!NOTE]
   >
   > Wenn Sie einen Übersetzungs-Connector verwenden, stellen Sie sicher, dass Sie den Connector konfiguriert haben, wie in *[AEM-Dokumentation unter „Konfigurieren &#x200B;](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/tc-tic.html)* Übersetzungsintegrations-Frameworks“ beschrieben.

1. Klicken Sie auf **Speichern**.

>[!IMPORTANT]
>
> Nachdem Sie die Übersetzungskonfigurationen eingerichtet haben, stellen Sie sicher, dass Sie die entsprechende Cloud-Konfiguration in den Sprachordnern eingerichtet haben.

## Konfigurieren des alten Übersetzungs-Workflows

>[!IMPORTANT]
> 
> Es wird empfohlen, für eine verbesserte Leistung den neuesten Übersetzungs-Workflow zu verwenden, der in AEM Guides 4.6.0 und höher verfügbar ist. Wenn Sie jedoch eine Anpassung im Übersetzungsprozess aktiviert haben und dieser durch den neuen Workflow beeinflusst wird, sollten Sie zur Problemumgehung den alten Übersetzungs-Workflow wiederherstellen.



Standardmäßig ist die Option Legacy-Übersetzungs-Workflow deaktiviert. Sie können diese Option konfigurieren, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Konfigurieren Sie die Workflow-Option für ältere Übersetzungen gemäß Ihren Einstellungen:

   - (*Standard*) Wenn Sie den neuesten Übersetzungs-Workflow verwenden möchten, deaktivieren Sie die Option **Legacy-Übersetzungs-Workflow**.
   - Wenn Sie den alten Übersetzungs-Workflow verwenden möchten, aktivieren Sie die Option **Legacy-Übersetzungs-Workflow ausführen**.

1. Klicken Sie auf **Speichern**.






<!---

This was added for 2406 CS IG

## Configure the legacy translation workflow 

It is recommended that you use the latest translation workflow, which provides enhanced performance. However, you can configure the legacy translation workflow if necessary.

Based on the translation workflow used in your setup, provide the following (property) details to configure the legacy translation workflow: the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ! Add the syntax of http as given in previous config

    Note: Configure htttp code as given in previous sample
    

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.



1.  Configure the **Run legacy translation workflow** option as per your setup:

    -   If you use the latest translation workflow, then *Disable* \( `false`\) the **Run legacy translation workflow** option. The latest translation workflow is enabled by default. <br> 

    -   If you use the legacy translation, then *Enable \( `true`\)* the **Run legacy translation workflow** option.

1.  Click **Save**.


--->


## Konfigurieren der Nachbearbeitung von temporären Sprachkopien

Wenn Sie den Übersetzungs-Workflow starten, erstellt das System temporäre Sprachkopien der Quellinhalte. Sie können den Nachbearbeitungsvorgang für diese temporären Dateien aktivieren oder deaktivieren. Bei der Nachbearbeitung werden die ein- und ausgehenden Verweise aus den Dateien aufgelöst und der Dokumentstatus zusammen mit anderen Vorgängen festgelegt. Wenn Sie die Nachbearbeitung dieser temporären Dateien aktivieren, kann der Abschluss des Übersetzungsprozesses länger dauern. Daher wird empfohlen, die Nachbearbeitungsoption deaktiviert zu lassen.

Standardmäßig ist die Option Nachbearbeitung temporärer Dateien deaktiviert. Sie können diese Option konfigurieren, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Konfigurieren Sie **Option „Sprachkopien nachverarbeiten** gemäß Ihrem Setup:

   - \(*Standard*\) Wenn Sie den Nachbearbeitungsvorgang für die temporären Dateien nicht ausführen möchten, *Sie* Option **Sprachkopien nachverarbeiten**.

   - Wenn Sie den Nachbearbeitungsvorgang für die temporären Dateien ausführen möchten, aktivieren *die Option* Sprachkopien **Nachbearbeitung**.

1. Klicken Sie auf **Speichern**.
