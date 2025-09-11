---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides, Version Juli 2023
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen in der Version Juli 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: 4b907729-4fbf-48ed-a2e1-014bd1101c73
feature: What's New
role: Leader
source-git-commit: 7d0ae0f13ab77a10beb89fcb0d8592b05c3828bd
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---

# Neue Funktionen in der Version Juli 2023 von Adobe Experience Manager Guides as a Cloud Service

Dieser Artikel behandelt die neuen und erweiterten Funktionen in der Version Juli 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](release-notes-2023-7-0.md).

## Herstellen einer Verbindung zu einer Datenquelle und Einfügen von Daten in die Themen

Jetzt können Sie mithilfe von vorkonfigurierten Connectoren von AEM Guides schnell eine Verbindung zu Ihren Datenquellen herstellen. Wenn Sie eine Verbindung zu einer Datenquelle herstellen, können Sie Ihre Informationen mit der Quelle synchronisieren. Alle Aktualisierungen der Daten werden automatisch übernommen, was AEM Guides zu einem echten Content-Hub macht. Mit dieser Funktion sparen Sie Zeit und Mühe beim manuellen Hinzufügen oder Kopieren der Daten.

Jetzt ermöglicht AEM Guides Ihrem Administrator die Konfiguration der vorkonfigurierten Connectoren für JIRA- und SQL-Datenbanken (MySQL, PostgreSQL, SQL Server, SQLite). Sie können auch andere Connectoren hinzufügen, indem sie die Standardschnittstellen erweitern.

Nach dem Hinzufügen können Sie die konfigurierten Connectoren anzeigen, die unter dem Bedienfeld **Datenquellen** im Web-Editor aufgeführt sind.

![](assets/code-snippet-generator.png){width="300" align="left"}

Sie können einen Inhaltsfragment-Generator erstellen, um die Daten aus einer verbundenen Datenquelle abzurufen. Anschließend können Sie die Daten in Ihre Themen einfügen und bearbeiten.

Nachdem Sie einen Inhaltsfragment-Generator erstellt haben, können Sie ihn wiederverwenden, um die Daten in ein beliebiges Thema einzufügen. Weitere Informationen finden Sie unter [Einfügen eines Inhaltsausschnitts aus Ihrer Datenquelle](../user-guide/web-editor-content-snippet.md).



## Überprüfungsbereich zur Präsentation von Überprüfungsprojekten und der aktiven Überprüfungsaufgaben

Jetzt macht AEM Guides Ihre Rezensionen nahtloser. Sie enthält das Bedienfeld Überprüfungen im Web-Editor. Im Bedienfeld Überprüfungen werden alle Überprüfungsprojekte und die aktiven Überprüfungsaufgaben innerhalb der Überprüfungsprojekte angezeigt, an denen Sie beteiligt sind.

Als Autor können Sie mit dieser Funktion die Prüfungsaufgaben einfach öffnen, die Kommentare anzeigen und die Kommentare schnell in einer zentralen Ansicht bearbeiten.
![](assets/active-review-task-comments.png){width="800" align="left"}
Weitere Informationen finden Sie in der **Funktionsbeschreibung** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Verbesserungen der Zuordnungssammlung

Mit einer Zuordnungssammlung können Sie mehrere Zuordnungen organisieren und stapelweise veröffentlichen. An der Zuordnungssammlung wurden viele neue Verbesserungen vorgenommen:

- Jetzt können Sie auch native PDF-Ausgabevorgaben zu einer Zuordnungssammlung hinzufügen und sie zum Generieren der PDF-Ausgabe verwenden.
- Sie können die von Ihrem Administrator erstellten globalen und Ordnerprofilvorgaben anzeigen und sie zum Generieren der PDF-Ausgabe verwenden.
- Jetzt können Sie nicht nur eine einzelne Vorgabe auswählen, sondern auch alle Ordnerprofilvorgaben für eine DITA-Zuordnung in einem Schritt aktivieren.
  ![](assets/edit-map-collection.png){width="800" align="left"}

Weitere Informationen finden Sie unter [Zuordnungssammlung für die Ausgabegenerierung verwenden](../user-guide/generate-output-use-map-collection-output-generation.md).

## Zugriff auf temporäre HTML-Dateien beim Generieren der nativen PDF-Ausgabe

Jetzt können Sie mit AEM Guides die temporären HTML-Dateien herunterladen, die beim Generieren der nativen PDF-Ausgabe erstellt wurden. Wählen Sie in den Ausgabevorgabeneinstellungen die Option zum Herunterladen der temporären Dateien aus.  Mit AEM Guides können Sie dann die temporären Dateien herunterladen, die beim Generieren der Ausgabe mit dieser Vorgabe erstellt wurden.

Diese Funktion bietet bessere Einblicke in den Generierungsprozess mit Zugriff auf Zwischenstile und -Layouts und hilft Ihnen, Ihre CSS-Stile entsprechend Ihren Anforderungen zu korrigieren oder zu ändern.

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Weitere Informationen finden Sie unter [Erstellen einer PDF-](../web-editor/native-pdf-web-editor.md#create-output-preset)&quot;.

## Microservice-basierte Veröffentlichung zur Generierung von HTML5- und benutzerdefinierten Ausgaben

Der neue Publishing-Microservice ermöglicht es Ihnen, große Publishing-Workloads gleichzeitig auf AEM Guides as a Cloud Service auszuführen und die branchenführende Adobe I/O Runtime Server-lose Plattform zu nutzen. Jetzt können Sie mit dem Microservice auch die HTML5- und die benutzerdefinierte Ausgabe generieren.
Sie können mehrere Veröffentlichungsanfragen ausführen und eine verbesserte Leistung erhalten, um diese Ausgabeformate zu generieren.
Weitere Informationen finden Sie unter [Konfigurieren von Microservice-basierter Veröffentlichung für AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).

## Anzeigen von AEM Guides-Versionsdetails in den Informationen zu

Jetzt können Sie neben den Informationen **AEM** Info) auch die Versionsdetails von AEM Guides anzeigen. Sie können die aktuellen Versionsdetails in der Option **Info** der **Hilfe** auf der AEM-Navigationsseite anzeigen.

![](assets/about-aem-help.png){width="800" align="left"}
