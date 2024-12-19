---
title: Symbolleiste anpassen
description: Erfahren Sie, wie Sie die Symbolleiste anpassen
exl-id: ba82af48-9357-4f29-90ce-6793366ab432
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Symbolleiste anpassen {#id172FB00L0V6}

Standardmäßig werden im Lieferumfang des Web-Editors die gängigsten redaktionellen Funktionen enthalten sein, die von einem DITA-Editor benötigt werden. Funktionen wie das Einfügen von Elementen des Typs \(nummeriert oder mit Aufzählungszeichen\), Querverweis, Inhaltsreferenz, Tabelle, Absatz und Zeichenformatierung sind im Editor verfügbar. Zusätzlich zu diesen grundlegenden Elementen können Sie den Web-Editor so anpassen, dass Elemente eingefügt werden, die in Ihrer Autorenumgebung verwendet werden.

Es gibt zwei Möglichkeiten, die Symbolleiste des Web-Editors anzupassen:

- Hinzufügen einer neuen Funktion zur Symbolleiste

- Entfernen vorhandener Funktionen aus der Symbolleiste


## Funktion in der Symbolleiste hinzufügen

Das Hinzufügen einer Funktion zum Web-Editor umfasst zwei Hauptaufgaben: Hinzufügen eines Symbols für die Funktion in der Datei *ui\_config.json* und Hinzufügen der Hintergrundfunktion in JavaScript.

Führen Sie die folgenden Schritte aus, um der Symbolleiste des Web-Editors eine Funktion hinzuzufügen:

1. Um die Konfigurationsdatei der Benutzeroberfläche herunterzuladen, melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie **oben auf** Bearbeiten“
1. Klicken Sie auf **Herunterladen**, um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
1. Fügen Sie in der `ui_config.json`-Datei die Definition der neuen Funktion im Abschnitt Symbolleisten hinzu. Speichern Sie die Datei und laden Sie sie hoch.

   In der Regel können Sie eine neue Gruppe von Symbolleistenschaltflächen erstellen und ihr eine oder mehrere Symbolleistenschaltflächen hinzufügen. Sie können auch eine neue Symbolleistenschaltfläche zu einer vorhandenen Symbolleistengruppe hinzufügen. Zum Erstellen einer neuen Symbolleistengruppe sind die folgenden Details erforderlich:

   **type**:   Geben Sie `blockGroup` als `type` an. Dieser Wert gibt an, dass Sie eine Blockgruppe erstellen, die eine oder mehrere Symbolleistengruppen enthalten würde.

   **extraClass**:   Name der Klasse(n), durch Leerzeichen getrennt

   **items**:   Legen Sie die Definition aller Gruppen in der Symbolleiste fest. Jede Gruppe kann ein oder mehrere Symbolleistensymbole enthalten. Um Symbole innerhalb einer Symbolleistengruppe zu definieren, müssen Sie erneut das `type` Attribut innerhalb der `items` definieren und deren Wert auf `buttonGroup` festlegen. Geben Sie einen oder mehrere Klassennamen in der `extraclass` Eigenschaft an. Geben Sie den Funktionsnamen in der Eigenschaft `label` an. Der folgende Ausschnitt aus der `ui_config.json` zeigt die Definition für den Haupt-Symbolleistenblock, gefolgt von der `buttonGroup` Definition:

       &quot;
       „toolbar“: {
       „type“: „blockGroup“,
       „extraClass“:
       „Symbolleistenvorgänge“,
       „items“: [
       {
       „type“: „buttonGroup“,
       „extraClass“: „left-Controls“,
       „label“: „Left Controls“,
       „items“: [
       &quot;
   
   Innerhalb der `items` müssen Sie die Definition für ein oder mehrere Symbolleistensymbole angeben.

   Sie müssen die folgenden Eigenschaften definieren, um ein Symbolleistensymbol hinzuzufügen:

   **type**:   Geben Sie `button` als `type` an. Dieser Wert gibt an, dass Sie eine Symbolleistenschaltfläche hinzufügen.

   **Symbol**:   Geben Sie den Namen des Coral-Symbols an, das Sie in der Symbolleiste verwenden möchten.

   **Variante**:   Geben Sie `quiet` als `variant` an.

   **title**:   Geben Sie die QuickInfo für das Symbol an.

   **on-click**:   Geben Sie den Befehlsnamen an, der für die Funktion in der JavaScript-Datei definiert ist. Wenn für den Befehl Eingabeparameter erforderlich sind, geben Sie den Befehlsnamen wie folgt an:

       „JavaScript
       „on-click“: {„name“: „AUTHOR_INSERT_ELEMENT“, „args“: „simpltable“}
       &quot;
   
   **Einblenden oder ausblenden**:   Wenn Sie die `show`-Eigenschaft definieren, geben Sie die Modi an, in denen das Symbol angezeigt wird. Zu den möglichen Werten gehören - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(Anzeige in allen Modi\) oder `false` \(Ausblenden in allen Modi\).

   Anstelle von `show` können Sie auch die Eigenschaft `hide` definieren. Die möglichen Werte sind dieselben wie in `show` Eigenschaft, mit dem einzigen Unterschied, dass das Symbol für den angegebenen Modus nicht angezeigt wird.

   Das folgende Beispiel zeigt die AEM Guides-Versionsnummer, wenn der/die Benutzende auf das Symbol Version anzeigen in der Symbolleiste klickt.

   Fügen Sie den folgenden Code zu einer JavaScript-Datei hinzu:

   ```Javascript
   $(document).ready(setTimeout(function() {
                           fmxml.commandHandler.subscribe({
                           key: 'user.alert',
                           next: function() {
                           alert("AEM Guides version x.x")
                           }
                           })
                           }, 1000))
   ```

   Fügen Sie die Funktion in der Datei *ui\_config.json* wie folgt hinzu:

   ```Javascript
   "type": "button",
   "icon": "alert","variant": "quiet","title": "About AEM Guides","show": "true","on-click": "user.alert"
   ```

1. Erstellen Sie *Ordner &quot;*&quot; und fügen Sie Ihre JavaScript diesem Ordner hinzu.

1. Aktualisieren Sie die Kategorieneigenschaft des Ordners *clientlib* durch Zuweisen des Werts &quot;*.fmdita.xml\_editor.page\_overrides*.

1. Speichern Sie die *ui\_config.json*-Datei und laden Sie den Web-Editor neu.


## Funktion aus der Symbolleiste entfernen

Manchmal möchten Sie vielleicht nicht alle derzeit im Web-Editor verfügbaren Funktionen bereitstellen. In diesem Fall können Sie die unerwünschte Funktion aus der Symbolleiste des Web-Editors entfernen.

Führen Sie die folgenden Schritte aus, um unerwünschte Funktionen aus der Symbolleiste zu entfernen:

1. Um die Konfigurationsdatei der Benutzeroberfläche herunterzuladen, melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie **oben auf** Bearbeiten“
1. Klicken Sie auf **Herunterladen**, um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

   Die `ui_config.json`-Datei besteht aus drei Abschnitten:

   1. **Symbolleisten**:   Dieser Abschnitt enthält die Definition aller in der Editor-Symbolleiste verfügbaren Funktionen wie Einfügen/Entfernen, Nummerierte Liste, \(Datei\) Schließen, Speichern, Kommentare und mehr.

   1. **Tastaturbefehle**:   Dieser Abschnitt enthält die Definition der Tastaturbefehle, die einer bestimmten Funktion im Editor zugewiesen sind.

   1. **Vorlagen**:   Dieser Abschnitt enthält die vordefinierte Struktur von DITA-Elementen, die Sie in Ihrem Dokument verwenden können. Standardmäßig enthält der Abschnitt Vorlagen Vorlagendefinitionen für einen Absatz, einfache Tabellen-, Tabellen- und Textelemente. Sie können eine Vorlagendefinition für ein beliebiges Element erstellen, indem Sie eine gültige XML-Struktur für das gewünschte Element hinzufügen. Wenn Sie beispielsweise zu jedem neuen `li`-Element in einer Liste ein `p`-Element hinzufügen möchten, können Sie zu diesem Zweck den folgenden Code am Ende des Abschnitts „Vorlagen“ hinzufügen:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Entfernen Sie aus dem Abschnitt Symbolleisten den Eintrag der Funktion, die Sie Ihren Benutzern nicht zur Verfügung stellen möchten.

1. Speichern Sie die *ui\_config.json*-Datei und laden Sie den Web-Editor neu.


**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
