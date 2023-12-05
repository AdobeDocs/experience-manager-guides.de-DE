---
title: Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Aufforderung zum Einchecken einer Datei beim Schließen konfigurieren
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren {#id222HC040PE8}

Wenn der Benutzer versucht, eine Datei zu schließen, die im Web-Editor mit dem **Schließen** auf der Registerkarte der Datei oder **Schließen** im Menü Optionen wird ein Dialogfeld angezeigt, wenn die Datei nicht gespeicherte Daten oder eine nicht gespeicherte Version aufweist. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um eine Eingabeaufforderung zum Einchecken einer Datei beim Schließen zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolesch \( true/false\).<br> **Standardwert**: false |

Wenn diese Konfiguration aktiviert ist, wird die **Datei entsperren** ist im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie unter *Szenarien zum Schließen und Speichern von Dateien* im as a Cloud Service Handbuch Verwenden von Adobe Experience Manager-Handbüchern beschrieben.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
