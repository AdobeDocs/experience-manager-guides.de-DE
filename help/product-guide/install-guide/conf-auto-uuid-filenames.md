---
title: Konfigurieren automatischer Dateinamen basierend auf UUID
description: Erfahren Sie, wie Sie automatische Dateinamen basierend auf der UUID konfigurieren
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Konfigurieren automatischer Dateinamen basierend auf UUID {#id205QG070D5Z}

Wenn ein Thema oder eine Zuordnungsdatei erstellt wird, haben Autoren standardmäßig die Möglichkeit, auch den Dateinamen anzugeben. Autoren können die Dateinamen gemäß ihren Anforderungen zuweisen. Dies kann jedoch zu Inkonsistenzen führen, und in einem großen Dokumentationssystem kann ein breites Spektrum von Dateinamen angezeigt werden. Als Admin können Sie Ihre Autoren daran hindern, den Dateien, die sie in Ihrem System erstellen, Dateinamen zuzuweisen. Für jede neue Themen- oder Zuordnungsdatei können Sie UUID-basierte Dateinamen automatisch zuweisen.

Führen Sie die folgenden Schritte aus, um den UUID-basierten Dateinamen automatisch für alle neuen Dateien zuzuweisen, die im System erstellt wurden:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.xmeditor.config.XmlEditorConfig* und klicken Sie darauf.

1. Wählen Sie die **UUID-basierte Systemdateinamen verwenden**.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Standardmäßig ist diese Option deaktiviert. Wenn diese Option aktiviert ist, wird den Autoren beim Erstellen eines neuen Themas oder einer Zuordnungsdatei die Option zum Angeben des Dateinamens nicht angezeigt. Über die Assets-Benutzeroberfläche und den Web-Editor kann eine neue Themen- oder Zuordnungsdatei erstellt werden.

**Übergeordnetes Thema:**&#x200B;[ Dateinamen konfigurieren](conf-file-names.md)
