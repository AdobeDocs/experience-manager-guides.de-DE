---
title: Status der Ausgabegenerierungsaufgabe anzeigen
description: Anzeigen der Ausgabegenerierungswarteschlange von FrameMaker-Dokumenten. Erfahren Sie, wie Sie den Status einer Ausgabegenerierungsaufgabe anzeigen können.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Status der Ausgabegenerierungsaufgabe anzeigen {#viewing_output_history}

Nachdem Sie die Ausgabegenerierungsaufgabe für ein FrameMaker-Dokument initiiert haben, sendet AEM Guides diese Aufgabe an die Ausgabegenerierungswarteschlange. Diese Warteschlange wird in Echtzeit aktualisiert und zeigt den Status jeder Ausgabegenerierungsaufgabe in der Warteschlange an.

Führen Sie die folgenden Schritte aus, um die Ausgabegenerierungswarteschlange anzuzeigen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zum Dokument FrameMaker , für das Sie den Status der Ausgabenerstellung überprüfen möchten, und klicken Sie darauf.

1. Klicken Sie auf Ausgaben.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. Die Seite &quot;Ausgaben&quot;ist in zwei Teile unterteilt:

   - **In die Warteschlange gestellte Ausgaben:**

     Listet die Ausgaben auf, die darauf warten, generiert zu werden oder sich im Generierungsprozess befinden. Sie finden außerdem die Einstellung zur Generierung der Ausgabe oder die Vorgabe, die für die in der Warteschlange befindliche Aufgabe verwendet wird, den Typ, den Benutzer, der die Aufgabe initiiert hat, die Zeit seit der Warteschlange der Aufgabe und den aktuellen Status.

   - **Erzeugte Ausgaben**

     Listet die abgeschlossenen Ausgabenaufgaben auf. Auch hier werden Informationen angezeigt, die dem Abschnitt &quot;In die Warteschlange gestellte Ausgaben&quot;ähneln, mit dem einzigen Unterschied zur Zeit der Ausgabenerstellung.

     In dieser Liste können Aufgaben aufgeführt sein, die erfolgreich ausgeführt wurden, oder Aufgaben, die fehlgeschlagen sind. Für die Aufgaben, die erfolgreich abgeschlossen wurden, erstellt der Veröffentlichungsprozess eine Protokolldatei \(logs.txt\), auf die über den Link in der Spalte Generiert am zugegriffen werden kann.


**Übergeordnetes Thema:**[ Ausgabe von FrameMaker-Dokumenten generieren](fm-output-generatation.md)
