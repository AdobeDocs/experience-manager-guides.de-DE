---
title: Native PDF | Verwenden von Variablen in der PDF-Ausgabe
description: Verwenden von Variablen in der PDF-Ausgabe und in den Ausgabevorlagen
feature: Output Generation
role: Admin
level: Experienced
exl-id: 96e54aee-52df-4af1-97fd-34986f553be4
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variablen in der PDF-Ausgabe

Ein Variable ist ein Name-Wert-Paar von Daten, das als wiederverwendbare Information dient. Dadurch ist Ihr Inhalte portabel und einfach zu aktualisieren. Wenn Sie eine Variable oder ihren Wert ändern, wird jeder Vorkommen dieser Variable oder dieses Werts aktualisiert.



## Neue Variable erstellen

Führen Sie die folgenden Schritte aus, um eine Variable zu erstellen:

![Neue Variable erstellen](assets/add-variable-default.png){width="800" align="left"}

*Erstellen von Variablen und Definieren von Werten dafür.*


1. Wechseln Sie im Web-Editor zur Registerkarte **Ausgabe** .
1. Wählen Sie **Variablen** <img alt= "Variablensymbol" src="./assets/variables-icon.svg" width="25"> im linken Bedienfeld.
1. Wählen Sie **Bearbeiten** aus <img alt= "Stiftsymbol bearbeiten" src="./assets/edit_pencil_icon.svg" width="25"> Sie den Editor **Variablen** öffnen.
Die Variablen sind alphabetisch geordnet.
1. Geben Sie den Namen Variable in die **Spalte &quot;Name** &quot; und seinen Wert in die **Spalte &quot;Wert** &quot; ein.
   >[!TIP]
   >
   >Sie können einen beliebigen HTML Inhalte als Variable Wert verwenden, um den Variable Wert in einer bestimmten Formatierung anzuzeigen. Sie können dem Wert Variable z. B. eine `<b>` Tag hinzufügen, um den Wert **Experience Manager Leitfäden** fett gedruckt anzuzeigen. Sie können auch Bilder aus dem Repository als Werte hinzufügen.

1. Wählen Sie **Variable hinzufügen** <img alt= "Symbol hinzufügen" src="./assets/add-icon.svg" width="25"> eine neue Variable hinzugefügt werden. Sie können keine Variable mit demselben Namen wie eine vorhandene Variable erstellen. Ein Fehler wird angezeigt.

   >[!NOTE]
   >
   >Wenn Sie nicht „Variable hinzufügen **auswählen** <img alt= "Symbol hinzufügen" src="./assets/add-icon.svg" width="25"> wird die Variable nicht erstellt und der Liste hinzugefügt.

Auf diese Weise können Sie Variablen mit Standardwerten erstellen. Zum Beispiel:
* Produktname: Experience Manager Guides
* Versionsnummer: 2300
* Veröffentlichungsdatum: 01/01/2023


### Bearbeiten einer Variablen

Sie haben zwei Möglichkeiten, um eine Variable zu bearbeiten:

**Im Variablenbedienfeld auf der linken Seite**

1. Wählen Sie eine Variable im **Variablen** aus.
1. Bewegen Sie den Mauszeiger über die Variable, um das Menü **Optionen** anzuzeigen, und wählen Sie dann die Option **Bearbeiten** aus.
1. Im Dialogfeld **Variable bearbeiten** können Sie den Standardwert der ausgewählten Variablen bearbeiten.
1. Klicken Sie auf **Fertig**.

**Aus dem Variablen-Editor**

1. Wählen Sie **Variablen** <img alt= "Variablensymbol" src="./assets/variables-icon.svg" width="25"> im linken Bedienfeld.
1. Wählen Sie **Bearbeiten** aus <img alt= "Stiftsymbol bearbeiten" src="./assets/edit_pencil_icon.svg" width="25"> , um die **Variablen** Bearbeiter zu öffnen.

1. **Im Variablen** Bearbeiter können Sie den Wert der ausgewählten Variable bearbeiten.

Sie müssen alle Änderungen, die **Sie im Variablen** Bearbeiter vornehmen, speichern, um sie im **Variablen** Bedienfeld auf der linken Seite zu Ansicht.

>[!NOTE]
>
> Wenn Sie einen Variable Wert bearbeiten, aktualisiert Adobe Experience Manager Guides gleichzeitig alle Verweise, sofern zutreffend.

### Search und Vorschau einer Variable

Sie können den Wert einer Variablen suchen und in der Vorschau anzeigen. Geben Sie eine Zeichenfolge in das Suchfeld des Bedienfelds &quot;**&quot;**. Es sucht sowohl basierend auf dem Variablennamen als auch auf seinem Wert.
Sie können eine Variable auf zwei Arten in der Vorschau anzeigen:

Die Vorschau der Variablen zeigt den Standardwert an. Wenn Sie beispielsweise den Standardwert der Variable „ProductName“ als &quot;Adobe Experience Manager Guides&quot; definiert haben, wird dieser Wert in der Vorschau angezeigt.

**Im Variablenbedienfeld auf der linken Seite**


1. Wählen Sie eine Variable im **Variablen** aus.
1. Bewegen Sie den Mauszeiger über die Variable, um das Menü **Optionen** anzuzeigen, und wählen Sie dann die Option **Vorschau** aus.

![Variablenvorschau im Variablenbedienfeld](assets/variables-panel-preview-default.png){width="550" align="left"}

*Vorschau des Standardwerts für eine Variable anzeigen.*

**Aus dem Variablen-Editor**

1. Bewegen Sie den Mauszeiger über die Variable in der Liste, um das Menü **Optionen** anzuzeigen.
1. Wählen Sie **Vorschau**.




### Duplizieren einer Variablen

Sie können eine Variable duplizieren und den Wert entsprechend Ihren Anforderungen ändern.


1. Bewegen Sie den Mauszeiger über die Variable im Liste, um das **Menü &quot;Optionen** &quot; zu Ansicht.
1. Wählen Sie **Duplizieren**.

Der Standardname der Variablen lautet `<selected variable name>` (z. B. „sample„). Sie können den Namen Ihren Anforderungen entsprechend ändern.

### Löschen einer Variablen

Sie haben zwei Möglichkeiten, um eine Variable zu löschen:

**Im Variablenbedienfeld auf der linken Seite**

1. Wählen Sie eine Variable im **Variablen** aus.
1. Bewegen Sie den Mauszeiger über die Variable, um das Menü **Optionen** anzuzeigen, und wählen Sie dann die Option **Löschen** aus.

**Aus dem Variablen-Editor**

1. Bewegen Sie den Mauszeiger über die Variable in der Liste, um das Menü **Optionen** anzuzeigen.
1. Wählen Sie **Option** Löschen“ aus.

Die Variable wird aus allen Variablensätzen gelöscht.

## Variablensätze für die Ausgabevorgaben

Adobe Experience Manager Guides unterstützt auch Variable-Sets, mit denen Sie Ihren Variablen alternative Werte zuweisen können. Ein Firma kann beispielsweise zwei Produkte, A und B, verkaufen. Für jeden von ihnen gibt es unterschiedliche Spezifikationen. Zu diesen Spezifikationen können beispielsweise der Produktname, die Versionsnummer und das Veröffentlichungsdatum gehören. Es kann noch andere Unterschiede im Branding geben. Wenn Sie Variable definieren, definieren Sie unterschiedliche Werte für Ihre Variablen. Beim Generieren der Ausgabe wählen Sie den entsprechenden Variablensatz aus und erzeugen die gewünschte Ausgabe.

### Konfigurieren von Variablensätzen

Sie müssen Variablensätze konfigurieren, bevor Sie Variablen zu ihnen hinzufügen.



1. Wählen Sie **Einstellungen** aus <img alt= "Einstellungssymbol" src="./assets/settings-icon.svg" width="25"> Sie das Dialogfeld **Variablensätze konfigurieren** öffnen.
   ![Variablensatz konfigurieren](assets/configure-variable-set.png){width="550" align="left"}
1. Geben Sie den Namen des Variablensatzes in die Spalte **Name** ein.
1. Wählen Sie **Variable hinzufügen** <img alt= "Symbol hinzufügen" src="./assets/add-icon.svg" width="25"> zum Hinzufügen eines neuen Variablensatzes. Die Variablensätze werden alphabetisch aufgelistet.
1. Sie können auf **Löschen** klicken, um einen Variablensatz zu entfernen.

### Vorgänge bei Variablensätzen

Alle Variablensätze haben dieselben Variablen, können aber unterschiedliche Werte haben.

Sie können die Werte für einen bestimmten Variablensatz anzeigen, bearbeiten und in der Vorschau anzeigen. Wählen Sie einen Variablensatz aus der Dropdown **Liste Variablensätze** aus. Die Werte werden entsprechend dem ausgewählten Variablensatz angezeigt.
Wenn Sie die Werte für die Variablen in bestimmten Variablensätzen bearbeiten, überschreibt es die Standardwerte und ändert die Werte des ausgewählten Variablensatzes.
Sie können beispielsweise die folgenden Werte für die Variablensätze festlegen: *Adobe-Set1* und *Adobe-Set2* .


**Variablensatz 1**: *Adobe-Set1*

* ProductName: ProductA
* Versionsnummer: 2311
* Veröffentlichungsdatum: 11/02/2023


**Variablensatz 2**: *Adobe-Set2*

* Produktname: Produkt B
* Versionsnummer: 2310
* Veröffentlichungsdatum: 09/07/2023

Jede neue Variable wird allen Variablensätzen hinzugefügt. Wenn Sie eine Variable löschen oder duplizieren, wird sie für alle Variablensätze aktualisiert.

Sie können auch eine Vorschau der Werte für einen Variablensatz anzeigen.
Für den Variablensatz *Adobe-Set1* haben Sie beispielsweise den Wert der Variable ProductName als „ProductA“ definiert. Anschließend wird dieser Wert im Variableneditor in der Vorschau angezeigt.

![Variablenvorschau im Variablen-Editor](assets/variables-editor-preview.png){width="550" align="left"}

*Vorschau des Werts anzeigen, den Sie im ausgewählten Variablensatz definiert haben.*

### Zurücksetzen des Werts einer Variablen

Wenn Sie den Wert bearbeitet haben, können Sie auch eine Variable auf den Standardwert zurücksetzen.
Zurücksetzen <img alt= "Symbol „Zurücksetzen“" src="./assets/application-variable-revert.svg" width="25"> wird für eine Variable mit einem geänderten Wert angezeigt.
Sie können beispielsweise den Wert für die Variable ProductName auf den Standardwert in den Experience Manager Guides zurücksetzen.

## Verwenden von Variablen in nativen PDF-Vorlagen

Sie können Variablen hinzufügen, während Sie die Ausgabe Ihrer Produktdokumente generieren, um sie portabel und einfach zu aktualisieren. Sie können diese Variablen in das Seiten-Layout einfügen, das auf den verschiedenen Seiten in Ihren Dokumenten angezeigt wird. Sie können beispielsweise die Variable ProductName hinzufügen, die im Kopfzeilenbereich des Seitenlayouts (oder in einem anderen Teil wie der Fußzeile oder dem Hauptteil) angezeigt wird.



Um eine Variable wie Ihren ProductName in den Kopfzeilenbereich einzufügen, führen Sie die folgenden Schritte aus:
1. Öffnen Sie das gewünschte Seiten-Layout zur Bearbeitung.

   >[!NOTE]
   >
   > Abschnitt [Anpassen eines Seiten-Layouts](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) zum Öffnen eines Seiten-Layouts zur Anpassung oder Bearbeitung anzeigen.

1. Wählen Sie die Kopfzeile aus, um das Einfügen einer Variablen zu aktivieren.

1. Sie können die Variable auf zwei Arten einfügen:

   **Im Variablen Bedienfeld auf der linken Seite**

   * Ziehen Sie eine Variable aus dem **Variablen** Bedienfeld in den Kopfzeilenbereich.

   **In der Symbolleiste**

   1. Wählen Sie **Variable/Felder einfügen** <img alt= "Variablensymbol" src="./assets/variables-icon.svg" width="25">.
   1. Wählen **im Dialogfeld** Variable“ den Namen der Variablen aus, um sie in den Kopfzeilenbereich einzufügen.
   1. Sie können die Suchzeichenfolge auch in das Textfeld eingeben. Die Variablennamen, die die angegebene Zeichenfolge enthalten, werden gefiltert und in der Liste angezeigt. Die ausgewählte Variable wird in den Kopfzeilenbereich eingefügt. Sie können den Standardwert der Variablen anzeigen.
   1. Um eine Variable zu ersetzen, doppelklicken Sie auf den Variablenwert und wählen Sie im Dialogfeld **Variable** eine andere Variable aus. Die Variable wird ersetzt.


## Erzeugen einer PDF-Ausgabe mit Variablen

Sie können die PDF-Ausgabe mit den Werten verschiedener Variablen generieren. Wählen Sie vor dem Generieren des Layouts einen Variablensatz aus der Dropdown **Liste „Variablensatz“ einer** aus, um dessen Werte auszuwählen.

![Dropdown „Variablensatz“](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Wählen Sie in der Dropdown-Liste in der Ausgabevorgabe einen Variable-Satz aus, den Sie zum Generieren der PDF-Ausgabe verwenden möchten.*

>[!NOTE]
>
> Sie können auch (Standardmäßig) aus der Dropdown-Liste auswählen, um die Standardwerte für alle Variablen zu veröffentlichen.

Je nach ausgewähltem Variablensatz erhalten Sie eine Ausgabe, die den im Variablensatz definierten Variablenwerten entspricht. Wenn Sie beispielsweise den Variablensatz *Adobe-Set1* auswählen, zeigt Ihre Ausgabe die Werte der Variablen an, wie in diesem Satz definiert.


<img src="assets/variable-pdf-output.png" alt="PDF-Ausgabe mit Variablen" width="500" border="2px">

*Generieren Sie die PDF-Ausgabe mithilfe von Variablen im Seiten-Layout.*

Sie können bei Bedarf auch schnell die Werte für jeden Variablensatz aktualisieren und die Ausgabe neu generieren. Wenn Sie beispielsweise die Details für eine Version aktualisieren müssen, können Sie den Wert der Version in der VersionNumber-Variablen aktualisieren und die Ausgabe neu generieren.
