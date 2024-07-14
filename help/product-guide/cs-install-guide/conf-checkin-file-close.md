---
title: Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Aufforderung zum Einchecken einer Datei beim Schließen konfigurieren
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

Wenn der Benutzer versucht, eine Datei zu schließen, die im Web Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei geöffnet ist, oder mit der Option **Schließen** im Menü &quot;Optionen&quot;wird ein Dialogfeld angezeigt, wenn die Datei nicht gespeicherte Daten oder eine nicht gespeicherte Version aufweist. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um eine Eingabeaufforderung zum Einchecken einer Datei beim Schließen zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolesch \( true/false\).<br> **Standardwert**: false |

Wenn diese Konfiguration aktiviert ist, ist im Dialogfeld standardmäßig das Kontrollkästchen **Datei entsperren** aktiviert.

Weitere Informationen finden Sie im Abschnitt *Szenarien schließen und speichern* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
