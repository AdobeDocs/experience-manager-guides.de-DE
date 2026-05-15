---
title: Konfigurieren einer benutzerdefinierten DITA-Zuordnungsvorlage
description: Erfahren Sie, wie Sie eine benutzerdefinierte DITA-Zuordnungsvorlage konfigurieren
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/16cGf5xY2tAfhc0qIBZeUhYTes-RrdRp-Kj-MoTuacE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 1%

---

# Konfigurieren einer benutzerdefinierten DITA-Zuordnungsvorlage {#id1774F04F05Z}

AEM Guides verfügt über zwei vordefinierte Kartenvorlagen - DITA Map und Bookmap. Sie können Karten basierend auf diesen Vorlagen erstellen oder eigene Karten-Vorlagen definieren, die dann zur Erstellung neuer Karten verwendet werden können.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Zuordnungsvorlagen hinzuzufügen:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Ordner, der zum Speichern der Zuordnungsvorlagendateien konfiguriert wurde. Standardmäßig werden alle Zuordnungsvorlagen im Ordner /content/dam/dita-templates/maps gespeichert.

   >[!NOTE]
   >
   > Informationen zum Konfigurieren eines benutzerdefinierten Speicherorts für Themen- oder Zuordnungsvorlagen finden Sie unter [Konfigurieren eines benutzerdefinierten DITA-Vorlagenordnerpfads](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Klicken Sie **Erstellen** \> **DITA-Vorlage**.

1. Wählen Sie auf der Blueprint-Seite den Typ der Zuordnungsvorlage aus, die Sie erstellen möchten.

   >[!NOTE]
   >
   > Sie können die Zuordnungs- oder Bookmap-Vorlage als Basis für Ihre neue Vorlage verwenden.

1. Klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite „Eigenschaften“ der neuen Vorlage **&quot;**&quot; und **Name** für die Vorlage ein.

   >[!NOTE]
   >
   > Der Name wird automatisch auf Grundlage des Titels der Vorlage vorgeschlagen. Wenn Sie den Namen manuell angeben möchten, stellen Sie sicher, dass der Name keine Leerzeichen, Apostrophe oder geschweifte Klammern enthält und mit &quot;.ditamap“ endet.

1. Klicken Sie auf **Erstellen**.

   Die Meldung Map Created wird angezeigt.

   Sie können die Vorlage zur Bearbeitung im Map-Editor öffnen oder die Vorlagendatei im Vorlagenspeicher speichern. Nachdem die Vorlage erstellt wurde, können Sie den Zuordnungs-Editor verwenden, um die Vorlage entsprechend Ihren Authoring-Anforderungen anzupassen. Nachdem Sie eine Vorlage eingerichtet haben, stellen Sie sicher, dass Sie sie entweder mit einem globalen Profil oder einem Profil auf Ordnerebene verknüpfen.


Wenn Sie das nächste Mal eine neue Karte erstellen, wird Ihre Vorlage auf der Blueprint-Seite angezeigt. Weitere Informationen zum Erstellen einer DITA-Zuordnung finden Sie unter *Verwenden von Adobe Experience Manager Guides*.

>[!TIP]
>
> Best *Practices zur Verwendung benutzerdefinierter Zuordnungsvorlagen finden Sie* Abschnitt Benutzerdefinierte Vorlagen im Handbuch zu Best Practices .

**Übergeordnetes Thema:** [Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md)
