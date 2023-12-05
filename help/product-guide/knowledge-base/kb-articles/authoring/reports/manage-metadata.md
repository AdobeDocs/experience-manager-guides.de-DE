---
title: Verwalten von Tags für DITA-Dateien in AEM Handbüchern
description: Kurzer Artikel zum Verwalten von cq:tags in AEM Handbüchern
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Hinzufügen, Entfernen und Verwalten von Tags in DITA-Inhalten

Tags eignen sich insbesondere für die Kategorisierung Ihrer Inhalte. Wenn Inhalt ordnungsgemäß mit Tags versehen ist, kann es Ihnen dabei helfen, genaue Themen in Ihrer Ditamap zu finden, und der Endbenutzer findet den entsprechenden Inhalt schneller in Ihrer veröffentlichten Ausgabe.

> **_NOTE:_**  Der folgende Artikel gilt für AEM Guides Build 4.2 (On-Premise) /Feb 2023 (Cloud-Version ) oder höhere Versionen


## Erstellen von Tags

Tagging ist eine native AEM-Funktion, und Ihr AEM Administrator kann bei der ersten Erstellung und Konfiguration dieser Tags behilflich sein.


## Hinzufügen, Entfernen und Verwalten von Tags in Ihrem DITA-Inhalt

**Alle Tags, die in AEM cq erstellt wurden: Tags können hinzugefügt, entfernt und für Ihre DITA-Inhalte verwaltet werden**

Es gibt verschiedene Möglichkeiten, Tags zu DITA-Inhalten hinzuzufügen. Dieser Artikel konzentriert sich jedoch auf die Benutzeroberfläche AEM Guides-Web-Editors.

### Schritte:

1. Wechseln Sie zur Repository-Ansicht in der Guides-Benutzeroberfläche
2. Doppelklicken Sie auf &quot;ditamap&quot;und öffnen Sie in der Kartenansicht.
3. Navigieren Sie zur Registerkarte &quot;Verwalten&quot;
4. Wählen Sie auf der Registerkarte Verwalten die Option Zu Metadaten .
5. Die Liste aller direkten und indirekten Ditamap-Dateien wird hier geladen.
6. Wählen Sie eine oder mehrere Dateien aus und klicken Sie auf das Symbol &quot;Verwalten&quot;. Hier können Sie ausgewählten Dateien Tags hinzufügen.
Sie können auch vorhandene Tags entfernen, die in ausgewählten Dateien verwendet werden.

<img title="Verwalten von Tags in AEM Handbüchern " alt="Verwalten von Tags in DITA " src="ManageTags.jpg">

## Fehlerbehebung und häufig gestellte Fragen

### Liste in manage->metadata ist leer oder unvollständig

Wenn die Liste leer oder unvollständig ist, müssen Sie die Indizierung möglicherweise in Ihrer Ditamap ausführen. Weitere Informationen finden Sie unter [Upgrade-Anweisungen (Index Ihres Inhalts)](/help/product-guide/install-guide/upgrade-xml-documentation.md#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Benutzerdefinierte Metadaten werden nicht in der Liste angezeigt

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Weitere hilfreiche Ressourcen

- [Massen-Tagging mit Map Dashboard (Assets-Benutzeroberfläche)](/help/product-guide/user-guide/map-editor-bulk-tagging.md)
- [Ditamap-Berichte im Web-Editor](/help/product-guide/user-guide/reports-web-editor.md)
- [Tagging in AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Wenden Sie sich bei weiteren Fragen an Ihren jeweiligen CSM.**
