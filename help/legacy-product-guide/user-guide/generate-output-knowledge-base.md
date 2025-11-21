---
title: Wissensdatenbank
description: Erfahren Sie, wie Sie eine Wissensdatenbankvorgabe aus dem Web-Editor und dem Zuordnungs-Dashboard erstellen. Konfigurieren der Knowledgebase-Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 5fc81de9-9ae0-4cd4-a7ef-b52eed2479f7
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Wissensdatenbank {#knowledge-base}

Sie können die Voreinstellung **Wissensdatenbank** im Web-Editor erstellen:

Öffnen Sie im Repository-Bedienfeld die DITA-Zuordnungsdatei in **Zuordnungsansicht**, wählen Sie dann auf der Registerkarte **Ausgabe** das Symbol + aus, um eine Ausgabevorgabe zu erstellen, und wählen Sie dann **Wissensdatenbank** aus der Dropdown-Liste **Typ** im Dialogfeld **Neue Ausgabevorgabe** aus. Sie können die Vorgabe benennen und das Ziel auswählen, um die Ausgabe mithilfe von **Adobe Experience Manager**, **Salesforce** oder **ServiceNow** zu generieren.




## Konfiguration der Wissensdatenbank{#knowledge-base-configuration}


Im Web-Editor wurden die folgenden Konfigurationen unter den Registerkarten **Allgemein** und **Artikel** organisiert. Sie können auch die Einstellungen für die spezifische **Wissensdatenbank** konfigurieren, die Sie als Ziel, **Adobe Experience Manager**, **Salesforce** oder **ServiceNow** ausgewählt haben.


### Allgemein

| Optionen in der Wissensdatenbank | Beschreibung |
| --- | --- |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVAL-**: Wählen Sie DITAVAL-Datei(en), um personalisierte Inhalte zu generieren. Sie können mehrere DITAVAL-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVAL-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVAL-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus der Voreinstellung gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im Adobe Experience Manager-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVAL-Dateien auswählen. Wenn Sie einen anderen Dateityp auswählen, wird ein Fehler angezeigt.<br>* **Bedingungsvorgabe**: Wählen Sie eine Bedingungsvorgabe aus der Dropdown-Liste aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie [ „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in Adobe Experience Manager konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, der nach Abschluss der Ausgabegenerierung ausgeführt werden soll.<br><br>**Hinweis**: Weitere Informationen zum [Anpassen des Workflows nach der Ausgabe](/help/product-guide/cs-install-guide/customize-workflows.md#id17A6GI004Y4) finden Sie im Installations- und Konfigurationshandbuch für Cloud Services. |

### ServiceNow

| ServiceNow-Optionen | Beschreibung |
| --- | --- |
| Profil veröffentlichen | Verwenden Sie das Dropdown, um aus den von Ihrem Administrator konfigurierten ServiceNow-Verbindungsprofilen auszuwählen. Weitere Informationen dazu, wie Admins ein Veröffentlichungsprofil erstellen können, finden Sie in der **Editor-Einstellungen** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](./web-editor-features.md#id2051EA0M0HS). |
| Wissensdatenbank | Wählen Sie in diesem Feld die erforderliche ServiceNow-Wissensdatenbank aus. Sie können Wissensdatenbanken auf der ServiceNow-Website so konfigurieren, dass Inhalte basierend auf den Berechtigungen gespeichert werden. Die Artikel aus dieser DITA-Map können in diesen Wissensdatenbanken veröffentlicht werden. |
| Kategorie und Unterkategorie | Kategorien sind wie hierarchische Strukturen, mit denen ServiceNow-Wissensdatenbankartikel gesucht und klassifiziert werden. Fügen Sie eine Kategorie und eine Unterkategorie hinzu, um die Themen und Unterthemen des Inhaltsverzeichnisses in dieser Kategorie und Unterkategorie auf der ServiceNow-Website zu veröffentlichen. |

### Salesforce

| Salesforce-Optionen | Beschreibung |
| --- | --- |
| Profil veröffentlichen | Verwenden Sie die Dropdown-Liste, um aus den von Ihrem Administrator konfigurierten Salesforce-Verbindungsprofilen auszuwählen. Weitere Informationen dazu, wie Admins ein Veröffentlichungsprofil erstellen können, finden Sie in der **Editor-Einstellungen** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](./web-editor-features.md#id2051EA0M0HS). |
| Datensatztyp | Verwenden Sie das Dropdown, um einen der in Salesforce eingerichteten Datensatztypen gemäß den Sichtbarkeitseinstellungen basierend auf Ihrem Benutzerprofil auszuwählen. Salesforce-Datensatztypen sind eine Möglichkeit, viele Datensätze eines Typs für dieses Objekt zu gruppieren. Sie definieren, wie Ihre Veröffentlichung organisiert ist. Sie können beispielsweise den Datensatztyp „Häufig gestellte Fragen“ auswählen und entsprechend dem Layout und den Feldern der häufig gestellten Fragen veröffentlichen. |
| Feld für Artikelinhalt | Sie können für jede Datensatztypvorlage unterschiedliche Felder und ein eindeutiges Layout verwenden. Verwenden Sie diese Felder, um je nach Artikeltyp spezifische Informationen einzugeben. Sie können beispielsweise den Titel, die Antwort und die Gleichung eines FAQ-Artikels anzeigen. |
| Kategorien | Wählen Sie eine Kategorie aus dem Dropdown-Menü aus, um die Themen des Inhaltsverzeichnisses in dieser Kategorie auf der Salesforce-Site zu veröffentlichen. |

Sie können auch die folgenden Optionen in den Salesforce- und ServiceNow-Vorgaben anzeigen:

| Optionen | Beschreibung |
| --- | --- |
| Entfernen Sie die Themenüberschrift aus dem Artikelinhalt. | Wählen Sie diese Option, um die Themenüberschrift aus dem Artikel in der veröffentlichten Ausgabe zu entfernen. |
| Als Entwurf hochladen | Wählen Sie diese Option aus, um das Thema hochzuladen und als Entwurf freizugeben, bevor es den Benutzern zur Verfügung gestellt wird. |
| Bilder hochladen | Wählen Sie diese Option aus, wenn Bilder in Themen in der veröffentlichten Ausgabe enthalten sein sollen. |
| Hochladen verknüpfter Dokumente | Wählen Sie diese Option aus, um die in den Themen verknüpften Dokumente in die veröffentlichte Ausgabe aufzunehmen. |

### Adobe Experience Manager

>[!NOTE]
>
>Sie können die Adobe Experience Manager-Knowledgebase-Voreinstellung verwenden, wenn sie von Ihrem Administrator konfiguriert wurde. Weitere Informationen finden Sie [ Abschnitt „Artikelbasierte Veröffentlichung im Web](/help/product-guide/install-guide/configure-article-based-publishing.md)Editor“ im Installations- und Konfigurationshandbuch.

| Adobe Experience Manager-Optionen | Beschreibung |
| --- | --- |
| Artikelpfad verwenden | Wählen Sie diese Option, um den **Artikelpfad** des Ordners anzuzeigen, der die Knowledge-Base-Vorlagen enthält. |
| Artikelpfad | Dieses Feld wird angezeigt, wenn Sie die Option **Artikelpfad verwenden** auswählen. Wählen Sie in Ihrem Adobe Experience Manager-Repository die Knowledge Base-Site aus, auf der die Ausgabe gespeichert wird. |
| Site | Verwenden Sie dieses Feld, um die erforderliche Adobe Experience Manager-Wissensdatenbank auszuwählen. Sie können Wissensdatenbanken auf der Adobe Experience Manager-Site so konfigurieren, dass Inhalte basierend auf den Berechtigungen gespeichert werden. Die Artikel aus dieser DITA-Map können in diesen Wissensdatenbanken veröffentlicht werden. |
| Kategorie | Wählen Sie eine Kategorie aus dem Dropdown-Menü aus, um die Themen des Inhaltsverzeichnisses in dieser Kategorie auf der Adobe Experience Manager-Site zu veröffentlichen. |
| Abschnittsvorlage und Artikelvorlage | Dies sind die Strukturkomponenten, die zum Organisieren des Inhalts Ihrer Ausgabe verwendet werden. Diese sind in der Adobe Experience Manager-Site-Vorlage vordefiniert. |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in Adobe Experience Manager konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br>Weitere Informationen zum [Anpassen des Workflows nach der Ausgabe](/help/product-guide/install-guide/customize-workflows.md#id17A6GI004Y4) im Installations- und Konfigurationshandbuch. |

>[!TIP]
> 
>Wählen Sie **Aktualisieren** ![Aktualisieren-Symbol](images/navtitle-refresh-icon.svg), um die entsprechenden Vorlagen in den Feldern gemäß der von Ihnen ausgewählten Wissensdatenbankvorlage auszufüllen.

### Artikel

Auf dieser Registerkarte wird die Baumstruktur oder die hierarchische Ansicht der Zuordnung angezeigt. Wählen Sie die Themen aus, die Sie in einer Wissensdatenbank veröffentlichen möchten. Erweitern Sie einen Inhaltsverzeichnisknoten und wählen Sie die Themen aus, die Sie veröffentlichen möchten.

**Übergeordnetes Thema:** [Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
