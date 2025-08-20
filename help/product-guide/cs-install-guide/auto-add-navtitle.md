---
title: '@navtitle standardmäßig einschließen'
description: Erfahren Sie, wie Sie @navtitle Attribut standardmäßig einschließen
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: a3c7973868549c72e868c05a3fc6ca8bdce9bce3
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# @navtitle standardmäßig einschließen {#id2115BC0J0XA}

Sie können einer Zuordnung verschiedene Arten von Referenzdateien hinzufügen, z. B. Themen-, Referenz-, Aufgaben-, \(Unter\)-Zuordnungen usw. Die meisten dieser Dateien unterstützen das `@navtitle`. Es wird jedoch nicht von vielen Autoren konsistent verwendet. Wenn Sie die Verwendung des Attributs `@navtitle` in allen referenzierten Dateien in einer Zuordnung erzwingen möchten, können Sie dies mit einer einfachen Konfiguration tun.

Nach der Aktivierung wird jeder Referenzdatei, die Sie einer Zuordnung hinzufügen, automatisch das `@navtitle` Attribut zu ihren Eigenschaften hinzugefügt. Der `@navtitle` erhält auch den Wert des `title` Elements des referenzierten Inhalts.

Um `@navtitle` Attribut standardmäßig in die Eigenschaften der Referenzdateien einzuschließen, führen Sie die folgenden Schritte aus:

1. Um die Konfigurationsdatei der Benutzeroberfläche herunterzuladen, melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie **oben auf** Bearbeiten“
1. Klicken Sie auf **Herunterladen**, um die Datei ui\_config.json auf Ihr lokales System herunterzuladen.
1. Sie können diese Änderung auf globaler Ebene oder auf Ordnerebene vornehmen. Je nachdem, wo Sie diese Änderung vornehmen möchten, müssen Sie die entsprechende ui\_config.json-Datei herunterladen. Weitere Informationen zum Herunterladen der Datei ui\_config.json finden Sie unter [Konfigurieren und Anpassen des XML-Web-Editors](conf-folder-level.md#id2065G300O5Z).

1. Suchen Sie nach der `ditaAttributes`.

   Die Standarddefinition von `ditaAttributes` lautet:

   ```
   "ditaAttributes": {
                           "attributes": [],
                           "constraint": false,
                           "required": {}
                           },
   ```

1. Ändern Sie den `required` wie unten dargestellt:

   ```
   "required": {"navtitle": true}
   ```

   Bei Festlegung auf `true` wird die Schaltfläche **Navigationstitelattribut aktualisieren** in der Editor-Symbolleiste angezeigt. Wenn sie auf `false` oder leer gelassen wird, bleibt die Schaltfläche im Editor ausgeblendet.
1. Speichern Sie die Datei.

1. Laden Sie die Datei in das entsprechende Profil hoch \(Global oder Ordner\).


Bei dieser Konfiguration enthält jede Referenzdatei, die Sie einer Zuordnung hinzufügen, standardmäßig das `@navtitle`.



**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
