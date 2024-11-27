---
title: Bedingte Attributprofilierung
description: Erfahren Sie, wie Sie bedingte Attribute in AEM Guides erstellen. Verwenden Sie bedingte Attribute im Ordner und globale Profile, um Ihren Inhalt an Bedingungen zu knüpfen.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Bedingte Attributprofilierung {#id1843I0HN0Y4}

Auf Unternehmensebene ist es äußerst wichtig sicherzustellen, dass Sie über ein Standard-Tagging-System verfügen. Tags oder bedingte Attribute können mit digitalen Assets im Repository verknüpft werden, wodurch die Ausgabe anhand der ausgewählten Bedingungen veröffentlicht werden kann. Beispielsweise können Sie bedingte Attribute für Windows- und Mac-Inhalte erstellen. Anschließend fügen Sie diese Attribute zum relevanten Inhalt in Ihren Themen hinzu. Zum Zeitpunkt der Veröffentlichung von Inhalten können Sie festlegen, ob Sie nur Inhalte von Windows oder Mac veröffentlichen möchten.

Mit AEM Guides können Sie bedingte Attribute mithilfe der entsprechenden DITA-Attribute einfach erstellen und zuordnen. Sie können bedingte Attribute auf globaler Ebene oder auf Ordnerebene definieren. Die global definierten Bedingungen sind für alle Projekte sichtbar, und ordnerspezifische Bedingungen sind nur in Projekten sichtbar, die innerhalb des angegebenen Ordners erstellt wurden. Inhaltsautoren können diese bedingten Attribute verwenden, um Inhalte in ihren DITA-Themen oder -Maps, die sie erstellen oder verwenden, an Bedingungen zu knüpfen. Diese Bedingungen können dann vom Publisher zum Erstellen bedingter Vorgaben verwendet werden. Mithilfe der bedingten Vorgaben kann der Herausgeber entscheiden, welche Bedingung ein- und von der veröffentlichten Ausgabe ausgeschlossen werden soll.

>[!NOTE]
>
> Sie können die bedingten Attribute in einem Ordnerprofil erstellen oder bearbeiten, auf das Sie Zugriff haben. Wenn Ihnen Ihr Systemadministrator keinen Zugriff auf ein Ordnerprofil gewährt hat, können Sie die bedingten Attribute nicht im Ordnerprofil erstellen oder bearbeiten.

Um bedingte Attribute zu definieren, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die Kachel **Ordnerprofile** und wählen Sie ein Ordnerprofil aus.

   >[!NOTE]
   >
   > Das globale Profil kann nicht bearbeitet werden.

1. Klicken Sie auf die Registerkarte **Bedingte Attribute** und klicken Sie auf **Bearbeiten**.

   Die Tabelle Bedingte Attribute wird angezeigt.

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie den **Namen**, den **Wert** und eine **Bezeichnung** für das Attribut ein.

   Sie können ein Profil mit nur dem Attributnamen speichern. Ein Attribut kann jedoch nur verwendet werden, wenn dafür ein Wert angegeben ist. Wenn Sie für ein Attribut sowohl -Wert als auch -Beschriftung angeben, zeigt der Web Editor weiterhin nur den Wert des Attributs an. Der Titel wird dem Publishing-Administrator zum Zeitpunkt der Erstellung einer bedingten Vorgabe angezeigt.

   Der folgende Screenshot zeigt die Definition für das Attribut `platform` mit dem Wert `unix` und der Bezeichnung `Red Hat Linux`.

   ![](images/add-profile.png){width="800" align="left"}

1. Wenn Sie weitere Werte für dasselbe Attribut hinzufügen möchten, klicken Sie auf das Symbol **+** und geben Sie zusätzlichen Wert und eine Beschriftung ein.

1. Wenn Sie weitere Attribute hinzufügen möchten, klicken Sie auf **Hinzufügen**.

1. Klicken Sie auf **Speichern**, um die Änderungen zu speichern.


Das Attribut `platform` wird im System gespeichert. Wenn ein Autor beschließt, das Attribut `platform` in einem DITA-Thema in einem Ordner zu verwenden, werden ihm die Werte auf der Registerkarte &quot;Eigenschaften&quot;im Web Editor angezeigt.

![](images/properties-tab.png){width="350" align="left"}

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
