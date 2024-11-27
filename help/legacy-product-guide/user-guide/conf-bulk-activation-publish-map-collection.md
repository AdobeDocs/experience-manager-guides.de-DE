---
title: Ausgabe aktivieren
description: Aktivieren Sie die Ausgabe von DITA-Maps in AEM Guides. Erfahren Sie, wie Sie Ihren Inhalt in der Veröffentlichungsinstanz aktivieren.
feature: Publishing, Bulk Activation
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---

# Ausgabe aktivieren {#id214GGF00V5U}

Nachdem Sie eine Zuordnungssammlung für die Massenaktivierung erstellt haben, besteht der nächste Schritt darin, Ihren Inhalt in der Veröffentlichungsinstanz zu aktivieren. Führen Sie die folgenden Schritte aus, um Ihren Inhalt zu aktivieren:

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Klicken Sie auf die Kachel **Publish-Dashboard-Stapel** .

   Eine Liste mit Massenaktivierungskarten-Sammlungen wird angezeigt.

1. Wählen Sie die Sammlung aus, die Sie veröffentlichen möchten, und klicken Sie auf **Öffnen**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Optional*\) Wenden Sie die erforderlichen Filter aus der linken Leiste an, um die Zuordnung anhand der geänderten \(Status\), Ausgabevorgabe oder Sprache zu filtern.

   >[!NOTE]
   >
   >Generieren Sie die Ausgabe für die Zuordnung mithilfe der Ausgabevorgabe, bevor Sie sie in der Zuordnungssammlung aktivieren.


Sehen Sie sich die verschiedenen Möglichkeiten an, um Ihre Sammlung basierend auf Ihrer Einrichtung zu aktivieren.

<details>
<summary> Cloud Services </summary>

![bulk-collection-publish on cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Sie können die Ausgabe für die Instanzen **Vorschau** oder **Publish** aktivieren.

**Vorschau**

* Um die Ausgabe der ausgewählten Maps zu aktivieren, wählen Sie die vorgenerierte Mapping-Ausgabe aus und wählen Sie **Publish to** > **Vorschau**.
* Um die Ausgabe aller DITA-Maps mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Spalte **Map** und wählen Sie dann **Publish to** > **Publish** aus.


**Veröffentlichen**

* Um die Ausgabe der ausgewählten Maps zu aktivieren, wählen Sie die vorgenerierte Mapping-Ausgabe aus und wählen Sie **Publish to** > **Publish**.

* Um die Ausgabe aller DITA-Maps mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Karte (Spalte) und wählen Sie dann **Publish zu** > **Publish** aus.


>[!NOTE]
> 
> Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.

Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte &quot;Prüfverlauf&quot;aktualisiert und die neueste aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

</details>

<details>    
<summary>  On-Premise Software </summary>


Führen Sie einen der folgenden Schritte aus:

* Um die Ausgabe der ausgewählten Karten zu aktivieren, wählen Sie die vorgenerierte Zuordnungsausgabe aus und wählen Sie **Quick Publish** aus.
* Um die Ausgabe aller DITA-Maps mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Karte (Spalte) und wählen Sie dann **Quick Publish** aus.
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.


Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte &quot;Prüfverlauf&quot;aktualisiert und die neueste aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
