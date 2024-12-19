---
title: Profilerstellung für bedingte Attribute
description: Erfahren Sie, wie Sie in AEM Guides bedingte Attribute erstellen. Verwenden Sie bedingte Attribute im Ordner und in globalen Profilen, um Ihre Inhalte mit Bedingungen zu versehen.
exl-id: 5ec7666e-df6b-4b0d-b6c2-cdc395fcccc5
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Profilerstellung für bedingte Attribute {#id1843I0HN0Y4}

Auf Unternehmensebene ist es äußerst wichtig, sicherzustellen, dass Sie über ein standardmäßiges Tagging-System verfügen. Tags oder bedingte Attribute können mit digitalen Assets im Repository verknüpft werden, was bei der Veröffentlichung der Ausgabe basierend auf den ausgewählten Bedingungen hilft. Beispielsweise können Sie bedingte Attribute für Windows- und Mac-Inhalte erstellen. Anschließend fügen Sie diese Attribute den relevanten Inhalten in Ihren Themen hinzu. Zum Zeitpunkt der Veröffentlichung von Inhalten können Sie auswählen, ob Sie nur Windows- oder Mac-Inhalte veröffentlichen möchten.

Mit AEM Guides können Sie bedingte Attribute einfach mithilfe der entsprechenden DITA-Attribute erstellen und verknüpfen. Sie können bedingte Attribute auf globaler Ebene oder Ordnerebene definieren. Die global definierten Bedingungen sind für alle Projekte sichtbar, und ordnerspezifische Bedingungen sind nur in Projekten sichtbar, die innerhalb des angegebenen Ordners erstellt wurden. Inhaltsautoren können diese bedingten Attribute verwenden, um Inhalte in ihren DITA-Themen oder -Karten, die sie erstellen oder verwenden, mit Bedingungen zu versehen. Diese Bedingungen können dann vom Publisher verwendet werden, um bedingte Vorgaben zu erstellen. Mithilfe der bedingten Vorgaben kann der Publisher entscheiden, welche Bedingung in die veröffentlichte Ausgabe eingeschlossen und von ihr ausgeschlossen werden soll.

>[!NOTE]
>
> Sie können die bedingten Attribute in einem Ordnerprofil erstellen oder bearbeiten, auf das Sie Zugriff haben. Wenn Ihnen Ihr Systemadministrator keinen Zugriff auf ein Ordnerprofil gewährt hat, können Sie die bedingten Attribute im Ordnerprofil nicht erstellen oder bearbeiten.

Um bedingte Attribute zu definieren, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die **Ordnerprofile** und wählen Sie ein Ordnerprofil aus.

   >[!NOTE]
   >
   > Das globale Profil kann nicht bearbeitet werden.

1. Klicken Sie auf die Registerkarte **Bedingte Attribute** und dann auf **Bearbeiten**.

   Die Tabelle Bedingte Attribute wird angezeigt.

1. Klicken Sie auf **Hinzufügen**.

1. Geben Sie **Name**, **Value** und einen **Label** für das Attribut ein.

   Sie können ein Profil nur mit dem Attributnamen speichern. Ein Attribut kann jedoch nur verwendet werden, wenn für es ein Wert angegeben wurde. Wenn Sie sowohl - Wert als auch Beschriftung für ein Attribut angeben, zeigt der Web-Editor weiterhin nur den Wert des Attributs an. Der Titel wird dem Veröffentlichungsadministrator zum Zeitpunkt der Erstellung der bedingten Vorgabe angezeigt.

   Der folgende Screenshot zeigt die Definition für das Attribut `platform` mit dem Wert `unix` und der Kennzeichnung `Red Hat Linux`.

   ![](images/add-profile.png){width="800" align="left"}

1. Wenn Sie weitere Werte für dasselbe Attribut hinzufügen möchten, klicken Sie auf das Symbol **+** und geben Sie zusätzlichen Wert und eine Bezeichnung ein.

1. Wenn Sie weitere Attribute hinzufügen möchten, klicken Sie auf **Hinzufügen**.

1. Klicken Sie auf **Speichern**, um die Änderungen zu speichern.


Das `platform` wird im System gespeichert. Wenn ein Autor sich entscheidet, das `platform`-Attribut in einem DITA-Thema in einem Ordner zu verwenden, werden die Werte auf der Registerkarte Eigenschaften im Web-Editor angezeigt.

![](images/properties-tab.png){width="350" align="left"}

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
