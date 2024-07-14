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

Standardmäßig werden im Web Editor die gängigsten redaktionellen Funktionen bereitgestellt, die für jeden DITA-Editor erforderlich sind. Funktionen wie das Einfügen von Elementen des Typs Liste \(nummeriert oder mit Aufzählungszeichen\), Querverweis, Inhaltsverweis, Tabelle, Absatz und Zeichenformatierung sind im Editor verfügbar. Zusätzlich zu diesen grundlegenden Elementen können Sie den Web-Editor anpassen, um Elemente einzufügen, die in Ihrer Authoring-Umgebung verwendet werden.

Es gibt zwei Möglichkeiten, die Symbolleiste des Web-Editors anzupassen:

- Hinzufügen neuer Funktionen zur Symbolleiste

- Entfernen vorhandener Funktionen aus der Symbolleiste


## Hinzufügen einer Funktion in der Symbolleiste

Das Hinzufügen einer Funktion zum Webeditor umfasst zwei Hauptaufgaben: das Hinzufügen eines Symbols für die Funktion in der Datei *ui\_config.json* und das Hinzufügen der Hintergrundfunktion in JavaScript.

Führen Sie die folgenden Schritte aus, um der Symbolleiste des Web-Editors eine Funktion hinzuzufügen:

1. Um die Benutzeroberflächenkonfigurationsdatei herunterzuladen, melden Sie sich als Administrator bei Adobe Experience Manager an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die Kachel **Globales Profil** .
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** aus und klicken Sie oben auf das Symbol **Bearbeiten** .
1. Klicken Sie auf das Symbol **Download** , um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
1. Fügen Sie in der Datei `ui_config.json` die Definition der neuen Funktion im Abschnitt &quot;Symbolleisten&quot;hinzu. Speichern Sie die Datei und laden Sie sie hoch.

   In der Regel können Sie eine neue Schaltflächengruppe für Symbolleisten erstellen und eine oder mehrere Schaltflächen der Symbolleiste hinzufügen. Sie können auch eine neue Symbolleistenschaltfläche innerhalb einer vorhandenen Symbolleistengruppe hinzufügen. Die folgenden Details sind erforderlich, um eine neue Symbolleistengruppe zu erstellen:

   **type**:   Geben Sie `blockGroup` als den Wert `type` an. Dieser Wert gibt an, dass Sie eine Blockgruppe erstellen, die eine oder mehrere Symbolleistengruppen enthalten würde.

   **extraclass**:   Name der Klasse(n), getrennt durch Leerzeichen.

   **items**:   Definieren Sie die Definition aller Gruppen in der Symbolleiste. Jede Gruppe kann ein oder mehrere Symbolleistensymbole enthalten. Um Symbole in einer Symbolleistengruppe zu definieren, müssen Sie das Attribut `type` innerhalb von `items` erneut definieren und dessen Wert auf `buttonGroup` setzen. Geben Sie einen oder mehrere Klassennamen in der Eigenschaft `extraclass` an. Geben Sie den Funktionsnamen in der Eigenschaft `label` an. Das folgende Codefragment aus der Datei `ui_config.json` zeigt die Definition des Haupt-Symbolleistenblocks gefolgt von der Definition `buttonGroup`:

       &quot;
       &quot;toolbar&quot;: {
       &quot;type&quot;: &quot;blockGroup&quot;,
       &quot;extraclass&quot;:
       &quot;toolbar operations&quot;,
       &quot;items&quot;: [
       {
       &quot;type&quot;: &quot;buttonGroup&quot;,
       &quot;extraclass&quot;: &quot;left-control&quot;,
       &quot;label&quot;: &quot;Left Controls&quot;,
       &quot;items&quot;: [
       &quot;
   
   In der Sammlung `items` müssen Sie die Definition für ein oder mehrere Symbolleistensymbole angeben.

   Sie müssen die folgenden Eigenschaften definieren, um ein Symbolleistensymbol hinzuzufügen:

   **type**:   Geben Sie `button` als den Wert `type` an. Dieser Wert gibt an, dass Sie eine Symbolleistenschaltfläche hinzufügen.

   **icon**:   Geben Sie den Namen des Coral-Symbols an, das Sie in der Symbolleiste verwenden möchten.

   **variant**:   Geben Sie `quiet` als den Wert `variant` an.

   **title**:   Geben Sie die QuickInfo für das Symbol an.

   **on-click**:   Geben Sie den für die Funktion definierten Befehlsnamen in der JavaScript-Datei an. Wenn für Ihren Befehl Eingabeparameter erforderlich sind, geben Sie den Befehlsnamen wie folgt an:

       &quot;Javascript
       &quot;on-click&quot;: {&quot;name&quot;: &quot;AUTHOR_INSERT_ELEMENT&quot;, &quot;args&quot;: &quot;simplable&quot;}
       &quot;
   
   **Einblenden oder Ausblenden**:   Wenn Sie die Eigenschaft `show` definieren, geben Sie die Modi an, in denen das Symbol angezeigt wird. Mögliche Werte sind - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(in allen Modi anzeigen\) oder `false` \(in allen Modi ausblenden\).

   Anstelle von `show` können Sie auch die Eigenschaft `hide` definieren. Die möglichen Werte sind mit denen in der Eigenschaft `show` identisch, mit dem einzigen Unterschied, dass das Symbol für den angegebenen Modus nicht angezeigt wird.

   Das folgende Beispiel zeigt die AEM Guides-Versionsnummer, wenn der Benutzer in der Symbolleiste auf das Symbol Version anzeigen klickt.

   Fügen Sie einer JavaScript-Datei den folgenden Code hinzu:

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

1. Erstellen Sie einen Ordner *clientlib* und fügen Sie Ihren JavaScript in diesen Ordner ein.

1. Aktualisieren Sie die categories-Eigenschaft des Ordners *clientlib* , indem Sie ihm den Wert *apps.fmdita.xml\_editor.page\_overrides* zuweisen.

1. Speichern Sie die Datei *ui\_config.json* und laden Sie den Web Editor neu.


## Entfernen einer Funktion aus der Symbolleiste

Manchmal möchten Sie nicht alle derzeit im Web-Editor verfügbaren Funktionen bereitstellen. In diesem Fall können Sie die unerwünschte Funktion aus der Symbolleiste des Web-Editors entfernen.

Führen Sie die folgenden Schritte aus, um unerwünschte Funktionen aus der Symbolleiste zu entfernen:

1. Um die Benutzeroberflächenkonfigurationsdatei herunterzuladen, melden Sie sich als Administrator bei Adobe Experience Manager an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Handbücher** aus der Liste der Tools und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die Kachel **Globales Profil** .
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** aus und klicken Sie oben auf das Symbol **Bearbeiten** .
1. Klicken Sie auf das Symbol **Download** , um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

   Die Datei `ui_config.json` enthält drei Abschnitte:

   1. **toolbars**:   Dieser Abschnitt enthält die Definition aller in der Symbolleiste des Editors verfügbaren Funktionen wie &quot;Nummerierte Liste einfügen/entfernen&quot;, &quot;\(Datei\) schließen&quot;, &quot;Speichern&quot;, &quot;Kommentare&quot;und mehr.

   1. **shortcuts**:   Dieser Abschnitt enthält die Definition von Tastaturbefehlen, die einer bestimmten Funktion im Editor zugewiesen sind.

   1. **templates**:   Dieser Abschnitt enthält die vordefinierte Struktur von DITA-Elementen, die Sie in Ihrem Dokument verwenden können. Standardmäßig enthält der Abschnitt &quot;Vorlagen&quot;Vorlagendefinitionen für Absätze, einfache Tabellen, Tabellen und Textelemente. Sie können eine Vorlagendefinition für jedes Element erstellen, indem Sie eine gültige XML-Struktur für das gewünschte Element hinzufügen. Wenn Sie beispielsweise ein `p` -Element mit jedem neuen `li` -Element in einer Liste hinzufügen möchten, können Sie den folgenden Code am Ende des Vorlagenabschnitts hinzufügen, um dies zu erreichen:

   ```css
   "li": "<li><p></p></li>"
   ```

1. Entfernen Sie im Abschnitt &quot;Symbolleisten&quot;den Eintrag der Funktion, die Sie Ihren Benutzern nicht zur Verfügung stellen möchten.

1. Speichern Sie die Datei *ui\_config.json* und laden Sie den Web Editor neu.


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
