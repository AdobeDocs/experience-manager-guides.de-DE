---
title: Benutzerdefinierte DITA-Zuordnungsvorlage konfigurieren
description: Erfahren Sie, wie Sie benutzerdefinierte DITA-Zuordnungsvorlagen konfigurieren
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 1%

---

# Benutzerdefinierte DITA-Zuordnungsvorlage konfigurieren {#id1774F04F05Z}

AEM Guides sind mit zwei nativen Kartenvorlagen ausgestattet - DITA-Map und Bookmap. Sie können auf diesen Vorlagen basierende Karten erstellen oder eigene Zuordnungsvorlagen definieren, die dann zur Erstellung neuer Maps verwendet werden können.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Zuordnungsvorlagen hinzuzufügen:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Ordner, der zum Speichern der Zuordnungsvorlagendateien konfiguriert ist. Standardmäßig werden alle Zuordnungsvorlagen im Ordner /content/dam/dita-templates/maps gespeichert.

   >[!NOTE]
   >
   > Informationen zum Konfigurieren eines benutzerdefinierten Speicherorts zum Speichern von Themen oder Zuordnungsvorlagen finden Sie unter [Benutzerdefinierten DITA-Vorlagenordnerpfad konfigurieren](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Klicks **Erstellen** \> **DITA-Vorlage**.

1. Wählen Sie auf der Blueprint-Seite den Typ der zu erstellenden Zuordnungsvorlage aus.

   >[!NOTE]
   >
   > Sie können die Vorlage Map oder Bookmap als Basis für Ihre neue Vorlage verwenden.

1. Klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite mit den neuen Vorlageneigenschaften eine **Titel** und **Name** für die Vorlage.

   >[!NOTE]
   >
   > Der Name wird basierend auf dem Titel der Vorlage automatisch vorgeschlagen. Wenn Sie den Namen manuell angeben möchten, stellen Sie sicher, dass der Name keine Leerzeichen, Apostroph oder Klammern enthält und mit .ditamap endet.

1. Klicken Sie auf **Erstellen**.

   Die Meldung Zuordnungserstellung wird angezeigt.

   Sie können die Vorlage zum Bearbeiten im Map Editor öffnen oder die Vorlagendatei am Speicherort der Vorlage speichern. Nachdem die Vorlage erstellt wurde, können Sie den Map Editor verwenden, um die Vorlage entsprechend Ihren Authoring-Anforderungen anzupassen. Nachdem eine Vorlage erstellt wurde, stellen Sie sicher, dass Sie sie entweder mit einem globalen Profil oder einem Profil auf Ordnerebene verknüpfen.


Wenn Sie das nächste Mal eine neue Zuordnung erstellen, wird Ihre Vorlage auf der Blueprint-Seite angezeigt. Weitere Informationen zum Erstellen einer DITA-Zuordnung finden Sie im as a Cloud Service Handbuch Verwenden von Adobe Experience Manager-Guides .

>[!TIP]
>
> Siehe *Benutzerdefinierte Vorlagen* im Best Practices-Handbuch für Best Practices zur Verwendung benutzerdefinierter Zuordnungsvorlagen.

**Übergeordnetes Thema:**[ Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md)
