---
title: '@navtitle standardmäßig einschließen'
description: Erfahren Sie, wie Sie @navtitle Attribut standardmäßig einschließen
exl-id: 38711c0c-efa8-461a-92e1-ecfcdcdd36d3
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/h8rkQYPX4uJRWTdJKIHmdGrzbCIh--HtTrhsQ5QeuL8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 326
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



**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
