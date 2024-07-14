---
title: Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Aufforderung zum Speichern als neue Version beim Schließen konfigurieren
exl-id: 9029b671-8ff8-45eb-b27e-ab89bd09e7ed
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren {#id222HBI00XXA}

Wenn der Benutzer versucht, eine Datei zu schließen, die im Web Editor mithilfe der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü &quot;Optionen&quot;geöffnet ist, wird ein Dialogfeld angezeigt, wenn die Datei nicht gespeicherte Daten oder eine nicht gespeicherte Version aufweist. Der Benutzer wird aufgefordert, die Datei als neue Version zu speichern, wenn die Version nicht gespeichert wird.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um eine Eingabeaufforderung zum Speichern beim Schließen als neue Version zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolesch \( true/false\). <br>  **Standardwert**: true |

Wenn diese Konfiguration aktiviert ist, ist das Kontrollkästchen **Als neue Version speichern** im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie im Abschnitt *Szenarien schließen und speichern* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
