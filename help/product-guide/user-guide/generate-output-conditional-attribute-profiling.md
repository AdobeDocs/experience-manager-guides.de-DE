---
title: Profilerstellung für bedingte Attribute
description: Erfahren Sie, wie Sie in AEM Guides bedingte Attribute erstellen. Verwenden Sie bedingte Attribute im Ordner und in globalen Profilen, um Ihre Inhalte mit Bedingungen zu versehen.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 1%

---

# Profilerstellung für bedingte Attribute {#id1843I0HN0Y4}

Auf Unternehmensebene ist es äußerst wichtig, sicherzustellen, dass Sie über ein standardmäßiges Tagging-System verfügen. Tags oder bedingte Attribute können mit digitalen Assets im Repository verknüpft werden, was bei der Veröffentlichung der Ausgabe basierend auf den ausgewählten Bedingungen hilft. Beispielsweise können Sie bedingte Attribute für Windows- und Mac-Inhalte erstellen. Anschließend fügen Sie diese Attribute den relevanten Inhalten in Ihren Themen hinzu. Zum Zeitpunkt der Veröffentlichung von Inhalten können Sie auswählen, ob Sie nur Windows- oder Mac-Inhalte veröffentlichen möchten.

Mit Adobe Experience Manager Guides können Sie bedingte Attribute einfach mithilfe der entsprechenden DITA-Attribute erstellen und verknüpfen. Sie können bedingte Attribute auf globaler Ebene oder Ordnerebene definieren. Die global definierten Bedingungen sind für alle Projekte sichtbar, und ordnerspezifische Bedingungen sind nur in Projekten sichtbar, die innerhalb des angegebenen Ordners erstellt wurden. Inhaltsautoren können diese bedingten Attribute verwenden, um Inhalte in ihren DITA-Themen oder -Karten, die sie erstellen oder verwenden, mit Bedingungen zu versehen. Diese Bedingungen können dann vom Publisher verwendet werden, um bedingte Vorgaben zu erstellen. Mithilfe der bedingten Vorgaben kann der Publisher entscheiden, welche Bedingung in die veröffentlichte Ausgabe eingeschlossen und von ihr ausgeschlossen werden soll.

>[!NOTE]
>
> Sie können die bedingten Attribute in einem Ordnerprofil erstellen oder bearbeiten, auf das Sie Zugriff haben. Wenn Ihnen Ihr Systemadministrator keinen Zugriff auf ein Ordnerprofil gewährt hat, können Sie die bedingten Attribute im Ordnerprofil nicht erstellen oder bearbeiten.

Um bedingte Attribute zu definieren, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.

1. Wählen Sie im Bedienfeld Tools die Option **Handbücher**.

1. Wählen Sie die **Ordnerprofile** und wählen Sie ein Ordnerprofil aus.

   >[!NOTE]
   >
   > Das globale Profil kann nicht bearbeitet werden.

1. Wählen Sie die Registerkarte **Bedingte Attribute** und dann **Bearbeiten** aus.

   Die Tabelle Bedingte Attribute wird angezeigt.

1. Wählen Sie **Hinzufügen** aus.

1. Geben Sie **Name**, **Value** und einen **Label** für das Attribut ein.

   Sie können ein Profil nur mit dem Attributnamen speichern. Ein Attribut kann jedoch nur verwendet werden, wenn für es ein Wert angegeben wurde. Wenn Sie sowohl - Wert als auch Beschriftung für ein Attribut angeben, zeigt der Web-Editor weiterhin nur den Wert des Attributs an. Der Titel wird dem Veröffentlichungsadministrator zum Zeitpunkt der Erstellung der bedingten Vorgabe angezeigt.

   Der folgende Screenshot zeigt die Definition für das Attribut `platform` mit dem Wert `unix` und der Kennzeichnung `Red Hat Linux`.

   ![](images/add-profile-new.png){align="left"}

1. Wenn Sie weitere Werte für dasselbe Attribut hinzufügen möchten, wählen Sie das Symbol **+** aus und geben Sie zusätzlichen Wert und eine Bezeichnung ein.

1. Wenn Sie weitere Attribute hinzufügen möchten, wählen Sie **Hinzufügen** aus.

1. Wählen Sie **Speichern** aus, um die Änderungen zu speichern.


Das `platform` wird im System gespeichert. Wenn sich ein Autor dafür entscheidet, das `platform`-Attribut in einem DITA-Thema in einem Ordner zu verwenden, kann er die Werte auf der Registerkarte Eigenschaften im Editor anzeigen.

![](images/properties-tab.png){width="350" align="left"}

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
