---
title: Verwalten von Tags für DITA-Dateien in AEM Guides
description: Informationen zum Verwalten von cq:tags in AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Hinzufügen , Entfernen und Verwalten von Tags in DITA-Inhalten

Tags sind nützlich, um Ihre Inhalte zu kategorisieren. Wenn Inhalte ordnungsgemäß mit Tags versehen sind, können sie Ihnen dabei helfen, genaue Themen in Ihrer Imagemap zu finden, und der Endbenutzer findet den entsprechenden Inhalt schneller in Ihrer veröffentlichten Ausgabe

> **_HINWEIS_** Der folgende Artikel gilt für AEM Guides Build 4.2 (On-Premise) /Feb 2023 (Cloud-Version ) oder höhere Versionen


## Tags erstellen

Tagging ist eine native AEM-Funktion, und Ihr AEM-Administrator kann Ihnen bei der ersten Erstellung und Konfiguration dieser Tags behilflich sein.


## Hinzufügen, Entfernen und Verwalten von Tags in DITA-Inhalten

**Alle in AEM cq: erstellten Tags können für DITA-Inhalte hinzugefügt, entfernt und verwaltet werden**

Es gibt verschiedene Möglichkeiten, Tags zu DITA-Inhalten hinzuzufügen, aber dieser Artikel konzentriert sich auf die Benutzeroberfläche des AEM Guides-Web-Editors.

### Schritte:

1. Zur Repository-Ansicht in der Handbuch-Benutzeroberfläche
2. Doppelklicken Sie auf Ditamap und öffnen Sie es in der Kartenansicht
3. Zur Registerkarte Verwalten wechseln
4. Gehen Sie auf der Registerkarte Verwalten zur Option Metadaten .
5. Alle Ihre direkten und indirekten Sitamap-Dateien werden hier geladen.
6. Wählen Sie eine oder mehrere Dateien aus und klicken Sie auf das Symbol „Verwalten“. Hier können Sie Tags zu ausgewählten Dateien hinzufügen.
Sie können auch vorhandene Tags entfernen, die in ausgewählten Dateien häufig verwendet werden.

<img title="Verwalten von Tags in AEM Guides " alt="Verwalten von Tags in DITA " src="ManageTags.jpg">

## Fehlerbehebung und häufig gestellte Fragen

### Liste in manage->metadata ist leer oder unvollständig

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Upgrade-Anweisungen (Inhalt indizieren)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=de#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Benutzerdefinierte Metadaten werden nicht in der Liste angezeigt

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Weitere hilfreiche Ressourcen

- [Bulk-Tagging mit dem Zuordnungs-Dashboard (Assets-Benutzeroberfläche)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=de)
- [Ditamap-Berichte im Web-Editor](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=de)
- [Tagging in AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=de)


**Wenden Sie sich bei weiteren Fragen an Ihren jeweiligen CSM**
