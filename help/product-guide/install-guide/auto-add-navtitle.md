---
title: '@navtitle standardmäßig einschließen'
description: Erfahren Sie, wie Sie @navtitle Attribut standardmäßig einschließen
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 1%

---

# @navtitle standardmäßig einschließen {#id2115BC0J0XA}

Sie können einer Zuordnung verschiedene Arten von Referenzdateien hinzufügen, z. B. Themen-, Referenz-, Aufgaben-, \(Unter\)-Zuordnungen usw. Die meisten dieser Dateien unterstützen das `@navtitle`. Es wird jedoch nicht von vielen Autoren konsistent verwendet. Wenn Sie die Verwendung des Attributs `@navtitle` in allen referenzierten Dateien in einer Zuordnung erzwingen möchten, können Sie dies mit einer einfachen Konfiguration tun.

Nach der Aktivierung wird jeder Referenzdatei, die Sie einer Zuordnung hinzufügen, automatisch das `@navtitle` Attribut zu ihren Eigenschaften hinzugefügt. Der `@navtitle` erhält auch den Wert des `title` Elements des referenzierten Inhalts.

Um `@navtitle` Attribut standardmäßig in die Eigenschaften der Referenzdateien einzuschließen, führen Sie die folgenden Schritte aus:

1. Laden Sie die Datei ui\_config.json herunter.

   Sie können diese Änderung auf globaler Ebene oder auf Ordnerebene vornehmen. Je nachdem, wo Sie diese Änderung vornehmen möchten, müssen Sie die entsprechende ui\_config.json-Datei herunterladen. Weitere Informationen zum Herunterladen der Datei ui\_config.json finden Sie unter [Konfigurieren und Anpassen des XML-Web-Editors](conf-folder-level.md#id2065G300O5Z).

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
