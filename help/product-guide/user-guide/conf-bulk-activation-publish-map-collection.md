---
title: Ausgabe aktivieren
description: Aktivieren der Ausgabe von DITA-Karten in AEM Guides. Erfahren Sie, wie Sie Ihre Inhalte auf der Veröffentlichungsinstanz aktivieren.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
TQID: https://experienceleague.adobe.com/ujkifru-aKa2oYvrE8EKUEE3Sai8NqQ9lx9BA2ZUw9U
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 469
ht-degree: 1%

---

# Ausgabe aktivieren {#id214GGF00V5U}

Nachdem Sie eine Zuordnungssammlung für die Massenaktivierung erstellt haben, besteht der nächste Schritt darin, Ihre Inhalte in der Veröffentlichungsinstanz zu aktivieren. Gehen Sie wie folgt vor, um Ihren Inhalt zu aktivieren:

1. Klicken Sie oben auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.

1. Wählen Sie im **Tools**-Bedienfeld **Guides** aus.

1. Wählen Sie die **Dashboard für Massenveröffentlichung** aus.

   Das Dashboard für die Massenveröffentlichung wird mit einer Liste von Zuordnungssammlungen für die Massenaktivierung angezeigt. Sie können auf dieses Dashboard auch über das linke Bedienfeld der Startseite von [Adobe Experience Manager Guides zugreifen](intro-home-page.md).

1. Wählen Sie die Sammlung aus, die Sie veröffentlichen möchten, und wählen Sie **Öffnen**.

   ![](images/bulk-activation-collection-open.png)

1. \(*Optional*\) Wenden Sie die erforderlichen Filter in der linken Leiste an, um die Zuordnung anhand ihres geänderten \(Status\), ihrer Ausgabevorgabe oder ihrer Sprache zu filtern.

   >[!NOTE]
   >
   >Generieren Sie die Ausgabe für die Zuordnung mithilfe der Ausgabevorgabe, bevor Sie sie in der Zuordnungssammlung aktivieren.


Sehen Sie sich die verschiedenen Möglichkeiten zur Aktivierung Ihrer Sammlung basierend auf Ihrer Einrichtung an.

<details>
<summary> Cloud Services </summary>

![bulk-collection-publish auf Cloud Service](images/bulk-activation-collection-quick-publish-CS.png){width="650"}

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
  ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650"}

  >[!NOTE]
  > 
  >Das Kontrollkästchen für eine Zuordnungsausgabe ist nur aktiviert, wenn Sie die Ausgabe für eine Zuordnung generiert haben.


Eine Erfolgsmeldung wird angezeigt, wenn die Zuordnungsausgabe zur Veröffentlichung in die Warteschlange gestellt wird.

Sobald die Ausgabe für die ausgewählten Zuordnungsdateien aktiviert wurde, wird die Registerkarte Prüfverlauf aktualisiert, und die zuletzt aktivierte Ausgabe wird oben angezeigt. Die Spalte **Veröffentlicht** wird mit dem Veröffentlichungsdatum und der Veröffentlichungszeit aktualisiert.

**Übergeordnetes Thema: **[Massenaktivierung veröffentlichter Inhalte](conf-bulk-activation.md)
