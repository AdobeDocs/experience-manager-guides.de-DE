---
title: Native PDF | Variablen in der PDF-Ausgabe verwenden
description: Verwenden von Variablen in der PDF-Ausgabe und in den Ausgabevorlagen
source-git-commit: f1fd9c9e3fd3f228feeff469d04221fc3b0ab30f
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variablen in der PDF-Ausgabe

Ein Variable ist ein Name-Wert-Paar von Daten, das als wiederverwendbare Information dient. Dadurch ist Ihr Inhalte portabel und einfach zu aktualisieren. Wenn Sie eine Variable oder ihren Wert ändern, wird jeder Vorkommen dieser Variable oder dieses Werts aktualisiert.



## Neue Variable erstellen

Führen Sie die folgenden Schritte aus, um eine Variable zu erstellen:

![Neue Variable erstellen](assets/add-variable-default.png){width="800" align="left"}

*Erstellen Sie Variablen und definieren Sie Werte für sie.*


1. Navigieren Sie im Web-Editor zum **Ausgabe** Registerkarte.
1. Auswählen **Variablen** <img alt= "Variablensymbol" src="./assets/variables-icon.svg" width="25"> im linken Bereich.
1. Auswählen **Bearbeiten** <img alt= "Stiftsymbol bearbeiten" src="./assets/edit_pencil_icon.svg" width="25"> , um die **Variablen** Editor.
Die Variablen sind alphabetisch geordnet.
1. Geben Sie den Namen Variable in die Spalte &quot;Name&quot; und seinen Wert in die **** Spalte &quot;**Wert**&quot; ein.
   >[!TIP]
   >
   >Sie können einen beliebigen HTML Inhalte als Variable Wert verwenden, um den Variable Wert in einer bestimmten Formatierung anzuzeigen. Sie können dem Wert Variable z. B. eine `<b>` Tag hinzufügen, um den Wert **Experience Manager Leitfäden** fett gedruckt anzuzeigen. Sie können auch Bilder aus dem Repository als Werte hinzufügen.

1. Auswählen **Variable hinzufügen** <img alt= "Symbol &quot;Hinzufügen&quot;" src="./assets/add-icon.svg" width="25"> um eine neue Variable hinzuzufügen. Sie können keine Variable mit demselben Namen wie eine vorhandene Variable erstellen. Es wird ein Fehler angezeigt.

   >[!NOTE]
   >
   >Wenn Sie nicht **Variable hinzufügen** <img alt= "Symbol &quot;Hinzufügen&quot;" src="./assets/add-icon.svg" width="25">, wird die Variable nicht erstellt und der Liste hinzugefügt.

Auf diese Weise können Sie Variablen mit Standardwerten erstellen. Zum Beispiel:
* ProductName: Experience Manager-Handbücher
* VersionNumber: 2300
* Releasedatum: 01.01.2023


### Bearbeiten einer Variablen

Sie können eine Variable auf zwei Arten bearbeiten:

**Im Bedienfeld &quot;Variablen&quot;auf der linken Seite**

1. Wählen Sie eine Variable in der **Variablen** Bedienfeld.
1. Bewegen Sie den Mauszeiger über die Variable, um die **Optionen** und wählen Sie anschließend die **Bearbeiten** -Option.
1. Im **Variable bearbeiten** können Sie den Standardwert der ausgewählten Variablen bearbeiten.
1. Klicken Sie auf **Fertig**.

**Im Variableneditor**

1. Auswählen **Variablen** <img alt= "Variablensymbol" src="./assets/variables-icon.svg" width="25"> im linken Bereich.
1. Auswählen **Bearbeiten** <img alt= "Stiftsymbol bearbeiten" src="./assets/edit_pencil_icon.svg" width="25"> , um die **Variablen** Bearbeiter zu öffnen.

1. **Im Variablen** Bearbeiter können Sie den Wert der ausgewählten Variable bearbeiten.

Sie müssen alle Änderungen, die **Sie im Variablen** Bearbeiter vornehmen, speichern, um sie im **Variablen** Bedienfeld auf der linken Seite zu Ansicht.

>[!NOTE]
>
> Wenn Sie einen Variable Wert bearbeiten, aktualisiert Adobe Experience Manager Guides gleichzeitig alle Verweise, sofern zutreffend.

### Search und Vorschau einer Variable

Sie können den Wert einer Variablen durchsuchen und in der Vorschau anzeigen. Geben Sie eine Zeichenfolge in das Suchfeld der **Variablen** Bedienfeld. Die Suche basiert sowohl auf dem Variablennamen als auch auf dem zugehörigen Wert.
Sie können eine Variable auf zwei Arten in der Vorschau anzeigen:

In der Vorschau der Variablen wird der Standardwert angezeigt. Wenn Sie beispielsweise den Standardwert der Variable ProductName als &quot;Adobe Experience Manager Guides&quot;definiert haben, wird dieser Wert in der Vorschau angezeigt.

**Im Bedienfeld &quot;Variablen&quot;auf der linken Seite**


1. Wählen Sie eine Variable in der **Variablen** Bedienfeld.
1. Bewegen Sie den Mauszeiger über die Variable, um die **Optionen** und wählen Sie anschließend die **Vorschau** -Option.

![Variablenvorschau im Variablenbedienfeld](assets/variables-panel-preview-default.png){width="550" align="left"}

*Vorschau des Standardwerts für eine Variable*

**Im Variableneditor**

1. Bewegen Sie den Mauszeiger über die Variable in der Liste, um die **Optionen** Menü.
1. Wählen Sie **Vorschau**.




### Variable duplizieren

Sie können eine Variable duplizieren und den Wert entsprechend Ihren Anforderungen ändern.


1. Bewegen Sie den Mauszeiger über die Variable im Liste, um das **Menü &quot;Optionen** &quot; zu Ansicht.
1. Wählen Sie **Duplizieren**.

Der Standardname der Variablen lautet `<selected variable name>` (z. B. &quot;sample&quot;). Sie können den Namen entsprechend Ihren Anforderungen ändern.

### Löschen einer Variablen

Sie können eine Variable auf zwei Arten löschen:

**Im Bedienfeld &quot;Variablen&quot;auf der linken Seite**

1. Wählen Sie eine Variable in der **Variablen** Bedienfeld.
1. Bewegen Sie den Mauszeiger über die Variable, um die **Optionen** und wählen Sie anschließend die **Löschen** -Option.

**Im Variableneditor**

1. Bewegen Sie den Mauszeiger über die Variable in der Liste, um die **Optionen** Menü.
1. Auswählen **Löschen** -Option.

Die Variable wird aus allen Variablensätzen gelöscht.

## Variablensätze für die Ausgabevorgaben

Adobe Experience Manager Guides unterstützt auch Variable-Sets, mit denen Sie Ihren Variablen alternative Werte zuweisen können. Ein Firma kann beispielsweise zwei Produkte, A und B, verkaufen. Für jeden von ihnen gibt es unterschiedliche Spezifikationen. Zu diesen Spezifikationen können beispielsweise der Produktname, die Versionsnummer und das Veröffentlichungsdatum gehören. Es kann andere Unterschiede beim Branding geben. Wenn Sie Variable definieren, definieren Sie unterschiedliche Werte für Ihre Variablen. Wenn Sie die Ausgabe generieren, wählen Sie den entsprechenden Variablensatz aus und erstellen die erforderliche Ausgabe.

### Konfigurieren von Variablensätzen

Sie müssen Variablensätze konfigurieren, bevor Sie ihnen Variablen hinzufügen.



1. Auswählen **Einstellungen** <img alt= "Symbol Einstellungen" src="./assets/settings-icon.svg" width="25"> , um die **Konfigurieren von Variablensätzen** Dialogfeld.
   ![Variablensatz konfigurieren](assets/configure-variable-set.png){width="550" align="left"}
1. Geben Sie den Namen des Variablensatzes in die **Name** Spalte.
1. Auswählen **Variable hinzufügen** <img alt= "Symbol &quot;Hinzufügen&quot;" src="./assets/add-icon.svg" width="25"> um einen neuen Variablensatz hinzuzufügen. Die Variablensätze werden alphabetisch aufgelistet.
1. Sie können **Löschen** um einen Variablensatz zu entfernen.

### Variablensätze

Alle Variablensätze haben dieselben Variablen, können aber unterschiedliche Werte aufweisen.

Sie können die Werte für einen bestimmten Variablensatz anzeigen, bearbeiten und in der Vorschau anzeigen. Wählen Sie einen Variablensatz aus dem **Variablensätze** Dropdown. Die Werte werden entsprechend dem ausgewählten Variablensatz angezeigt.
Wenn Sie die Werte für die Variablen in bestimmten Variablensätzen bearbeiten, werden die Standardwerte überschrieben und die Werte des ausgewählten Variablensatzes geändert.
Sie können beispielsweise die folgenden Werte für die Variablensätze festlegen: *Adobe-set1* und *Adobe-set2* .


**Variable festgelegt 1**: *Adobe-set1*

* ProductName: ProductA
* VersionNumber: 2311
* Releasedatum: 20.11.2023


**Variable festgelegt 2**: *Adobe-set2*

* ProductName: ProductB
* VersionNumber: 2310
* Releasedatum: 07.09.2023

Jede neue Variable wird zu allen Variablensätzen hinzugefügt. Wenn Sie eine Variable löschen oder duplizieren, wird sie für alle Variablensätze aktualisiert.

Sie können auch eine Vorschau der Werte für einen Variablensatz anzeigen.
Beispiel: für den Variablensatz *Adobe-Set1* festgelegt haben, haben Sie den Wert der Variable ProductName als &quot;ProductA&quot;definiert und dann wird dieser Wert in der Vorschau im Variableneditor angezeigt.

![Variablenvorschau im Variableneditor](assets/variables-editor-preview.png){width="550" align="left"}

*Vorschau des Werts, den Sie im ausgewählten Variablensatz definiert haben*

### Den Wert einer Variablen zurücksetzen

Wenn Sie den Wert bearbeitet haben, können Sie auch eine Variable auf den Standardwert zurücksetzen.
Zurücksetzen <img alt= "Zurücksetzen-Symbol" src="./assets/application-variable-revert.svg" width="25"> für eine Variable mit einem geänderten Wert angezeigt.
Sie können beispielsweise den Wert für die Variable ProductName auf den Standardwert Experience Manager Guides zurücksetzen.

## Variablen in nativen PDF-Vorlagen verwenden

Sie können Variablen hinzufügen, während Sie die Ausgabe Ihrer Produktdokumente generieren, um sie portabel und einfach zu aktualisieren. Sie können diese Variablen in das Seitenlayout einfügen, das auf den verschiedenen Seiten in Ihren Dokumenten angezeigt wird. Sie können beispielsweise die Variable ProductName hinzufügen, die im Kopfzeilenbereich des Seitenlayouts (oder in einem anderen Teil wie der Fußzeile oder dem Hauptteil) angezeigt wird.



So fügen Sie eine Variable wie Ihren Produktnamen in den Kopfzeilenbereich ein:
1. Öffnen Sie das gewünschte Seitenlayout zur Bearbeitung.

   >[!NOTE]
   >
   > Ansicht [Seitenlayout anpassen](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) zum Öffnen eines Seitenlayouts zur Anpassung oder Bearbeitung.

1. Wählen Sie die Kopfzeile aus, damit das Einfügen einer Variablen aktiviert wird.

1. Sie können die Variable auf zwei Arten einfügen:

   **Im Variablen Bedienfeld auf der linken Seite**

   * Ziehen Sie eine Variable aus dem **Variablen** Bedienfeld in den Kopfzeilenbereich.

   **In der Symbolleiste**

   1. Auswählen **Variable/Felder einfügen** <img alt= "Variablensymbol" src="./assets/variables-icon.svg" width="25">.
   1. Im **Variable** wählen Sie den Namen der Variablen aus, die in den Kopfzeilenbereich eingefügt werden soll.
   1. Sie können auch die Suchzeichenfolge in das Textfeld eingeben. Die Variablennamen, die die angegebene Zeichenfolge enthalten, werden gefiltert und in der Liste angezeigt. Die ausgewählte Variable wird in den Kopfzeilenbereich eingefügt. Sie können den Standardwert der Variablen anzeigen.
   1. Um eine Variable zu ersetzen, doppelklicken Sie auf den Variablenwert und wählen Sie eine andere Variable aus der **Variable** Dialogfeld. Die -Variable wird ersetzt.


## Generieren einer PDF-Ausgabe mit Variablen

Sie können die PDF-Ausgabe mit den Werten verschiedener Variablen generieren. Wählen Sie vor dem Generieren des Layouts einen Variablensatz aus der **Variablensatz** Dropdown-Liste, um die zugehörigen Werte auszuwählen.

![Dropdown-Liste für Variableneinstellungen](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Wählen Sie in der Dropdown-Liste in der Ausgabevorgabe einen Variable-Satz aus, den Sie zum Generieren der PDF-Ausgabe verwenden möchten.*

>[!NOTE]
>
> Sie können auch (Standardmäßig) aus der Dropdown-Liste auswählen, um die Standardwerte für alle Variablen zu veröffentlichen.

Je nach ausgewähltem Variablensatz erhalten Sie eine Ausgabe, die den im Variablensatz definierten Variablenwerten entspricht. Wenn Sie beispielsweise den Variablensatz auswählen *Adobe-set1* angezeigt, zeigt Ihre Ausgabe die in diesem Satz definierten Werte der Variablen an.


<img src="assets/variable-pdf-output.png" alt="PDF-Ausgabe mit Variablen" width="500" border="2px">

*Generieren Sie die PDF-Ausgabe mithilfe von Variablen im Seitenlayout.*

Sie können die Werte für jeden beliebigen Variablensatz auch schnell aktualisieren, wann immer dies erforderlich ist, und die Ausgabe neu generieren. Wenn Sie beispielsweise die Details für eine Version aktualisieren müssen, können Sie den Wert der Version in der Variablen VersionNumber aktualisieren und die Ausgabe neu generieren.


