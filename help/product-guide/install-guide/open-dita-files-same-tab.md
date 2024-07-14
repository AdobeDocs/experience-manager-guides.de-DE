---
title: DITA-Themen- oder Zuordnungsdateien auf derselben Registerkarte öffnen
description: Erfahren Sie, wie Sie DITA-Themen oder -Zuordnungsdateien auf derselben Registerkarte öffnen
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# DITA-Themen- oder Zuordnungsdateien auf derselben Registerkarte öffnen {#id223HI0P202H}

Wenn Sie in einigen Workflows auf einen Link eines Themas oder einer Zuordnungsdatei klicken, wird dieser in einer neuen Registerkarte geöffnet. Dies kann dazu führen, dass in Ihrem Browser viele Tabs geöffnet werden, was sich auf Ihre Produktivität auswirken könnte. Sie können dieses Verhalten beim Öffnen einer Themen- oder Zuordnungsdatei in einer neuen Registerkarte ändern und das Öffnen auf der aktuellen Registerkarte erzwingen. Führen Sie dazu die folgenden Konfigurationsänderungen durch:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **DITA-Thema/Karte auf derselben Registerkarte öffnen** aus.

1. Klicken Sie auf **Speichern**.


Diese Einstellung wirkt sich auf die folgenden Stellen aus, an denen Sie auf die Themen- oder Zuordnungsdateien zugreifen können:

- DITA-Thema erstellen \(am Ende des Workflows, wenn Sie auf die Schaltfläche **Thema öffnen** klicken\)

- DITA-Map erstellen \(am Ende des Workflows, wenn Sie auf die Schaltfläche **Map öffnen** klicken\)

- Registerkarte &quot;Themen&quot;in der DITA-Map-Konsole

- Registerkarte &quot;Grundlinien&quot;in der DITA-Map-Konsole

- Registerkarte &quot;Berichte&quot;in der DITA-Map-Konsole


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
