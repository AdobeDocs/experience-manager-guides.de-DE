---
title: Erstellen von Karten basierend auf benutzerdefinierten Vorlagen
description: Erfahren Sie, wie Sie eine Vorlage erstellen, sie zum Erstellen neuer Zuordnungsdateien verwenden und den definierten Titel an eine DITA-Zuordnung in AEM Guides weitergeben.
feature: Authoring, Map Editor
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 0%

---

# Erstellen von Karten basierend auf benutzerdefinierten Vorlagen {#id225VF0808MP}

Sie können benutzerdefinierte Zuordnungsvorlagen erstellen und diese zum Erstellen von DITA-Maps zusammen mit den Themenvorlagen und Zuordnungsvorlagen verwenden, auf die in der Zuordnungsvorlage verwiesen wird

Sie können von der benutzerdefinierten Zuordnungsvorlage aus auf andere Zuordnungsvorlagen und Themenvorlagen verweisen. Die referenzierten Zuordnungsvorlagen können sich auf verschiedene Zuordnungsvorlagen, Themenvorlagen, Themen, Zuordnungen, Bilder, Videos und andere Assets beziehen. Die benutzerdefinierte Kartenvorlage kann Ihnen dabei helfen, die Zuordnungsvorlagen und die gesamte referenzierte Ordnerstruktur einfach zu replizieren. Diese benutzerdefinierten Vorlagen sind besonders nützlich, um mehrere Karten mit rekursiven Strukturen und Referenzen zu erstellen und neu zu erstellen.

>[!NOTE]
>
> Themenvorlagen werden nicht rekursiv erstellt. Es werden nur Themenvorlagen generiert, die sich direkt in der Zuordnungsvorlage befinden, und jede Themenvorlage innerhalb einer Themenvorlage wird einfach direkt in der übergeordneten Vorlage referenziert.

## Benutzerdefinierte Vorlagen erstellen

Mit AEM Guides können Sie benutzerdefinierte Maps und Themen aus dem Ordner dita-templates erstellen. Sie können diese benutzerdefinierten Vorlagen verwenden, um Ihre Karte und Ihr Thema zu erstellen. Sie können diese Vorlagen auch für Ihre Autoren freigeben und sie zum Erstellen ihrer Dateien verwenden. Mithilfe dieser Vorlagen können Sie Autoren erlauben, separate Kopien bestimmter Ressourcen zu speichern, die sich im Ordner &quot;Vorlagen&quot;befinden.

>[!NOTE]
>
> Alle Ressourcen, auf die nur verwiesen und die in allen Versionen gepflegt werden sollen, müssen außerhalb des Vorlagenordners aufbewahrt werden.


Sie können Zuordnungs- und Themenvorlagen wie folgt erstellen:
1. Vorlagenbereich des Bereichs [Links ](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Vorlagen in der Assets-Benutzeroberfläche](#templates-assets-ui)
1. [Optionen, Menü](#templates-in-assets-ui)

### Vorlagen in der Assets-Benutzeroberfläche {#templates-assets-ui}

**Themenvorlage**

Führen Sie die folgenden Schritte aus, um eine Themenvorlage zu erstellen:

1. Navigieren Sie in der **Assets-Benutzeroberfläche** zum Ordner &quot;dita-templates&quot;.

   ![](images/dita-templates.png){width="800" align="left"}

1. Klicken Sie auf den Ordner **topics** , um ihn zu öffnen. Klicken Sie auf **Erstellen \> DITA-Vorlage**.
1. Wählen Sie auf der Blueprint-Seite **Thema** aus und klicken Sie dann auf **Weiter**.
1. Geben Sie auf der Seite Eigenschaften die Themenvorlage **Titel** an.
1. Geben Sie die Datei **Name** an

   >[!NOTE]
   >
   > Der Dateiname muss die Erweiterung .dita aufweisen.

1. \(Optional\) Fügen Sie eine Beschreibung hinzu.
1. Klicken Sie auf **Erstellen**. Die Nachricht zur Erstellung der Themenvorlage wird angezeigt. Anschließend können Sie die Themenvorlage öffnen und bearbeiten.

**Zuordnungsvorlage**

Führen Sie die folgenden Schritte aus, um eine Zuordnungsvorlage zu erstellen:

1. Navigieren Sie in der **Assets-Benutzeroberfläche** zum Ordner &quot;dita-templates&quot;.
1. Klicken Sie auf den Ordner **maps** , um ihn zu öffnen.
1. Klicken Sie auf **Erstellen \> DITA-Vorlage.**

   ![](images/create-dita-template.png){width="300" align="left"}

1. Wählen Sie auf der Blueprint-Seite **Map** aus und klicken Sie auf **Next**.
1. Geben Sie auf der Seite Eigenschaften die Zuordnungsvorlage **Titel** an.
1. Geben Sie die Datei **Name** an.

   >[!NOTE]
   >
   > Der Dateiname muss die Erweiterung .ditamap aufweisen.

1. (Optional\) Fügen Sie eine Beschreibung hinzu. Klicken Sie auf **Erstellen**. Die erstellte Meldung wird angezeigt. Anschließend können Sie die Zuordnungsvorlage öffnen und bearbeiten. Sie können die Referenzen für die Themenvorlagen, Zuordnungsvorlagen und auch andere Assets in der Zuordnungsvorlage hinzufügen.

### Optionen, Menü {#options-menu}

Gehen Sie wie folgt vor, um eine Zuordnung oder Themenvorlage zu erstellen:

1. Wählen Sie den Ordner **Zuordnung** oder **Thema** im aktuellen Vorlagenordner aus. Beispielsweise den Ordner `dita-templates`.
1. Wählen Sie im Menü **Optionen** die Option **Zuordnungsvorlage erstellen** oder **Themenvorlage erstellen** aus.

   Das Dialogfeld **Neue Zuordnungsvorlage erstellen** oder **Neue Themenvorlage erstellen** wird geöffnet.
1. Geben Sie den Titel und den Namen der neuen Vorlage ein.
1. Wählen Sie aus der Dropdownliste **Vorlage** den Typ der Vorlage aus, die Sie erstellen möchten.

Die erstellte Meldung wird angezeigt. Sie können die Vorlage Ihrem globalen Profil oder Profil auf Ordnerebene hinzufügen. Die neue Vorlage wird dann im Prozess der Themen- oder Zuordnungserstellung angezeigt und Sie können damit Zuordnungen oder Themen erstellen.


Ihr Administrator kann auch einen Ordner erstellen und so konfigurieren, dass er der Ordner ist, in dem Sie die Vorlagen erstellen und speichern können.

Je nach Setup erfahren Sie, wie Sie den benutzerdefinierten Ordnerpfad für DITA-Vorlagen konfigurieren:
<details>
    <summary> Cloud Services </summary>

Erfahren Sie im Cloud Service-Installations- und Konfigurationshandbuch, wie Sie den benutzerdefinierten Ordnerpfad für DITA-Vorlagen ](../install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) konfigurieren.[
</details>

<details>
    <summary> On-Premise Software</summary>

Erfahren Sie im On-Premise-Installations- und Konfigurationshandbuch, wie Sie den benutzerdefinierten Ordnerpfad für DITA-Vorlagen ](../cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) konfigurieren.[
</details>

## Weitergeben des in den Vorlagen definierten Titels

Wenn Sie den Titel des Themas oder der in Ihrer Vorlage verwendeten Zuordnung an die mit dieser Vorlage erstellten DITA-Maps weitergeben möchten, verwenden Sie geschweifte Klammern um den Titel.

Beispiel

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> Nur das erste Vorkommen von geschweiften Klammern wird durch den Titel ersetzt.

Wenn Sie keine geschweiften Klammern um den Titel verwenden, wird die resultierende DITA-Zuordnung nur das erste Element ausgewählt und die Verschachtelung des Titels wird nicht aus der Vorlage ausgewählt und sieht wie folgt aus:

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> Sie können auch die geschweiften Klammern um den Text verwenden, um die verschachtelte Struktur von den benutzerdefinierten Vorlagen an Ihre DITA-Maps zu übergeben.

Beispiel

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




## Verwenden Sie die Zuordnungsvorlage, um neue Zuordnungen zu erstellen

>[!NOTE]
>
> Die Zuordnungsvorlage muss von Ihrem Administrator konfiguriert und für die Bearbeitung zur Verfügung gestellt werden. Weitere Informationen finden Sie im Abschnitt *Bearbeitungsvorlagen konfigurieren* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

Führen Sie die folgenden Schritte aus, um eine Zuordnung mithilfe der benutzerdefinierten Zuordnungsvorlage zu erstellen:

1. Navigieren Sie in der Benutzeroberfläche von **Assets** zu dem Ordner, in dem Sie die Zuordnung erstellen möchten.
1. Klicken Sie auf **Erstellen \> DITA Map**.
1. Wählen Sie auf der Blueprint-Seite die gewünschte Zuordnungsvorlage aus und klicken Sie auf **Weiter**. Wenn Sie beispielsweise eine Zuordnungsvorlage &quot;test-template&quot;erstellt haben, wählen Sie sie aus.
1. Geben Sie auf der Seite Eigenschaften die Zuordnung **Titel** an.
1. Geben Sie die Datei **Name** an.

   >[!NOTE]
   >
   > Der Dateiname muss die Erweiterung .ditamap aufweisen.

1. Klicken Sie auf **Erstellen**. Die Nachricht Zuordnungserstellung wird angezeigt.


Die Zuordnung generiert alle Assets, auf die im Vorlagenordner verwiesen wird. Einige Asset-Typen, die in einer Zuordnung referenziert werden, können wie folgt aussehen:

- Wenn die Zuordnung den Verweis auf eine Themenvorlage enthält, wird eine Kopie davon im Ordner erstellt, in derselben Hierarchie wie im Ordner &quot;topics&quot;im Ordner &quot;`dita-templates`&quot;.
- Wenn die Zuordnung den Verweis auf eine Zuordnungsvorlage enthält, wird eine Kopie davon im Ordner erstellt, in derselben Hierarchie wie im Ordner &quot;maps&quot;im Ordner &quot;`dita-templates`&quot;.
- Wenn die Zuordnung den generischen Verweis auf ein Thema oder eine Zuordnung außerhalb des Ordners `dita-templates/topics` oder `dita-templates/maps` enthält, wird nur auf dasselbe verwiesen und es wird keine Kopie erstellt.

  >[!NOTE]
  >
  > `dita-templates/topics` und `dita-templates/maps` sind die Standardpfade in Guides und können konfiguriert werden.


  Wenn sich in der Zuordnungsvorlage eine Schlüsseldefinition für die Themenvorlage befindet, wird ein neuer Schlüssel &quot;\(also neues Thema\)&quot;erstellt und in der Zuordnung auf diesen verwiesen.

- Wenn eine andere Zuordnung oder ein anderes Thema auf derselben Ebene im Ordner erstellt wird, werden die Namen der neu erstellten Assets mit 0,1,2 usw. angehängt. Sie können wählen, ob Sie die Karte zur Bearbeitung öffnen oder die Zuordnungsdatei im Repository speichern möchten.

**Übergeordnetes Thema:**[ Arbeiten mit dem Map-Editor](map-editor.md)
