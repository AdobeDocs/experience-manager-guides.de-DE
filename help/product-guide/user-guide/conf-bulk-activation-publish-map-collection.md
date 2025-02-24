---
title: Ausgabe aktivieren
description: Aktivieren der Ausgabe von DITA-Karten in AEM Guides. Erfahren Sie, wie Sie Ihre Inhalte auf der Veröffentlichungsinstanz aktivieren.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
source-git-commit: a00674a98e4ba87dbc5ddac3412cedca15a205bd
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 1%

---

# Ausgabe aktivieren {#id214GGF00V5U}

Nachdem Sie eine Zuordnungssammlung für die Massenaktivierung erstellt haben, besteht der nächste Schritt darin, Ihre Inhalte in der Veröffentlichungsinstanz zu aktivieren. Gehen Sie wie folgt vor, um Ihren Inhalt zu aktivieren:

1. Klicken Sie oben auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.

1. Wählen Sie im **Tools**-Bedienfeld **Guides** aus.

1. Wählen Sie die **Dashboard für Massenveröffentlichung** aus.

   Das Dashboard für die Massenveröffentlichung wird mit einer Liste von Zuordnungssammlungen für die Massenaktivierung angezeigt. Sie können auf dieses Dashboard auch über das linke Bedienfeld der Startseite von [Adobe Experience Manager Guides zugreifen](intro-home-page.md).

1. Wählen Sie die Sammlung aus, die Sie veröffentlichen möchten, und wählen Sie **Öffnen**.

   ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1. \(*Optional*\) Wenden Sie die erforderlichen Filter in der linken Leiste an, um die Zuordnung anhand ihres geänderten \(Status\), ihrer Ausgabevorgabe oder ihrer Sprache zu filtern.

   >[!NOTE]
   >
   >Generieren Sie die Ausgabe für die Zuordnung mithilfe der Ausgabevorgabe, bevor Sie sie in der Zuordnungssammlung aktivieren.


Sehen Sie sich die verschiedenen Möglichkeiten zur Aktivierung Ihrer Sammlung basierend auf Ihrer Einrichtung an.

<details>
<summary> Cloud Services </summary>

![bulk-collection-publish auf Cloud Service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

Sie können die Ausgabe für die Instanzen **Vorschau** oder **Veröffentlichen** aktivieren.

**Vorschau**

* Um die Ausgabe ausgewählter Zuordnungen zu aktivieren, wählen Sie die vorgenerierte Zuordnungsausgabe aus und klicken Sie auf **Veröffentlichen in** > **Vorschau**.
* Um die Ausgabe aller DITA-Zuordnungen mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Spalte **Map** und wählen Sie dann **Veröffentlichen in** > **Veröffentlichen**.


**Veröffentlichen**

* Um die Ausgabe ausgewählter Zuordnungen zu aktivieren, wählen Sie die vorgenerierte Zuordnungsausgabe aus und klicken Sie auf **Veröffentlichen in** > **Veröffentlichen**.

* Um die Ausgabe aller DITA-Zuordnungen mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Zuordnung (Spalte) und wählen Sie dann **Veröffentlichen in** > **Veröffentlichen**.


>[!NOTE]
> 
> Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.

Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte Prüfverlauf aktualisiert, und die zuletzt aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

</details>

<details>    
<summary>  On-Premise Software </summary>


Führen Sie einen der folgenden Schritte aus:

* Um die Ausgabe ausgewählter Zuordnungen zu aktivieren, wählen Sie die vorgenerierte Zuordnungsausgabe aus und klicken Sie auf **Quick Publish**.
* Um die Ausgabe aller DITA-Zuordnungen mit den konfigurierten Vorgaben zu aktivieren, aktivieren Sie das Kontrollkästchen neben der Zuordnung (Spalte) und wählen Sie dann **Quick Publish.**
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}

  >[!NOTE]
  > 
  >Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.


Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte Prüfverlauf aktualisiert, und die zuletzt aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
