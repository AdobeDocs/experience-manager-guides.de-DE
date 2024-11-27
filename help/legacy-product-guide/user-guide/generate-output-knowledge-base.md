---
title: Wissensdatenbank
description: Erfahren Sie, wie Sie eine Knowledge Base-Vorgabe aus dem Web-Editor und dem Map-Dashboard erstellen. Konfigurieren Sie die Ausgabevorgabe der Wissensdatenbank in AEM Guides.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Wissensdatenbank {#knowledge-base}

Sie können die Vorgabe **Knowledge Base** im Web Editor erstellen:

Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Zuordnungsdatei in **Zuordnungsansicht**, wählen Sie dann auf der Registerkarte **Ausgabe** das Symbol + aus, um eine Ausgabevorgabe zu erstellen, und wählen Sie dann im Dialogfeld **Neue Ausgabevorgabe** aus der Dropdown-Liste **Typ** die Option **Wissensdatenbank** aus. Sie können die Vorgabe benennen und das Ziel auswählen, um die Ausgabe mithilfe von **Adobe Experience Manager**, **Salesforce** oder **ServiceNow** zu generieren.




## Knowledgebase-Konfiguration{#knowledge-base-configuration}


Im Web-Editor wurden die folgenden Konfigurationen auf den Registerkarten **Allgemein** und **Artikel** organisiert. Sie können auch die Einstellungen für die spezifische **Wissensdatenbank** konfigurieren, die Sie als Ziel ausgewählt haben, **Adobe Experience Manager**, **Salesforce** oder **ServiceNow**.


### Allgemein

| Optionen der Wissensdatenbank | Beschreibung |
| --- | --- |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVAL file**: Wählen Sie DITAVAL-Dateien aus, um personalisierten Inhalt zu generieren. Sie können mehrere DITAVAL-Dateien über das Dialogfeld &quot;Durchsuchen&quot;oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuzsymbol neben dem Dateinamen, um ihn zu entfernen. DITAVAL-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen Bedingungen haben. Sie können die Dateireihenfolge beibehalten, indem Sie Dateien hinzufügen oder löschen. Wenn die DITAVAL-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus der Vorgabe gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im Adobe Experience Manager-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVAL-Dateien auswählen. Wenn Sie einen anderen Dateityp auswählen, wird ein Fehler angezeigt.<br>* **Bedingungsvorgabe**: Wählen Sie eine Bedingungsvorgabe aus der Dropdown-Liste aus, um beim Veröffentlichen der Ausgabe eine Bedingung anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte Bedingungsvorgaben der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Bedingungsvorgaben verwenden](generate-output-use-condition-presets.md#id1825FL004PN). |
| Grundlinie verwenden | Wenn Sie eine Grundlinie für die ausgewählte DITA-Zuordnung erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Anzeigen [Arbeiten mit Grundlinie](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) für weitere Details. |
| Arbeitsablauf nach der Erstellung | Wenn Sie diese Option wählen, wird eine neue Dropdownliste mit dem Workflow nach der Generierung angezeigt, die alle in Adobe Experience Manager konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, der nach Abschluss der Ausgabegenerierung ausgeführt werden soll.<br><br>**Hinweis**: Weitere Informationen zum [Anpassen des Workflows für die Generierung nach der Ausgabe](../cs-install-guide/customize-workflows.md#id17A6GI004Y4) finden Sie im Installations- und Konfigurationshandbuch für Cloud Service. |

### ServiceNow

| ServiceNow-Optionen | Beschreibung |
| --- | --- |
| Profil veröffentlichen | Verwenden Sie das Dropdown-Menü, um aus den ServiceNow-Verbindungsprofilen auszuwählen, die Ihr Administrator konfiguriert. Weitere Informationen dazu, wie Ihr Administrator ein Veröffentlichungsprofil erstellen kann, finden Sie in der Funktionsbeschreibung **Editor Settings** im Abschnitt [Left Panel](./web-editor-features.md#id2051EA0M0HS) . |
| Wissensdatenbank | Verwenden Sie dieses Feld, um die erforderliche ServiceNow-Wissensdatenbank auszuwählen. Sie können Wissensdatenbanken auf der ServiceNow-Site konfigurieren, um den Inhalt basierend auf den Berechtigungen zu speichern. Die Artikel aus dieser DITA-Karte können in diesen Wissensdatenbanken veröffentlicht werden. |
| Kategorie und Unterkategorie | Kategorien ähneln hierarchischen Baumstrukturen, mit denen ServiceNow Knowledge Base-Artikel gesucht und klassifiziert werden. Fügen Sie eine Kategorie und Unterkategorie hinzu, um die Themen und Unterthemen des Inhaltsverzeichnisses in dieser Kategorie und Unterkategorie auf der ServiceNow-Site zu veröffentlichen. |

### Salesforce

| Salesforce-Optionen | Beschreibung |
| --- | --- |
| Profil veröffentlichen | Wählen Sie aus der Dropdown-Liste die von Ihrem Administrator konfigurierten Salesforce-Verbindungsprofile aus. Weitere Informationen dazu, wie Ihr Administrator ein Veröffentlichungsprofil erstellen kann, finden Sie in der Funktionsbeschreibung **Editor Settings** im Abschnitt [Left Panel](./web-editor-features.md#id2051EA0M0HS) . |
| Record Type | Verwenden Sie das Dropdown-Menü, um unter den in Salesforce eingerichteten Datensatztypen gemäß den Sichtbarkeitseinstellungen auf Grundlage Ihres Benutzerprofils auszuwählen. Salesforce-Datensatztypen bieten die Möglichkeit, viele Datensätze eines Typs für dieses Objekt zu gruppieren. Sie legen die Organisation Ihrer Veröffentlichung fest. Beispielsweise können Sie den häufig gestellten Fragedatentyp auswählen und gemäß dem Seitenlayout und den Feldern der häufig gestellten Fragen veröffentlichen. |
| Artikel-Inhaltsfeld | Sie können für jede Datensatztyp-Vorlage unterschiedliche Felder und ein eindeutiges Layout verwenden. Verwenden Sie diese Felder, um je nach Artikeltyp spezifische Informationen einzugeben. Sie können beispielsweise den Titel, die Antwort und die Gleichung eines FAQ-Artikels anzeigen. |
| Kategorien | Wählen Sie im Dropdown-Menü eine Kategorie aus, um die Themen des Inhaltsverzeichnisses in dieser Kategorie auf der Salesforce-Site zu veröffentlichen. |

Sie können auch die folgenden Optionen in den Salesforce- und ServiceNow-Vorgaben anzeigen:

| Optionen | Beschreibung |
| --- | --- |
| Entfernen Sie die Überschrift des Themas aus dem Artikeltext. | Wählen Sie diese Option aus, um die Themenüberschrift aus dem Artikel in der veröffentlichten Ausgabe zu entfernen. |
| Als Entwurf hochladen | Wählen Sie diese Option aus, um das Thema hochzuladen, um es als Entwurf freizugeben, bevor es für die Benutzer verfügbar gemacht wird. |
| Bilder hochladen | Wählen Sie diese Option aus, wenn Bilder in Themen in die veröffentlichte Ausgabe aufgenommen werden sollen. |
| Hochladen verknüpfter Dokumente | Aktivieren Sie diese Option, um die in Themen verknüpften Dokumente in die veröffentlichte Ausgabe einzuschließen. |


### Adobe Experience Manager

>[!NOTE]
>
>Sie können die Vorgabe der Adobe Experience Manager Knowledge Base verwenden, wenn Ihr Administrator sie konfiguriert hat. Weitere Informationen finden Sie unter [Artikelbasierte Veröffentlichung im Web-Editor](../install-guide/configure-article-based-publishing.md) im Installations- und Konfigurationshandbuch.

| Adobe Experience Manager-Optionen | Beschreibung |
| --- | --- |
| Artikelpfad verwenden | Wählen Sie diese Option aus, um den **Artikelpfad** des Ordners anzuzeigen, der die Knowledge Base-Vorlagen enthält. |
| Artikelpfad | Dieses Feld wird angezeigt, wenn Sie die Option **Artikelpfad verwenden** auswählen. Suchen Sie nach der Knowledge Base-Site in Ihrem Adobe Experience Manager-Repository, in dem die Ausgabe gespeichert ist. |
| Site | Verwenden Sie dieses Feld, um die erforderliche Adobe Experience Manager-Wissensdatenbank auszuwählen. Sie können Wissensdatenbanken auf der Adobe Experience Manager-Site konfigurieren, um den Inhalt basierend auf den Berechtigungen zu speichern. Die Artikel aus dieser DITA-Karte können in diesen Wissensdatenbanken veröffentlicht werden. |
| Kategorie | Wählen Sie im Dropdown-Menü eine Kategorie aus, um die Themen des Inhaltsverzeichnisses in dieser Kategorie auf der Adobe Experience Manager-Site zu veröffentlichen. |
| Vorlage für Abschnitte und Artikelvorlagen | Dies sind die Strukturkomponenten, mit denen der Inhalt Ihrer Ausgabe organisiert wird. Diese sind in der Adobe Experience Manager Site-Vorlage vordefiniert. |
| Arbeitsablauf nach der Erstellung | Wenn Sie diese Option auswählen, wird eine neue Dropdown-Liste für den Arbeitsablauf nach der Generierung angezeigt, die alle in Adobe Experience Manager konfigurierten Arbeitsabläufe enthält. Sie müssen einen Workflow auswählen, der nach Abschluss des Workflows zur Generierung der Ausgabe ausgeführt werden soll.<br>Erfahren Sie im Installations- und Konfigurationshandbuch mehr über das Anpassen des Workflows für die Generierung nach der Ausgabe [.](../install-guide/customize-workflows.md#id17A6GI004Y4) |

>[!TIP]
> 
>Wählen Sie das Aktualisierungssymbol **Aktualisieren** ![](images/navtitle-refresh-icon.svg) aus, um die entsprechenden Vorlagen in den Feldern gemäß der von Ihnen ausgewählten Knowledge Base-Vorlage zu füllen.

### Artikel

Auf dieser Registerkarte wird der Baum oder die hierarchische Ansicht der Karte angezeigt. Wählen Sie die Themen aus, die Sie in einer Wissensdatenbank veröffentlichen möchten. Erweitern Sie einen Inhaltsverzeichnis-Knoten und wählen Sie die Themen aus, die Sie veröffentlichen möchten.

**Übergeordnetes Thema:** [Grundlegendes zu den Ausgabevorgaben](generate-output-understand-presets.md)
