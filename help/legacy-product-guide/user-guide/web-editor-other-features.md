---
title: Weitere Funktionen im Web-Editor
description: Erkunden Sie andere Funktionen des Web-Editors in AEM Guides. Erfahren Sie, wie Sie diese Funktionen für ein verbessertes Authoring in AEM Guides verwenden.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 7639fa76-b319-44b5-9ff8-2b8c1a716b7b
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '2532'
ht-degree: 0%

---

# Weitere Funktionen im Web-Editor {#id2056B0B0YPF}

Es gibt einige andere nützliche Funktionen im Web-Editor, die Sie nutzen können:

**Kontextmenüfunktionen auf der Registerkarte einer Datei**

Wenn Sie eine Datei im Web-Editor öffnen, können Sie verschiedene Aktionen über das Kontextmenü ausführen. Je nachdem, ob Sie eine Mediendatei, eine einzelne DITA-Datei oder mehrere Dateien öffnen, werden Ihnen möglicherweise unterschiedliche Optionen angezeigt.

**Mediendatei**

Die folgenden Funktionen finden Sie im Kontextmenü der Registerkarte einer geöffneten Mediendatei:

![](images/media-file-context-menu.png){width="300" align="left"}

**Einzelne DITA-Datei**

Die folgenden Funktionen finden Sie im Kontextmenü der Registerkarte einer geöffneten Datei:

:   ![](images/single-file-context-menu.png){width="300" align="left"}

**Mehrere Dateien**

Wenn mehrere Dateien geöffnet sind, stehen im Kontextmenü weitere Optionen zur Verfügung:

![](images/multiple-files-context-menu.png){width="550" align="left"}

Nachfolgend werden die verschiedenen Optionen im Kontextmenü erläutert:

***Speichern***: Sie können aus den folgenden Optionen auswählen:

- **Speichern**: Um eine Datei zu speichern, ohne eine neue Version zu erstellen, wählen Sie **Speichern**. Wenn Sie ein neues Thema erstellen, wird in DAM eine Arbeitskopie des Themas ohne Version erstellt. Durch Speichern des Dokuments wird die Arbeitskopie des Dokuments in DAM aktualisiert. Durch eine einfache Speicherung dieser Version wird keine neue Version eines Themas erstellt. Wenn Ihr Thema überprüft wird, erhalten Ihre Reviewer beim Speichern eines Themas keinen Zugriff auf den Inhalt Ihres geänderten Themas.

- **Alle speichern**: Wenn mehrere Dokumente im Web-Editor geöffnet sind, erhalten Sie auch eine Option zum **Alle speichern** geöffneter Dokumente.


***Als neue Version speichern***

Um eine neue Version der Datei zu erstellen, wählen Sie **Als neue Version speichern**. Weitere Informationen zu **Speichern** und **Als neue Version speichern** finden Sie unter [Kennen Sie die Funktionen des Web-Editors](web-editor-features.md#).

***Kopieren***: Sie können aus den folgenden Optionen auswählen:

- **UUID kopieren**: Um die UUID der aktuell aktiven Datei in die Zwischenablage zu kopieren, wählen Sie **Kopieren \> UUID kopieren**.
- **Pfad kopieren**: Um den vollständigen Pfad der derzeit aktiven Datei in die Zwischenablage zu kopieren, wählen Sie **Kopieren \> Pfad kopieren**.


***Suchen in***: Sie können aus den folgenden Optionen auswählen:

- **Map**: Wenn Sie eine große DITA-Map geöffnet haben und den genauen Speicherort einer Datei in der Map finden möchten, wählen Sie **Locate In \> Map**. Wenn Sie die Option „In Zuordnung suchen“ auswählen, befindet sich die Datei \(von der aus die Option aufgerufen wird\) und wird in der Zuordnungshierarchie hervorgehoben. Um diese Funktion verwenden zu können, müssen Sie die Zuordnungsdatei im Web-Editor öffnen. Wenn die Zuordnungsansicht ausgeblendet ist, wird beim Aufrufen dieser Funktion die Zuordnungsansicht angezeigt und die Datei wird in der Zuordnungshierarchie hervorgehoben.

- **Repository**: Ähnlich wie „In Map suchen“ zeigt **In \> Repository** den Speicherort der Datei im Repository \(oder DAM\). Die Repository-Ansicht wird geöffnet und die ausgewählte Datei wird im Repository hervorgehoben. Wenn sich die Datei in einem Ordner befindet, wird dieser Ordner erweitert, um den Speicherort der ausgewählten Datei im Repository anzuzeigen.


***Hinzufügen zu***: Sie können aus den folgenden Optionen auswählen:

- **Favoriten**: Um die ausgewählte Datei zur Favoritensammlung hinzuzufügen, wählen Sie **Zu \> Favoriten hinzufügen** aus. Weitere Informationen finden Sie in der **Favoriten** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](web-editor-features.md#id2051EA0M0HS).



- **Wiederverwendbarer Inhalt**: Um die ausgewählte Datei in die Liste der wiederverwendbaren Inhalte zu kopieren, wählen Sie **Zu \> Wiederverwendbare Inhalte hinzufügen** aus. Weitere Informationen finden Sie in der **Wiederverwendbarer Inhalt** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](web-editor-features.md#id2051EA0M0HS).




***Eigenschaften***

Um die AEM-Eigenschaftsseite der ausgewählten Datei anzuzeigen, wählen Sie **Eigenschaften** aus.

***Aufspaltung***: Sie können aus den folgenden Optionen auswählen:

**Nach oben, unten, links oder rechts**

Standardmäßig können Sie mit dem Web-Editor jeweils nur ein Thema anzeigen. Es kann Fälle geben, in denen Sie zwei oder mehr Themen gleichzeitig sehen möchten. Durch die Aufteilung des Bildschirms des Editors können Sie mehrere Themen gleichzeitig anzeigen. Beispiel: Zwei Themen - A und B - sind im Editor geöffnet. Wenn Sie mit der rechten Maustaste auf Thema B klicken und **Aufspaltung \> Nach** wählen, wird das Editor-Fenster in zwei Teile unterteilt. Thema B wird in der oberen Hälfte und Thema A in der unteren Hälfte angezeigt. Ebenso können Sie den Bildschirm auch horizontal aufteilen, indem Sie **Aufspaltung \> Links** oder **Aufspaltung \> Rechts** auswählen. Im folgenden Screenshot des Web-Editors werden Themen horizontal und vertikal geteilt angezeigt. In jeder Teilung können Sie eine andere Ansicht haben. Im folgenden Screenshot befindet sich beispielsweise der Bildschirm 1 im Source-Ansichtsmodus, Bildschirm 2 hat zwei Dokumente im Autorenmodus geöffnet und Bildschirm 3 ist im Vorschaumodus. Sie können Ihre Dokumente von einem Bildschirm auf den anderen verschieben, indem Sie die Registerkarte Datei ziehen und auf dem Bildschirm ablegen, auf dem Sie sie platzieren möchten. Ebenso können Sie die Dateiregisterkarten auch neu anordnen, indem Sie sie nach Ihren Wünschen ziehen und verschieben.

![](images/split-editor.png){width="800" align="left"}

***Quick Generate***

Ausgabe für die ausgewählte Datei erzeugen. Die Ausgabe kann nur für Dateien generiert werden, die Teil einer Ausgabevorgabe sind. Weitere Informationen finden Sie unter [Artikelbasierte Veröffentlichung im Web-Editor](web-editor-article-publishing.md#id218CK0U019I).

***Schließen***: Sie können aus den folgenden Optionen auswählen:

**Schließen**, **Andere schließen** oder **Alle schließen**

Wenn Sie die Datei schließen möchten, über die Sie das Kontextmenü aufgerufen haben, wählen Sie **Schließen \> Schließen**. Verwenden Sie **Schließen \> Andere schließen**, um alle anderen geöffneten Dateien mit Ausnahme der derzeit aktiven Datei zu schließen. Um alle geöffneten Dateien zu schließen, wählen Sie die Option **Schließen \> Alle schließen** aus dem Kontextmenü aus, oder Sie können auch den Web-Editor schließen. Wenn Ihre Sitzung nicht gespeicherte Dateien enthält, werden Sie aufgefordert, diese Dateien zu speichern.

**Szenarien zum Schließen und Speichern von Dateien**

Wenn Sie versuchen, eine im Web-Editor geöffnete Datei mithilfe der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Optionsmenü zu schließen, fordert AEM Guides Sie auf, Ihre Änderungen zu speichern und eine gesperrte Datei zu entsperren.

Die Eingabeaufforderungen basieren auf den folgenden Konfigurationen, die von Ihrem Administrator ausgewählt wurden:

- **Beim Schließen zum Einchecken auffordern:** Sie haben die Möglichkeit, die Datei \(die Sie ausgecheckt haben\) einzuchecken, wenn Sie den Editor schließen.
- **Beim Schließen um neue Version bitten**: Beim Schließen des Editors haben Sie die Möglichkeit, die Datei \(die Sie bearbeitet haben\) als neue Version zu speichern.

Ihr Dateispeichererlebnis hängt von den folgenden drei Szenarien ab, in denen Sie über Folgendes verfügen:

- Keine Änderungen am Inhalt vorgenommen.
- Inhalt bearbeitet und Änderungen gespeichert.
- Inhalt bearbeitet, aber Änderungen nicht gespeichert.

Je nachdem, ob die Datei gesperrt/entsperrt ist und gespeicherte oder nicht gespeicherte Änderungen aufweist, werden möglicherweise die folgenden Optionen angezeigt:

- **Entsperren und Schließen**: Die Sperre für die Datei wird aufgehoben, und die Datei wird geschlossen.

  ![](images/file-close-unlock-file.png){width="400" align="left"}

- **Als neue Version speichern**: Speichert die Änderungen, die Sie am Inhalt vorgenommen haben, und erstellt eine neue Version der Datei. Sie können der neu gespeicherten Version auch Beschriftungen und Kommentare hinzufügen. Weitere Informationen zum Speichern einer neuen Version finden Sie unter [Als neue Version speichern](web-editor-features.md#save-as-new-version-id209ME400GXA).

- **Datei entsperren**: Wenn Sie eine Datei entsperren, wird die Sperre für die Datei aufgehoben und die Änderungen werden in der aktuellen Version der Datei gespeichert.

  >[!NOTE]
  >
  > Wenn Sie die Option zum Entsperren der Datei deaktivieren, erhalten Sie auch die Option, die Datei zu schließen, ohne die Änderungen zu speichern.

  Eine der Eingabeaufforderungen wird beispielsweise im folgenden Screenshot angezeigt:

  ![](images/file-close-save-changes-unlock.png){width="400" align="left"}

**Visuelle Hinweise auf fehlerhafte Verweise**

- Wenn das Thema fehlerhafte Querverweise oder Inhaltsreferenzen enthält, werden diese in rotem Text angezeigt.

**Smartes Kopieren und Einfügen**

- Sie können mühelos Inhalte kopieren und in und über Themen hinweg einfügen. Die Struktur des Quellelements wird am Ziel beibehalten. Wenn der kopierte Inhalt Inhaltsreferenzen enthält, werden auch diese kopiert.

**Letzten durchsuchten Speicherort speichern**

- Der Web-Editor bietet ein Dialogfeld zum Durchsuchen von smarten Dateien. Der Editor speichert den zuletzt verwendeten Speicherort beim Einfügen eines Verweises oder Inhalts. Wenn Sie das Dialogfeld zum ersten Mal aufrufen (über Verweis einfügen oder Inhalt wiederverwenden), werden Sie an den Speicherort des aktuellen Dokuments weitergeleitet. Wenn Sie in derselben Sitzung versuchen, einen anderen Verweis einzufügen, navigiert das Dialogfeld zum Durchsuchen der Datei automatisch zu der Position, von der aus Sie den letzten Verweis eingefügt haben.

>[!NOTE]
>
> Im Falle einer Bild-, Audio- oder Videodatei wird im Dialogfeld zum Durchsuchen der Datei standardmäßig der Speicherort der Datei und nicht der zuletzt verwendete Speicherort angezeigt.

**Unterstützung für die artikelbasierte Veröffentlichung**

- Im Web-Editor können Sie die Ausgabe für ein oder mehrere Themen oder die gesamte DITA-Zuordnung generieren. Sie müssen Ausgabevorgaben für Ihre DITA-Zuordnung erstellen und dann können Sie die Ausgabe einfach für ein oder mehrere Themen generieren. Wenn Sie einige Themen in Ihrer Zuordnung aktualisiert haben, können Sie die Ausgabe auch nur für diese Themen aus dem Web-Editor generieren. Weitere Informationen finden Sie unter [Artikelbasierte Veröffentlichung im Web-Editor](web-editor-article-publishing.md#id218CK0U019I).

**Unterstützung für Markdown-Dokumente**

- Mit dem Web-Editor können Sie Markdown-Dokumente \(.md\) zusammen mit Ihren DITA-Dokumenten verwenden. Sie können ein Markdown-Dokument einfach im Web-Editor erstellen und in der Vorschau anzeigen und es über den DITA-Karteneditor auch Ihrer Kartendatei hinzufügen. Weitere Informationen finden Sie unter [Erstellen von Markdown-Dokumenten über den Web-Editor](web-editor-markdown-topic.md#).

**Unterstützung für DITA-Glossarbegriffsthema**

- Der Web-Editor unterstützt DITA-Glossarbegriffe, die Sie einfügen können, indem Sie `term` oder `abbreviated-form` Elemente hinzufügen.

**Einfügen von MathML-Gleichungen**

- Experience Manager Guides bietet vorkonfigurierte Unterstützung zum Einfügen von MathML-Gleichungen durch Integration mit dem [MathType Web](https://docs.wiris.com/en/mathtype/mathtype_web/intro)-Programm. Um eine MathML-Gleichung einzufügen, klicken Sie auf das Symbol **Element einfügen** und geben Sie mathml ein. Wenn Sie ein mathml-Element aus der Liste auswählen, wird **Dialogfeld &quot;MathML einfügen** angezeigt:

![Einfügen einer MathML-Gleichung im MathML-Editor](images/insert-mathml-equation.png){width="550" align="left"}

Erstellen Sie mithilfe der MathML-Formel Ihre Formel und klicken Sie auf **Einfügen**, um sie Ihrem Dokument hinzuzufügen. Die Gleichung wird mit hellgrauem Hintergrund eingefügt, wie unten dargestellt:

![Beispiel-mathml-Gleichung](images/sample-mathml-equation.PNG){width="400" align="left"}

Sie können eine Formel jederzeit aktualisieren, indem Sie mit der rechten Maustaste auf eine vorhandene Gleichung klicken und **MathML bearbeiten** aus dem Kontextmenü auswählen.

- **Validierung von Gleichungen im MathML-Editor**

  Experience Manager Guides validiert MathML-Gleichungen, wenn Sie ein Thema speichern, das sie enthält.
Wenn Sie eine Gleichung mit dem MathML-Editor einfügen, markiert Experience Manager Guides die Gleichung rot, wenn Syntaxprobleme auftreten. Sie können sie vor dem Einfügen korrigieren. Wenn Sie keine Änderungen vornehmen, aber **Einfügen** auswählen, wird eine Warnung angezeigt.

  ![Validieren einer MathML-Gleichung](images/validate-mathml-equation.png){width="400" align="left"}

  Wenn Sie die MathML-Gleichung einfügen, die einen Syntaxfehler enthält, tritt beim Speichern des Themas ein Validierungsfehler auf.


**Fußnoten einfügen**

- Fügen Sie eine Fußnote mithilfe des `fn` in Ihren Inhalt ein. Im Bearbeitungsmodus wird der Fußnotenwert inline mit dem Inhalt angezeigt. Wenn Sie jedoch in den Vorschaumodus wechseln oder Ihr Dokument veröffentlichen, wird die Fußnote am Ende des Themas angezeigt.


**Umbenennen oder Ersetzen eines Elements**

- Der Web-Editor zeigt den Breadcrumb des Elements oben im Thema an. Wenn Sie ein Element durch ein anderes ersetzen möchten, können Sie dies im Kontextmenü des Breadcrumbs tun. Sie können beispielsweise `p` Element durch `note` oder ein anderes gültiges Element im Kontext austauschen.

![](images/rename-element.png){width="400" align="left"}

Klicken Sie im Breadcrumb mit der rechten Maustaste auf den Namen eines Elements, das Sie ersetzen möchten, und wählen Sie dann im Kontextmenü Element umbenennen . Das Dialogfeld Element umbenennen zeigt alle gültigen Elemente an, die am aktuellen Speicherort zulässig sind. Wählen Sie im Dialogfeld Element umbenennen das Element aus, das Sie verwenden möchten. Das ursprüngliche Element wird durch das neue Element ersetzt.

Zusätzlich zum Kontextmenü des Breadcrumbs kann das Dialogfeld Element umbenennen auch von anderen Speicherorten aus aufgerufen werden:

- Klicken Sie auf den Elementnamen auf dem Breadcrumb, um den Inhalt des Elements auszuwählen, und klicken Sie mit der rechten Maustaste auf den ausgewählten Inhalt, um das Kontextmenü aufzurufen.

- Aktivieren Sie die Tag-Ansicht, klicken Sie auf das öffnende Tag eines beliebigen Elements und klicken Sie dann mit der rechten Maustaste auf den ausgewählten Inhalt, um das Kontextmenü aufzurufen.

- Sie können auf das Dialogfeld Element umbenennen zugreifen, indem Sie das Menü Optionen eines Elements im Gliederungsfenster aufrufen.



**Element umschließen**

- Wenn Sie ein Element umschließen, können Sie dem ausgewählten Text ein Element-Tag hinzufügen. Sie können den Text in ein beliebiges untergeordnetes Element einschließen, das DITA-Standards entspricht. Wenn Sie beispielsweise Text unter einem `note` Element haben, können Sie den Text in ein `p` Element einschließen.

  Die **Element umbrechen** Option ist im Kontextmenü des Breadcrumbs des Themas verfügbar. Um ein Element einzuschließen, klicken Sie mit der rechten Maustaste auf das Element und öffnen Sie das Kontextmenü. Wählen Sie das Element im Dialogfeld **Element umbrechen** aus. Der Text wird im neuen Element angezeigt.

  Sie können auch den Text oder das Element im Inhalt auswählen und dann die Option **Element umbrechen** aus dem Kontextmenü auswählen.

**Element entpacken**

- Wenn Sie die Verpackung eines Elements aufheben, können Sie das Tag des Elements aus dem markierten Text entfernen und es mit dem übergeordneten Element zusammenführen. Wenn Sie beispielsweise ein `p` in einem `note` haben, können Sie den Wrapper für das `p` Element aufheben, um den Text direkt im `note` Element zusammenzuführen. Die **Element entpacken**-Option ist im Kontextmenü des Breadcrumbs des Themas verfügbar. Um den Wrapper für ein Element aufzuheben, klicken Sie mit der rechten Maustaste auf das Element, um das Kontextmenü zu öffnen, und wählen Sie **Element aufheben**, um das Element zu entfernen und den Text des Elements mit seinem übergeordneten Element zusammenzuführen.

**Umgang mit Leerzeichen für DITA-Elemente**

- In XML umfassen Leerzeichen Leerzeichen Leerzeichen, Tabulatoren, Zeilenumbrüche und Leerzeilen. Experience Manager Guides wandelt mehrere aufeinander folgende Leerzeichen in ein einziges Leerzeichen um. Auf diese Weise können Sie die WYSIWYG-Ansicht des Web-Editors beibehalten.

  >[!NOTE]
  >
  >Bei einigen Elementen, bei denen Leerräume gemäß den DITA-Regeln beibehalten werden müssen, werden die mehreren aufeinander folgenden Leerräume beibehalten. Beispielsweise `<pre>` und `<codeblock>` Elemente.


**Beibehalten von Zeilenumbrüchen und Einzügen**

- DITA-Elemente, die Zeilenumbrüche und Leerzeichen enthalten, werden gemäß ihrer Definition im Author-, Source- oder Preview-Modus unterstützt und gerendert, sowie in der endgültigen veröffentlichten Ausgabe. Der folgende Screenshot zeigt den Inhalt innerhalb des `msgblock`, bei dem die Zeilenumbrüche und Leerzeichen \(Einzug\) beibehalten wurden:

![](images/new-line-support_cs.png){width="500" align="left"}



**Umgang mit Leerzeichen ohne Unterbrechung im Web-Editor**

- Sie können Leerzeichen ohne Umbruch in Ihr Dokument einfügen, indem Sie das Symbol **Sonderzeichen einfügen** ![Sonderzeichen einfügen](images/insert-special-chars-icon.svg) oder die Tastenkombinationen **Alt** + **Leerzeichen** verwenden.  Diese geschützten Leerzeichen werden beim Bearbeiten eines Themas im Web-Editor als Indikator angezeigt. Sie können die Anzeige der Leerzeichen ohne Unterbrechung mit der Option **Anzeige von Leerzeichen ohne Unterbrechung im Autorenmodus anzeigen** auf der Registerkarte **Erscheinungsbild** des **Benutzereinstellungen** ![Benutzereinstellungen](images/user_preference_editor_icon.svg).

- Wenn Sie Inhalte mit einem Leerzeichen ohne Unterbrechung aus externen Quellen kopieren und in die Ansicht **Autor** einfügen, wird der Leerzeichen ohne Unterbrechung in ein Leerzeichen umgewandelt.
Wenn Sie jedoch Inhalte mit einem Leerzeichen kopieren und einfügen, das nicht aus der **Autoren**-Ansicht stammt, bleiben diese erhalten.


**Element-ID automatisch generieren**

- Sie können automatisch IDs für die Elemente in Ihrem DITA-Thema generieren. Diese IDs sind innerhalb eines DITA-Themas eindeutig. Wenn Sie beispielsweise IDs für ein Absatzelement generieren, sind die IDs p\_1, p2, p\_3 usw. Sie können mehrere Elemente auswählen und für jedes ausgewählte Element IDs generieren.

Gehen Sie folgendermaßen vor, um automatisch eine ID für ein oder mehrere Elemente zu generieren:

1. Öffnen Sie das Thema im Web-Editor.
1. Wählen Sie den Inhalt aus, dem Sie IDs zuweisen möchten.
1. Klicken Sie mit der rechten Maustaste und wählen **Generate IDs (IDs generieren) aus dem Kontextmenü.**

   Alternativ können Sie mit der rechten Maustaste in den Breadcrumb klicken und **IDs generieren** auswählen.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Arbeiten mit dem Web-Editor](web-editor.md)
