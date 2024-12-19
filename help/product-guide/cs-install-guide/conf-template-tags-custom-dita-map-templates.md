---
title: Konfigurieren einer benutzerdefinierten DITA-Zuordnungsvorlage
description: Erfahren Sie, wie Sie eine benutzerdefinierte DITA-Zuordnungsvorlage konfigurieren
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 83971ee35a19cf0146ddd034b1ae7a345f587663
workflow-type: tm+mt
source-wordcount: '489'
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


Wenn Sie das nächste Mal eine neue Karte erstellen, wird Ihre Vorlage auf der Blueprint-Seite angezeigt. Weitere Informationen zum Erstellen einer DITA-Zuordnung finden Sie im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

>[!TIP]
>
> Best *Practices zur Verwendung benutzerdefinierter Zuordnungsvorlagen finden Sie* Abschnitt Benutzerdefinierte Vorlagen im Handbuch zu Best Practices .


## Anpassen der Anzahl der Verweise in einer DITA-Zuordnung

Sie können den Schwellenwert für die asynchrone Verarbeitung auf der Grundlage der Anzahl der Verweise in der DITA-Zuordnung konfigurieren. Standardmäßig werden Zuordnungen mit mehr als 5 Verweisen über asynchrone Vorgänge erstellt, während Zuordnungen mit weniger Verweisen weiterhin synchrone Vorgänge verwenden.


Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um die Anzahl der Verweise in der DITA-Zuordnungsvorlage anzugeben, damit der Prozess synchron bleibt:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| com.adobe.fmdita.xmleditor.config.XmlEditorConfig | xmleditor.asyncmapcreation | > 0 <br> **Standardwert**: 5 |

Beim Erstellen einer DITA-Zuordnung mit großen Themenverweisen mithilfe einer benutzerdefinierten Vorlage schlägt die Zuordnungserstellung auf dem Cloud-Server fehl, wenn die Gesamtverarbeitungszeit 60 Sekunden überschreitet.

Um dies zu verhindern, konfigurieren Sie **asynchrone DITA-Map-Erstellung** in XmlEditorConfig, die es Aufgaben ermöglicht, parallel ausgeführt zu werden, und die Verarbeitungszeiten für größere DITA-Maps reduziert.

**Übergeordnetes Thema:** [Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md)
