---
title: Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren
description: Erfahren Sie, wie Sie eine Eingabeaufforderung konfigurieren, um beim Schließen eine Datei einzuchecken
exl-id: 5b09ec46-aea4-4a3f-8bab-42414e31e37d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren {#id222HC040PE8}

Wenn der/die Benutzende versucht, eine Datei zu schließen, die im Web-Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü Optionen geöffnet wurde, wird ein Dialogfeld angezeigt, wenn die Datei ungespeicherte Daten oder eine ungespeicherte Version enthält. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um eine Eingabeaufforderung zum Einchecken einer Datei beim Schließen zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolescher Wert \( true/false\).<br> **Standardwert**: false |

Wenn diese Konfiguration aktiviert ist **ist das Kontrollkästchen** Datei entsperren“ im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie *Abschnitt „Schließen und Speichern von Dateien* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
