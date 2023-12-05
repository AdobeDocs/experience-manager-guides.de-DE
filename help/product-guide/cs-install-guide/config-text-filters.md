---
title: Textfilter konfigurieren
description: Erfahren Sie, wie Sie Textfilter konfigurieren
exl-id: 0963606c-010e-4a72-b7bf-850b86b34a84
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Textfilter konfigurieren {#id21BPD0FK0XA}

AEM Guides bietet die Funktion zum Suchen nach Text in den Dateien, die auf dem ausgewählten Pfad des AEM-Repositorys vorhanden sind. Sie können die Filtersuche verwenden, um Dateien aus dem Repository-Bereich zu suchen oder Dateien zu durchsuchen. Bei der Arbeit im Web Editor müssen Sie das Dialogfeld zum Durchsuchen von Dateien verwenden, um Elemente wie Bilder, Verweise oder wichtige Verweise einzufügen.

Standardmäßig können Sie einige erweiterte Filter verwenden, um die Dateien im AEM Repository zu durchsuchen. Sie können alle DITA-Dateien oder Nicht-DITA-Dateien filtern, die im ausgewählten Pfad vorhanden sind. Sie können auch nach bestimmten Werten in den Attributen von DITA-Elementen suchen. Sie können auch nach Dateien suchen, die vom angegebenen Benutzer ausgecheckt wurden.

>[!NOTE]
>
> Sie können auch das globale Profil konfigurieren und weitere Filter für die Suche hinzufügen.

Führen Sie die folgenden Schritte aus, um die Textfilter zu konfigurieren:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Instrumente**.
1. Auswählen **Handbücher** aus der Liste der Tools und klicken Sie auf die Schaltfläche **Ordnerprofile**.
1. Klicken Sie auf **Globales Profil** Kachel.
1. Klicken Sie auf **Konfiguration des XML-Editors**.
1. Klicken Sie auf **Bearbeiten** Symbol oben.
1. Klicken Sie auf **Herunterladen** -Symbol, um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
   1. Konfigurieren Sie die Filter in der Datei. Sie können auch benutzerdefinierte Filter hinzufügen, wie im folgenden Beispiel gezeigt:

      Das folgende Codefragment zeigt, wie Sie Filteroptionen für DITA-Dateien, Nicht-DITA-, DITA-Elemente und Ausgecheckt von Dateien hinzufügen. Es enthält auch einen benutzerdefinierten Filter - Tags.

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

      Im obigen Codefragment ist der erste Filter für DITA-Dateien. Die Filterdefinition akzeptiert die folgenden Parameter:

      ****Titel****: Der Anzeigename des Filters. Dieser Titel wird als Filteroption im Dialogfeld zum Durchsuchen von Dateien angezeigt.

      ****Eigenschaft****: Die Eigenschaft, die in den Metadaten der Datei übereinstimmen soll. Um beispielsweise nur Dateien zuzulassen, deren -Eigenschaft die dita\_class -Metadaten enthält, verwendet der Eigenschaftenfilter den Wert &quot;jcr:content/metadata/dita\_class&quot;.

      ****Vorgang **:**Geben Sie &quot;exists&quot;an, um für das Vorhandensein des im Eigenschaftsparameter angegebenen Werts zu stimmen.

1. Laden Sie die aktualisierte Datei ui\_config.json hoch, die die hinzugefügten Filter enthält.

Die konfigurierten Filter sind im Filterbereich verfügbar.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
