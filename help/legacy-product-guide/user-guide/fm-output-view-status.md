---
title: Anzeigen des Status der Ausgabegenerierungsaufgabe
description: Anzeigen der Ausgabegenerierungswarteschlange von FrameMaker-Dokumenten. Erfahren Sie, wie Sie den Status einer Ausgabegenerierungsaufgabe anzeigen.
feature: Publishing FrameMaker Documents
role: User
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
source-git-commit: 86fb9cc382689beb493847cb506c788199a2d3f4
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# Anzeigen des Status der Ausgabegenerierungsaufgabe {#viewing_output_history}

Nachdem Sie die Ausgabegenerierungsaufgabe für ein FrameMaker-Dokument initiiert haben, sendet AEM Guides diese Aufgabe an die Ausgabegenerierungswarteschlange. Diese Warteschlange wird in Echtzeit aktualisiert und zeigt den Status jeder Ausgabegenerierungsaufgabe in der Warteschlange an.

Führen Sie die folgenden Schritte aus, um die Ausgabegenerierungswarteschlange anzuzeigen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu und klicken Sie auf FrameMaker-Dokument, für das Sie den Status der Ausgabegenerierung überprüfen möchten.

1. Klicken Sie auf Ausgaben.

   ![](images/output-queued-fm.png){width="800" align="left"}

1. Die Seite „Ausgaben“ ist in zwei Teile unterteilt:

   - **Ausgänge in der Warteschlange:**

     Listet die Ausgaben auf, die entweder auf die Generierung warten oder sich im Generierungsprozess befinden. Sie finden auch die Einstellung für die Ausgabegenerierung oder die Voreinstellung für die Aufgabe in der Warteschlange, den Typ, den Benutzer, der die Aufgabe initiiert hat, den Zeitpunkt, seit dem die Aufgabe in die Warteschlange gestellt wird, und den aktuellen Status.

   - **Erzeugte Ausgaben**

     Listet die abgeschlossenen Ausgabeaufgaben auf. Auch hier ähneln die Informationen in diesem Abschnitt den Ausgaben in der Warteschlange, mit dem einzigen Unterschied der Erzeugungszeit für die Ausgabe.

     In dieser Liste sind möglicherweise Aufgaben enthalten, die erfolgreich ausgeführt wurden, oder Aufgaben, bei denen ein Fehler aufgetreten ist. Für die erfolgreich abgeschlossenen Aufgaben erstellt der Veröffentlichungsprozess eine Protokolldatei \(logs.txt\), auf die Sie zugreifen können, indem Sie auf den Link in der Spalte Generiert unter klicken.


**Übergeordnetes Thema:**[ Ausgabe von FrameMaker-Dokumenten generieren](fm-output-generatation.md)
