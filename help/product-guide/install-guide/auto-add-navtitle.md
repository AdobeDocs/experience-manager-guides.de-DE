---
title: '@navtitle standardmäßig einschließen'
description: Erfahren Sie, wie Sie @navtitle Attribut standardmäßig einschließen
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/bwVOZrkVrn6QPq7BoUttFvnFAzdLIL6--JGCoHYkA0o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 1%

---

# @navtitle standardmäßig einschließen {#id2115BC0J0XA}

Sie können einer Zuordnung verschiedene Arten von Referenzdateien hinzufügen, z. B. Themen-, Referenz-, Aufgaben-, \(Unter\)-Zuordnungen usw. Die meisten dieser Dateien unterstützen das `@navtitle`. Es wird jedoch nicht von vielen Autoren konsistent verwendet. Wenn Sie die Verwendung des Attributs `@navtitle` in allen referenzierten Dateien in einer Zuordnung erzwingen möchten, können Sie dies mit einer einfachen Konfiguration tun.

Nach der Aktivierung wird jeder Referenzdatei, die Sie einer Zuordnung hinzufügen, automatisch das `@navtitle` Attribut zu ihren Eigenschaften hinzugefügt. Der `@navtitle` erhält auch den Wert des `title` Elements des referenzierten Inhalts.

Um `@navtitle` Attribut standardmäßig in die Eigenschaften der Referenzdateien einzuschließen, führen Sie die folgenden Schritte aus:

1. Laden Sie die Datei ui\_config.json herunter.

   Sie können diese Änderung auf globaler Ebene oder auf Ordnerebene vornehmen. Je nachdem, wo Sie diese Änderung vornehmen möchten, müssen Sie die entsprechende ui\_config.json-Datei herunterladen. Weitere Informationen zum Herunterladen der Datei ui\_config.json finden Sie unter [Konfigurieren und Anpassen des XML-Editors](conf-folder-level.md#id2065G300O5Z).

1. Suchen Sie nach der `ditaAttributes`.

   Die Standarddefinition von `ditaAttributes` lautet:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Ändern Sie den `required` wie folgt:

   ```json
   "required": {"navtitle": true}
   ```

1. Speichern Sie die Datei.

1. Laden Sie die Datei in das entsprechende Profil hoch \(Global oder Ordner\).


Bei dieser Konfiguration enthält jede Referenzdatei, die Sie einer Zuordnung hinzufügen, standardmäßig das `@navtitle`.
