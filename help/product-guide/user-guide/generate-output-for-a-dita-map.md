---
title: Ausgabe generieren
description: Generieren Sie eine Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole und das Zuordnungs-Dashboard in AEM Guides.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
source-git-commit: 358d38ca761661eaee7aeac2cc7d46c53105c543
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Ausgabe generieren

Es gibt zwei Möglichkeiten, eine Ausgabe für eine DITA-Zuordnung zu generieren:

- [Generieren einer Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole](#generate-output-for-a-dita-map-from-the-map-console)
- [Generieren einer Ausgabe für eine DITA-Zuordnung über das Zuordnungs-Dashboard](#generate-output-for-a-dita-map-from-the-map-dashboard)

## Generieren einer Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole

Führen Sie die folgenden Schritte aus, um mithilfe der Zuordnungskonsole eine Ausgabe für eine DITA-Zuordnung zu generieren:

1. [Öffnen Sie eine Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).
2. Die DITA-Zuordnungskonsole wird mit der Liste der **Ausgabevorgaben“ angezeigt** die für die Generierung der Ausgabe verfügbar sind.

3. Öffnen Sie die Vorgabe, die Sie für die Generierung der Ausgabe verwenden möchten, und wählen Sie **Ausgabe generieren** aus, um den Generierungsprozess zu starten.

   <img src="images/generate-output-pdf.png" alt="Registerkarte Metadaten" width="600">

   Bewegen Sie alternativ den Mauszeiger über die Vorgabe und wählen **Generieren** aus dem Kontextmenü der Vorgabe aus.


   <img src="images/generate-preset-map-console.png" alt="Registerkarte Metadaten" width="600">

Nachdem die Ausgabegenerierung abgeschlossen ist, wählen Sie **Ausgabe anzeigen** aus, um die Ausgabe anzuzeigen.

Ein **Erfolgreich**-Dialogfeld wird unten rechts im Bildschirm angezeigt.

Wenn eine Ausgabe nicht erfolgreich ist, wird die folgende Fehlermeldung angezeigt.

<img src="images/error-log.png" alt="Fehlerprotokoll" width="250">

Um das Fehlerprotokoll anzuzeigen, wählen Sie **Verwerfen**, bewegen Sie den Mauszeiger über die ausgewählte Vorgabenregisterkarte und wählen Sie **Protokoll anzeigen** aus dem vordefinierten Kontextmenü aus.

## Generieren einer Ausgabe für eine DITA-Zuordnung über das Zuordnungs-Dashboard

Führen Sie die folgenden Schritte aus, um mithilfe des Zuordnungs-Dashboards eine Ausgabe für eine DITA-Zuordnung zu generieren:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Zuordnungsdatei, die Sie veröffentlichen möchten, und wählen Sie sie aus.

   Die DITA-Zuordnungskonsole wird mit der Liste der verfügbaren Ausgabevorgaben angezeigt, um eine Ausgabe zu generieren.

1. Wählen Sie eine oder mehrere Ausgabevorgaben aus, die Sie zum Generieren der Ausgabe verwenden möchten.

   ![](images/generate-multiple-outputs-uuid.png){align="left"}

1. Wählen Sie das **Generieren**, um den Ausgabegenerierungsprozess zu starten.


Sie können den aktuellen Status der Ausgabegenerierungsanfrage auf der Registerkarte **Ausgaben** einsehen. Weitere Informationen finden Sie unter [Anzeigen des Status der Aufgabe zur Ausgabenerstellung](./generate-output-manage-process.md#view-the-status-of-the-output-generation-task).

>[!IMPORTANT]
>
> Wenn sich ein Ausgabegenerierungsprozess für eine Voreinstellung entweder in der Warteschlange befindet oder in Bearbeitung ist, können Sie für dieselbe Voreinstellung keine andere Ausgabegenerierungsaufgabe starten.

Sie können auch die AEM Sites-Ausgabe für ein oder mehrere Themen oder die gesamte DITA-Zuordnung über die Zuordnungskonsole generieren. Weitere Informationen finden Sie unter [Generieren von Wissensdatenbankausgaben](web-editor-article-publishing.md#id218CK0U019I).

## Zusammenführen verschiedener Themen innerhalb einer DITA-Zuordnung mithilfe des `chunk` Attributs

Eine DITA-Zuordnung kann verschiedene Thementypen wie Referenz, Konzept und Aufgabe enthalten. Mit dem Attribut `chunk=to-content` können Sie diese Themen zusammenführen, um eine Einzelseitenausgabe in AEM Sites zu generieren. Um das zusammengeführte Thema jedoch ordnungsgemäß zu veröffentlichen, stellen Sie sicher, dass Ihr Administrator den richtigen XML-Katalog in den DITA-Profilen konfiguriert hat.

Das System erfordert eine öffentliche ID mit dem Schlüsselwort `composite` im XML-Katalog, um die entsprechende DTD-Regel korrekt zu identifizieren und anzuwenden.
Diese Konfiguration ist standardmäßig im Standard-XML-Katalog enthalten. Wenn Sie jedoch einen benutzerdefinierten XML-Katalog verwenden, stellen Sie sicher, dass Ihr Administrator diese öffentliche ID zur Konfiguration hinzugefügt hat. Ohne sie wird das zusammengeführte Thema möglicherweise nicht ordnungsgemäß veröffentlicht.

Weitere Informationen zur Verwendung der öffentlichen ID und System-ID in Ihren benutzerdefinierten DTDs/XSDs finden Sie unter [DITA-Spezialisierung integrieren](../cs-install-guide/dita-ot-specialization.md#integrate-dita-specialization-id211mb0e00xa).



**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
