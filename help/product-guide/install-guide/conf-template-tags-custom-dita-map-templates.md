---
title: Konfigurieren einer benutzerdefinierten DITA-Zuordnungsvorlage
description: Erfahren Sie, wie Sie eine benutzerdefinierte DITA-Zuordnungsvorlage konfigurieren
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '331'
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
