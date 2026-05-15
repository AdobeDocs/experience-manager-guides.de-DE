---
title: Verwalten von Tags für DITA-Dateien in AEM Guides
description: Informationen zum Verwalten von cq:tags in AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/u3MZ3fUZIp-FYQE895I7kDRkF3l96KhwYMRMJ-rG2RE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 0%

---

# Hinzufügen , Entfernen und Verwalten von Tags in DITA-Inhalten

Tags sind nützlich, um Ihre Inhalte zu kategorisieren. Wenn Inhalte ordnungsgemäß mit Tags versehen sind, können sie Ihnen dabei helfen, genaue Themen in Ihrer Imagemap zu finden, und der Endbenutzer findet den entsprechenden Inhalt schneller in Ihrer veröffentlichten Ausgabe

> **_HINWEIS:_** Der folgende Artikel gilt für AEM Guides Build 4.2 (On-Premise) /Feb 2023 (Cloud-Version ) oder höher


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

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Upgrade-Anweisungen (Inhalt indizieren)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Benutzerdefinierte Metadaten werden nicht in der Liste angezeigt

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Weitere hilfreiche Ressourcen

- [Bulk-Tagging mit dem Zuordnungs-Dashboard (Assets-Benutzeroberfläche)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Ditamap-Berichte im Web-Editor](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Tagging in AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Wenden Sie sich bei weiteren Fragen an Ihren jeweiligen CSM**
