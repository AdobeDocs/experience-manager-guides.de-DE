---
title: Ausgabe aktivieren
description: Aktivieren der Ausgabe von DITA-Karten in AEM Guides. Erfahren Sie, wie Sie Ihre Inhalte auf der Veröffentlichungsinstanz aktivieren.
feature: Publishing, Bulk Activation
role: User
exl-id: de1fd057-60c6-4b1a-9e55-f32969eb0079
source-git-commit: 86fb9cc382689beb493847cb506c788199a2d3f4
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---

# Ausgabe aktivieren {#id214GGF00V5U}

Nachdem Sie eine Zuordnungssammlung für die Massenaktivierung erstellt haben, besteht der nächste Schritt darin, Ihre Inhalte in der Veröffentlichungsinstanz zu aktivieren. Gehen Sie wie folgt vor, um Ihren Inhalt zu aktivieren:

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Klicken Sie auf die Kachel **Publish-Dashboard** Massenverarbeitung“.

   Eine Liste der Massenaktivierungszuordnungssammlungen wird angezeigt.

1. Wählen Sie die zu veröffentlichende Sammlung aus und klicken Sie auf **Öffnen**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Optional*\) Wenden Sie die erforderlichen Filter in der linken Leiste an, um die Zuordnung anhand ihres geänderten \(Status\), ihrer Ausgabevorgabe oder ihrer Sprache zu filtern.

   >[!NOTE]
   >
   >Generieren Sie die Ausgabe für die Zuordnung mithilfe der Ausgabevorgabe, bevor Sie sie in der Zuordnungssammlung aktivieren.


Sehen Sie sich die verschiedenen Möglichkeiten zur Aktivierung Ihrer Sammlung basierend auf Ihrer Einrichtung an.

<details>
<summary> Cloud Services </summary>

![bulk-collection-publish auf Cloud Service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Sie können die Ausgabe für die **Vorschau** oder **Publish-** aktivieren.

**Vorschau**

* Um die Ausgabe ausgewählter Zuordnungen zu aktivieren, wählen Sie die vorgenerierte Zuordnungsausgabe aus und wählen Sie **Publish bis** > **Vorschau**.
* Um die Ausgabe aller DITA-Zuordnungen mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Spalte **Map** und wählen Sie dann **Publish nach** > **Publish**.


**Veröffentlichen**

* Um die Ausgabe ausgewählter Zuordnungen zu aktivieren, wählen Sie die vorgenerierte Zuordnungsausgabe aus und wählen Sie **Publish zu** > **Publish**.

* Um die Ausgabe aller DITA-Zuordnungen mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Zuordnung (Spalte) und wählen Sie dann **Publish zu** > **Publish**.


>[!NOTE]
> 
> Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.

Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte Prüfverlauf aktualisiert, und die zuletzt aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

</details>

<details>    
<summary>  On-Premise Software </summary>


Führen Sie einen der folgenden Schritte aus:

* Um die Ausgabe ausgewählter Karten zu aktivieren, wählen Sie die vorgenerierte Kartenausgabe aus und klicken Sie auf **Quick Publish**.
* Um die Ausgabe aller DITA-Zuordnungen mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Zuordnung (Spalte) und wählen Sie dann **Quick Publish.**
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.


Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte Prüfverlauf aktualisiert, und die zuletzt aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
