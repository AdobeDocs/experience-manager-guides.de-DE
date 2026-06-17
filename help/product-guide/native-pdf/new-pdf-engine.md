---
title: Neue Publishing-Engine für Native PDF | Generieren von PDF-Ausgaben
description: Erfahren Sie, wie Sie mit der neuen Veröffentlichungs-Engine für native PDF-Veröffentlichungen arbeiten
feature: Publishing, Native PDF Output
role: User
TQID: https://experienceleague.adobe.com/GV3iYtBdFVrQwFjdvfqnfDIWPMugO3hFjS4FZqspG2M
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d6596f3f-92a7-43ec-b444-237db6adad05id: f6b497f1-f8e0-42ce-8e95-56c28d94026eid: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 2b6a0f1a6ac03984286e9d3df40c197f28d52f8d
workflow-type: tm+mt
source-wordcount: 844
ht-degree: 0%

---

# Arbeiten mit der nativen PDF-Engine v2

Die neue Publishing-Engine *Native PDF Engine v2* basiert auf einem aktualisierten PDF-Generierungs-Framework und enthält Änderungen an der Schriftartenverarbeitung, der CSS-Verarbeitung und dem Rendering-Verhalten.

Daher kann sich die mit der neuen Publishing-Engine generierte PDF-Ausgabe von der Ausgabe unterscheiden, die mit der bestehenden PDF-Engine generiert wurde (*native PDF-Engine v1*). Unterschiede können in Bereichen wie Text-Layout, Abstand, Stil, Bild-Rendering und Fußnotenformatierung sichtbar sein.

Beispielsweise unterstützt die native PDF-Engine v2 `OpenType` Schriftarten, während die native PDF-Engine v1 hauptsächlich auf `TrueType` Schriftarten basiert. Ähnliche Rendering-Verbesserungen können sich auf das allgemeine Erscheinungsbild der generierten PDFs auswirken.

Weitere Informationen zum Aktivieren der nativen PDF Engine v2 in Ihrer Umgebung finden Sie unter [Konfigurieren der neuen Veröffentlichungs-Engine für Native PDF](./conf-new-pdf-engine.md).

## Empfohlene CSS-Aktualisierungen für die neue Publishing-Engine

Wenn Sie das Erscheinungsbild der PDF-Ausgabe erhalten möchten, die von der nativen PDF-Engine v1 bei Verwendung der nativen PDF-Engine v2 generiert wurde, müssen Sie möglicherweise Ihr benutzerdefiniertes CSS aktualisieren. Die unten beschriebenen empfohlenen CSS-Änderungen können dazu beitragen, die Ausgabekonsistenz nach der Aktivierung der neuen Einstellung aufrechtzuerhalten.

| Beschreibung | Empfohlene CSS-Aktualisierung |
|-------------|------------------------------------------------|
| Skalierte Bilder können aufgrund von Änderungen im Bild-Rendering-Verhalten anders aussehen. | Um das Renderverhalten des Bildes wiederherzustellen, fügen Sie Folgendes hinzu:<br><br> `image-rendering: pixelated` |
| Die Ausrichtung der Führungslinie im Inhaltsverzeichnis (Inhaltsverzeichnis) kann sich aufgrund von Änderungen im Renderverhalten der Führungslinie leicht unterscheiden. | Um die Ausrichtung der Inhaltsverzeichnisleiterelemente wiederherzustellen, passen Sie den Stil der Inhaltsverzeichnisleiterelemente in Ihrem benutzerdefinierten Stylesheet an. Die erforderlichen CSS-Änderungen können je nach Layout und Formatierung des Inhaltsverzeichnisses variieren. |
| Der Textabstand und der Zeilenumbruch können aufgrund von Änderungen beim Schriftartrendering und bei der Verarbeitung des Glyphen-Layouts unterschiedlich sein. | Wenn Ihr Stylesheet die `sans-serif` Schriftfamilie oder Schriftarten verwendet, die Abstandsunterschiede aufweisen, fügen Sie Folgendes hinzu:<br><br> `-ro-glyph-layout-mode: quality;` |
| Fußnotenverweise werden aufgrund von Änderungen am standardmäßigen Fußnotenstil möglicherweise nicht mehr als hochgestellte Markierungen angezeigt. | Um Fußnotenmarkierungen im hochgestellten Stil wiederherzustellen, fügen Sie Folgendes hinzu:<br><br>`.fn::footnote-marker` <br> `{ content: counter(footnote) " ";`<br> `vertical-align: super;`<br>`font-size: 65%;}` |
| Unterstrichener Text kann aufgrund von Änderungen bei der Unterstrichpositionierung mit einem größeren Abstand zwischen dem Text und der Unterstreichung angezeigt werden. | Verwenden Sie zum Wiederherstellen der Unterstrichpositionierung die `text-underline-offset` und passen Sie den Versatzwert nach Bedarf an. Beispiel:<br><br>`text-decoration: underline;`<br>`text-underline-offset: -0.1em;` |
| Der Abstand zwischen Listenmarkierungen und Listenelementtext kann aufgrund von Änderungen im Listenrenderingverhalten unterschiedlich sein. | Um den Abstand wiederherzustellen, erhöhen Sie den linken Abstand für Listenelemente. Beispiel:<br><br>`.step {`<br> ` margin-top: 0.3rem;`<br> `margin-bottom: 0.5rem;`<br> `padding-left: calc(1.5rem + 1ch);}` |
| Der Abstand vor den Überschriften kann aufgrund von Änderungen im Verhalten beim Reduzieren des Rands unterschiedlich sein. | Um den Abstand wiederherzustellen, überprüfen Sie die Ränder benachbarter Elemente und reduzieren oder entfernen Sie überlappende obere und untere Ränder bei Bedarf. Beispiel:<br><br>`h1.chapter { `<br> `margin-top: 0;` <br>`}`<br>`chaptoc-body { margin-bottom: 0;`<br>` }` |
| Mit CSS generierte Markierungen können unterschiedliche Größen oder Stile aufweisen, da sie in unterschiedlichen Ersatzschriftarten dargestellt werden. | Um Markierungen konsistent wiederzugeben, verwenden Sie eine Schriftfamilie, die beide Symbole enthält. Beispiel:<br><br>`::marker {`<br> `font-family: -ro-symbols !important;}` |
| CSS-generierte zirkuläre Listenmarkierungen können aufgrund von Änderungen im Verhalten der Markerpositionierung teilweise abgeschnitten oder abgeschnitten sein. | Um das Erscheinungsbild von kreisförmigen Listenmarkierungen wiederherzustellen, vermeiden Sie die Verwendung der absoluten Positionierung für die Markierung. Wenn eine absolute Positionierung erforderlich ist, geben Sie explizit einen entsprechenden `top` an, um die Markierung korrekt zu positionieren. |
| Die Lesereihenfolge von Listenelementen in der PDF/UA-Ausgabe kann unterschiedlich sein, wenn Listenelemente Positionierungsstile wie `position: relative` verwenden. | Damit die Lesereihenfolge der Struktur des Quelldokuments besser entspricht, wenden Sie die folgende CSS-Eigenschaft auf Listenelemente an:<br><br>`li {`<br>`-ro-paint-reordering: avoid;}` |


## Problemumgehungen für bekannte Probleme

Die folgenden Problemumgehungen können dabei helfen, bekannte Probleme in der generierten PDF-Ausgabe bei der Verwendung der nativen PDF Engine v2 zu beheben.

- `text-decoration` auf Tabelleninhalte angewendeten CSS-Eigenschaften werden in der PDF-Ausgabe nicht gerendert.

  **Problemumgehung**: Wenden Sie die Textdekorationseigenschaften auf `span` Elemente im Tabelleninhalt an, anstatt sie direkt auf die Tabellenelemente anzuwenden.

- `-ro-colorbar-top-left` und `-ro-colorbar-top-right` CSS-Eigenschaften wirken sich nicht auf die Farbleiste in der PDF-Ausgabe aus.

  **Problemumgehung**: Entfernen Sie in `mergedHTML.json` die entsprechenden Werte aus dem Benutzer-Stylesheet oder fügen Sie den Eigenschaftswerten im Dokument-CSS `!important` hinzu, damit sie nicht vom Benutzer-Stylesheet überschrieben werden.

- Farbbalken können zusammengeführt werden, wenn die Seitenbreite eingeschränkt ist, da Farbbalken in der PDF-Ausgabe nicht mit der Seitengröße herunterskaliert werden.

  **Problemumgehung**: Zeigen Sie die grauen und farbigen Balken auf verschiedenen Seiten der Seite an, oder passen Sie die Einstellungen der Farbbalken an, sodass sie sich bei kleineren Seitenbreiten nicht überschneiden.

## Es wurden Probleme mit der neuen Publishing-Engine behoben

Die folgenden Probleme in der PDF-Ausgabe, die mit _Native PDF Engine v1_ generiert wurde, wurden in _Native PDF Engine v2)_:

- Beim Generieren der nativen PDF-Ausgabe für bestimmte Inhalte wird nur die erste Seite in der PDF gerendert, obwohl die dazwischenliegende HTML den vollständigen Inhalt auf mehreren Seiten enthält. (GUIDES-28270)
- Die Lesereihenfolge von Inhalten in der nativen PDF-Ausgabe mit aktivierten Barrierefreiheitseinstellungen ist falsch. Seitenzahlen in Fußzeilen werden vor dem Hauptinhalt und nicht am Ende gelesen. (GUIDES-27790)
- Die Farbleiste in der nativen PDF-Ausgabe erstreckt sich nicht über die gesamte Seitenbreite und überschneidet sich bei der Anpassung der Seitengröße, wodurch einige Farbfelder ausgeblendet werden. (GUIDES-15505)
- Der `CSS:is()pseudo-class`-Selektor wird in der nativen PDF-Ausgabe nicht berücksichtigt, was zu Stilunterschieden im Vergleich zum Browser-Rendering führt. (GUIDES-11328)