---
title: Wissensdatenbank
description: Erfahren Sie, wie Sie über die Zuordnungskonsole eine Knowledge Base-Voreinstellung erstellen. Konfigurieren der Knowledgebase-Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
exl-id: 31fdfd96-377c-406b-96ed-59a80bf6e03e
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 1%

---

# Wissensdatenbank {#knowledge-base}

Führen Sie die folgenden Schritte aus, um die Voreinstellung **Wissensdatenbank** über die Zuordnungskonsole zu erstellen:

1. [Öffnen Sie eine DITA-Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).

   Sie können auf die Zuordnungsdatei auch über das Widget **Letzte Dateien** im Abschnitt [Übersicht](./intro-home-page.md#overview) zugreifen. Die ausgewählte Zuordnungsdatei wird dann in der Zuordnungskonsole geöffnet.
1. Klicken **auf der Registerkarte** Ausgabevorgaben“ auf das Symbol + , um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **Wissensdatenbank** aus der Dropdown-Liste Typ im Dialogfeld **Neue**) aus.
1. Wählen **im Feld** ein Ziel für die generierte Ausgabe aus. Die verfügbaren Optionen sind: **Adobe Experience Manager**, **Salesforce** und **ServiceNow**.

   ![](./images/knowledge-base-preset-dialog-box.png){width="350" align="left"}

1. Wählen Sie die **Zum aktuellen Ordnerprofil hinzufügen**, um eine Ausgabevorgabe innerhalb des aktuellen Ordnerprofils zu erstellen. Das ![Ordnerprofilsymbol](images/global-preset-icon.svg) gibt eine Vorgabe auf Ordnerprofilebene an.

   Weitere Informationen zu [Verwalten globaler und Ordnerprofil-Ausgabevorgaben](./web-editor-manage-output-presets.md).

1. Wählen Sie **Hinzufügen** aus.

   Die Voreinstellung für die Wissensdatenbank wird erstellt.

## Konfiguration der Wissensdatenbank{#knowledge-base-configuration}


Die Konfigurationsoptionen für die Knowledgebase-Voreinstellung sind auf den Registerkarten **Allgemein**, **Artikel** und Ausgewähltes Ziel (**AEM**/ **ServiceNow**/ **Salesforce**) organisiert.

![](./images/kb-aem-preset.png){width="550" align="left"}

### Allgemein

Die folgenden Konfigurationsoptionen sind auf der Registerkarte **Allgemein** verfügbar:

| Optionen in der Wissensdatenbank | Beschreibung |
| --- | --- |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVAL-**: Wählen Sie DITAVAL-Datei(en), um personalisierte Inhalte zu generieren. Sie können mehrere DITAVAL-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVAL-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVAL-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus der Voreinstellung gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im Adobe Experience Manager-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVAL-Dateien auswählen. Wenn Sie einen anderen Dateityp auswählen, wird ein Fehler angezeigt.<br><br> **Hinweis**: Beachten Sie bei Verwendung der DITAVAL-Filterung für die **Salesforce-** Folgendes: <br> - Für jede DITAVAL-Eigenschaft werden nur `Include`- und `Exclude` unterstützt.<br> - Markierung zum visuellen Markieren oder Hervorheben bedingter Inhalte in der Ausgabe wird nicht unterstützt.<br> - In den Ausgabevorgaben kann nur eine einzige DITAVAL-Datei zur Veröffentlichung ausgewählt werden. Mehrere DITAVAL-Dateiauswahlen werden für die Salesforce-Veröffentlichung nicht unterstützt. <br>- `ditavalref` Verweise im Inhalt werden nicht unterstützt. <br><br> **Bedingungsvorgabe**: Wählen Sie im Dropdown-Menü eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie [ „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in Adobe Experience Manager konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, der nach Abschluss der Ausgabegenerierung ausgeführt werden soll.<br><br>**Hinweis**: Weitere Informationen zum [Anpassen des Workflows nach der Ausgabe](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) finden Sie im Installations- und Konfigurationshandbuch für Cloud Services. |

### Artikel

Auf dieser Registerkarte wird die Baumstruktur oder die hierarchische Ansicht der Zuordnung angezeigt. Wählen Sie die Themen aus, die Sie in einer Wissensdatenbank veröffentlichen möchten. Erweitern Sie einen Inhaltsverzeichnisknoten und wählen Sie die Themen aus, die Sie veröffentlichen möchten.

### Target - Adobe Experience Manager/ServiceNow/Salesforce

Die Konfigurationsoptionen ändern sich je nach ausgewählter Zielgruppe.


**Adobe Experience Manager**

Die folgenden Konfigurationsoptionen werden für **Adobe Experience Manager** als Ziel angezeigt:


>[!NOTE]
>
>Sie können die Adobe Experience Manager-Knowledgebase-Voreinstellung nur verwenden, wenn sie von Ihrem Administrator konfiguriert wurde.

| Adobe Experience Manager-Optionen | Beschreibung |
| --- | --- |
| Artikelpfad verwenden | Wählen Sie diese Option, um den **Artikelpfad** des Ordners anzuzeigen, der die Knowledge-Base-Vorlagen enthält. |
| Artikelpfad | Dieses Feld wird angezeigt, wenn Sie die Option **Artikelpfad verwenden** auswählen. Wählen Sie in Ihrem Adobe Experience Manager-Repository die Knowledge Base-Site aus, auf der die Ausgabe gespeichert wird. |
| Site | Verwenden Sie dieses Feld, um die erforderliche Adobe Experience Manager-Wissensdatenbank auszuwählen. Sie können Wissensdatenbanken auf der Adobe Experience Manager-Site so konfigurieren, dass Inhalte basierend auf den Berechtigungen gespeichert werden. Die Artikel aus dieser DITA-Map können in diesen Wissensdatenbanken veröffentlicht werden. |
| Kategorie | Wählen Sie eine Kategorie aus dem Dropdown-Menü aus, um die Themen des Inhaltsverzeichnisses in dieser Kategorie auf der Adobe Experience Manager-Site zu veröffentlichen. |
| Abschnittsvorlage und Artikelvorlage | Dies sind die Strukturkomponenten, die zum Organisieren des Inhalts Ihrer Ausgabe verwendet werden. Diese sind in der Adobe Experience Manager-Site-Vorlage vordefiniert. |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in Adobe Experience Manager konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br>Weitere Informationen zum [Anpassen des Workflows nach der Ausgabe](../install-guide/customize-workflows.md#id17A6GI004Y4) im Installations- und Konfigurationshandbuch. |

>[!TIP]
> 
>Wählen Sie das **Aktualisieren**-Symbol aus, um die entsprechenden Vorlagen in die Felder gemäß der von Ihnen ausgewählten Wissensdatenbankvorlage einzufügen.

**ServiceNow**

Die folgenden Konfigurationsoptionen werden für „ServiceNow **als** angezeigt:

| ServiceNow-Optionen | Beschreibung |
| --- | --- |
| Profil veröffentlichen | Verwenden Sie das Dropdown, um aus den von Ihrem Administrator konfigurierten ServiceNow-Verbindungsprofilen auszuwählen. Weitere Informationen dazu, wie Ihr Administrator ein Veröffentlichungsprofil erstellen kann, finden Sie in der Beschreibung der Funktion **Workspace** (angezeigt als **Einstellungen** für **On-Premise**) im Abschnitt [Linkes Bedienfeld](./web-editor-features.md#id2051EA0M0HS). |
| Wissensdatenbank | Wählen Sie in diesem Feld die erforderliche ServiceNow-Wissensdatenbank aus. Sie können Wissensdatenbanken auf der ServiceNow-Website so konfigurieren, dass Inhalte basierend auf den Berechtigungen gespeichert werden. Die Artikel aus dieser DITA-Map können in diesen Wissensdatenbanken veröffentlicht werden. |
| Kategorie und Unterkategorie | Kategorien sind wie hierarchische Strukturen, mit denen ServiceNow-Wissensdatenbankartikel gesucht und klassifiziert werden. Fügen Sie eine Kategorie und eine Unterkategorie hinzu, um die Themen und Unterthemen des Inhaltsverzeichnisses in dieser Kategorie und Unterkategorie auf der ServiceNow-Website zu veröffentlichen. |

**Salesforce**

Die folgenden Konfigurationsoptionen werden für **Salesforce** als Ziel angezeigt:

| Salesforce-Optionen | Beschreibung |
| --- | --- |
| Profil veröffentlichen | Verwenden Sie die Dropdown-Liste, um aus den von Ihrem Administrator konfigurierten Salesforce-Verbindungsprofilen auszuwählen. Weitere Informationen dazu, wie Ihr Administrator ein Veröffentlichungsprofil erstellen kann, finden Sie unter **Workspace-** Einstellungen **(** für **On-Premise**) in der [Tabulatorleiste](./web-editor-tab-bar.md). |
| Datensatztyp | Verwenden Sie das Dropdown, um einen der in Salesforce eingerichteten Datensatztypen gemäß den Sichtbarkeitseinstellungen basierend auf Ihrem Benutzerprofil auszuwählen. Salesforce-Datensatztypen sind eine Möglichkeit, viele Datensätze eines Typs für dieses Objekt zu gruppieren. Sie definieren, wie Ihre Veröffentlichung organisiert ist. Sie können beispielsweise den Datensatztyp „Häufig gestellte Fragen“ auswählen und entsprechend dem Layout und den Feldern der häufig gestellten Fragen veröffentlichen. |
| Feld für Artikelinhalt | Sie können für jede Datensatztypvorlage unterschiedliche Felder und ein eindeutiges Layout verwenden. Verwenden Sie diese Felder, um je nach Artikeltyp spezifische Informationen einzugeben. Sie können beispielsweise den Titel, die Antwort und die Gleichung eines FAQ-Artikels anzeigen. |
| Kategorien | Wählen Sie eine Kategorie aus dem Dropdown-Menü aus, um die Themen des Inhaltsverzeichnisses in dieser Kategorie auf der Salesforce-Site zu veröffentlichen. |

**Einige weitere Optionen**

Sie können auch die folgenden Optionen in den Salesforce- und ServiceNow-Vorgaben anzeigen:

| Optionen | Beschreibung |
| --- | --- |
| Entfernen Sie die Themenüberschrift aus dem Artikelinhalt. | Wählen Sie diese Option, um die Themenüberschrift aus dem Artikel in der veröffentlichten Ausgabe zu entfernen. |
| Als Entwurf hochladen | Wählen Sie diese Option aus, um das Thema hochzuladen und als Entwurf freizugeben, bevor es den Benutzern zur Verfügung gestellt wird. |
| Bilder hochladen | Wählen Sie diese Option aus, wenn Bilder in Themen in der veröffentlichten Ausgabe enthalten sein sollen. |
| Hochladen verknüpfter Dokumente | Wählen Sie diese Option aus, um die in den Themen verknüpften Dokumente in die veröffentlichte Ausgabe aufzunehmen. |





**Übergeordnetes Thema:** [Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
