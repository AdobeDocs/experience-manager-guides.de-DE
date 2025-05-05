---
title: Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte
description: Erfahren Sie, wie Sie DITA-Themen oder -Zuordnungsdateien in derselben Registerkarte öffnen.
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte {#id223HI0P202H}

Wenn Sie in einigen Workflows auf einen Link eines Themas oder einer Zuordnungsdatei klicken, wird diese auf einer neuen Registerkarte geöffnet. Dies kann dazu führen, dass in Ihrem Browser viele Registerkarten geöffnet werden, was sich auf Ihre Produktivität auswirken kann. Sie können dieses Verhalten ändern, wenn Sie ein Thema oder eine Zuordnungsdatei in einer neuen Registerkarte öffnen und das Öffnen in der aktuellen Registerkarte erzwingen. Führen Sie dazu die folgenden Konfigurationsänderungen durch:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die **DITA-Thema/-Zuordnung auf derselben Registerkarte öffnen** aus.

1. Klicken Sie auf **Speichern**.


Diese Einstellung wirkt sich auf die folgenden Orte aus, von denen aus Sie auf das Thema oder die Zuordnungsdateien zugreifen können:

- DITA-Thema erstellen \(am Ende des Workflows, wenn Sie auf die Schaltfläche **Thema öffnen** klicken)

- DITA-Map erstellen \(Klicken Sie am Ende des Workflows auf die Schaltfläche **Zuordnung öffnen**\)

- Registerkarte „Themen“ in der DITA-Zuordnungskonsole

- Registerkarte „Baselines“ in der DITA-Zuordnungskonsole

- Registerkarte „Berichte“ in der DITA-Zuordnungskonsole


**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
