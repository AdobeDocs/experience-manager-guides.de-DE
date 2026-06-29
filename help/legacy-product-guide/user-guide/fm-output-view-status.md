---
title: Anzeigen des Status der Ausgabegenerierungsaufgabe
description: Anzeigen der Ausgabegenerierungswarteschlange von FrameMaker-Dokumenten. Erfahren Sie, wie Sie den Status einer Ausgabegenerierungsaufgabe anzeigen.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
TQID: https://experienceleague.adobe.com/FP5RxNtyWcdS-xpw2Atttt3x6DHx73Ljv-Ym91IxY5s
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 7ba2ad081f90fcbd38c7b34524a9ed1378e64f0d
workflow-type: tm+mt
source-wordcount: 544
ht-degree: 0%

---

# Anzeigen des Status der Ausgabegenerierungsaufgabe {#viewing_output_history}

Nachdem Sie die Ausgabegenerierungsaufgabe für ein FrameMaker-Dokument initiiert haben, sendet AEM Guides diese Aufgabe an die Ausgabegenerierungswarteschlange. Diese Warteschlange wird in Echtzeit aktualisiert und zeigt den Status jeder Ausgabegenerierungsaufgabe in der Warteschlange an.

Führen Sie die folgenden Schritte aus, um die Ausgabegenerierungswarteschlange anzuzeigen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem FrameMaker-Dokument, für das Sie den Status der Ausgabegenerierung überprüfen möchten, und klicken Sie darauf.

1. Klicken Sie auf Ausgaben.

   ![](images/output-queued-fm.png){width="800"}

1. Die Seite „Ausgaben“ ist in zwei Teile unterteilt:

   - **Ausgänge in der Warteschlange:**

     Listet die Ausgaben auf, die entweder auf die Generierung warten oder sich im Generierungsprozess befinden. Sie finden auch die Einstellung für die Ausgabegenerierung oder die Voreinstellung für die Aufgabe in der Warteschlange, den Typ, den Benutzer, der die Aufgabe initiiert hat, den Zeitpunkt, seit dem die Aufgabe in die Warteschlange gestellt wird, und den aktuellen Status.

   - **Erzeugte Ausgaben**

     Listet die abgeschlossenen Ausgabeaufgaben auf. Auch hier ähneln die Informationen in diesem Abschnitt den Ausgaben in der Warteschlange, mit dem einzigen Unterschied der Erzeugungszeit für die Ausgabe.

     In dieser Liste sind möglicherweise Aufgaben enthalten, die erfolgreich ausgeführt wurden, oder Aufgaben, bei denen ein Fehler aufgetreten ist. Für die erfolgreich abgeschlossenen Aufgaben erstellt der Veröffentlichungsprozess eine Protokolldatei \(logs.txt\), auf die Sie zugreifen können, indem Sie auf den Link in der Spalte Generiert unter klicken.

> **Definieren von Attributen für mehrere Zellen, die gesamte Zeile oder Spalte einer Tabelle**
>
> Sie können Attribute auf Zellen-, Zeilen- oder Spaltenebene definieren
>
> <details>
>&gt; <summary>Schritte anzeigen</summary>
>
> Sie können auch Attribute für mehrere Zellen, die gesamte Zeile oder Spalte einer Tabelle definieren. Um beispielsweise eine Tabellenzelle auszurichten, ziehen Sie die gewünschte Zelle und wählen Sie sie aus. Im Bedienfeld Inhaltseigenschaften (rechts) ändert sich die Eigenschaft **Typ** in **Eintrag**.
>
> 1. Wählen **Abschnitt „Attribute** die Option **+Hinzufügen**.
> 1. Wählen Sie das `@valign` Attribut aus der Dropdown **Liste „Attribut** aus.
> 1. Wählen Sie aus der Dropdown-Liste Wert die gewünschte Textausrichtung aus, die Sie auf die ausgewählten Tabellenzellen anwenden möchten.
> 1. Wählen Sie **Hinzufügen.**
>
> ![](images/align-table-cell_cs.png)
>
> </details>



**Attribute für mehrere Zellen, die gesamte Zeile oder Spalte einer Tabelle definieren**

Sie können Attribute auf Zellen-, Zeilen- oder Spaltenebene definieren.

<details>
<summary>Schritte anzeigen</summary>

Sie können auch Attribute für mehrere Zellen, die gesamte Zeile oder Spalte einer Tabelle definieren. Um beispielsweise eine Tabellenzelle auszurichten, ziehen Sie die gewünschte Zelle und wählen Sie sie aus. Im Bedienfeld Inhaltseigenschaften (rechts) ändert sich die Eigenschaft **Typ** in **Eintrag**.

1. Wählen **Abschnitt „Attribute** die Option **+Hinzufügen**.
1. Wählen Sie das `@valign` Attribut aus der Dropdown **Liste „Attribut** aus.
1. Wählen Sie aus der Dropdown-Liste Wert die gewünschte Textausrichtung aus, die Sie auf die ausgewählten Tabellenzellen anwenden möchten.
1. Wählen Sie **Hinzufügen.**

   ![](images/align-table-cell_cs.png)

   </details>

>[!BEGINSHADEBOX]
>
> **Definieren von Attributen für mehrere Zellen, die gesamte Zeile oder Spalte einer Tabelle**
>
> Sie können Attribute auf Zellen-, Zeilen- oder Spaltenebene definieren.
>
> <details>
>&gt; <summary>Schritte anzeigen</summary>
>
> Sie können auch Attribute für mehrere Zellen, eine ganze Zeile oder eine Spalte einer Tabelle definieren. Um beispielsweise eine Tabellenzelle auszurichten, ziehen Sie die gewünschte Zelle und wählen Sie sie aus. Im Bedienfeld Inhaltseigenschaften (rechts) ändert sich die Eigenschaft **Typ** in **Eintrag**.
>
> 1. Wählen **Abschnitt „Attribute** die Option **+Hinzufügen**.
> 1. Wählen Sie das `@valign` Attribut aus der Dropdown **Attribut** aus.
> 1. Wählen Sie im **Wert** die gewünschte Textausrichtung aus.
> 1. Wählen Sie **Hinzufügen** aus.
>
> ![](images/align-table-cell_cs.png)
>
> </details>
>
>[!ENDSHADEBOX]




**Übergeordnetes Thema:**&#x200B;[&#x200B; Ausgabe von FrameMaker-Dokumenten generieren](fm-output-generatation.md)

