---
title: Textfilter konfigurieren
description: Erfahren Sie, wie Sie Textfilter konfigurieren
exl-id: 0963606c-010e-4a72-b7bf-850b86b34a84
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/kni90T4QnDideo-hhxJZRje3H4WTEvBfwEaLa2zOzcg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9baid: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 0%

---

# Textfilter konfigurieren {#id21BPD0FK0XA}

AEM Guides bietet die Funktion, um nach Text in den Dateien zu suchen, die im ausgewählten Pfad des AEM-Repositorys vorhanden sind. Sie können die Filtersuche verwenden, um Dateien im Repository-Bereich zu suchen oder Dateien zu durchsuchen. Beim Arbeiten im Web-Editor müssen Sie das Dialogfeld zum Durchsuchen von Dateien verwenden, um Elemente wie Bilder, Verweise oder Schlüsselverweise einzufügen.

Standardmäßig können Sie einige erweiterte Filter verwenden, um die Dateien im AEM-Repository zu durchsuchen. Sie können alle DITA-Dateien oder Nicht-DITA-Dateien filtern, die im ausgewählten Pfad vorhanden sind. Sie können auch in den Attributen von DITA-Elementen nach bestimmten Werten suchen. Sie können auch nach Dateien suchen, die vom angegebenen Benutzer ausgecheckt wurden.

>[!NOTE]
>
> Sie können auch das globale Profil konfigurieren und weitere Filter für die Suche hinzufügen.

Führen Sie die folgenden Schritte aus, um die Textfilter zu konfigurieren:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Klicken Sie auf **XML-Editor-Konfiguration**.
1. Klicken Sie oben **auf** Bearbeiten“.
1. Klicken Sie auf **Herunterladen**, um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
   1. Konfigurieren Sie die Filter in der Datei . Sie können auch benutzerdefinierte Filter hinzufügen, wie im folgenden Beispiel gezeigt:

      Das folgende Codefragment zeigt, wie Sie Filteroptionen für DITA-Dateien, Nicht-DITA- und DITA-Elemente hinzufügen und durch Dateien ausgecheckt werden. Es enthält auch einen benutzerdefinierten Filter - Tags.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      Im obigen Code-Snippet ist der erste Filter für DITA-Dateien. Die Filterdefinition akzeptiert die folgenden Parameter:

      ****Titel****: Der Anzeigename des Filters. Dieser Titel wird als Filteroption im Dialogfeld zum Durchsuchen von Dateien angezeigt.

      ****Property****: Die Eigenschaft, die in den Metadaten der Datei abgeglichen werden soll. Um beispielsweise nur die Dateien zuzulassen, die die Metadaten „dita\_class“ in ihrer Eigenschaft enthalten, nimmt der Eigenschaftsfilter „jcr:content/metadata/dita\_class“ als Wert.

      ****Operation **:**Geben Sie „exists“ an, um mit dem Vorhandensein des im Eigenschaftenparameter angegebenen Werts abzugleichen

1. Laden Sie die aktualisierte Datei ui\_config.json hoch, die die hinzugefügten Filter enthält.

Die konfigurierten Filter sind im Bedienfeld Filter verfügbar.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
