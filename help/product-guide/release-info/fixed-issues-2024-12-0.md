---
title: Versionshinweise zu | Es wurden Probleme in der Version 2024.12.0 von Adobe Experience Manager Guides behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.12.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 04a57e1a-6e74-46f6-acde-5045d3dcacdc
source-git-commit: dd404c42863f0b4a5f31b54f770c0bf296d68ab9
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 1%

---

# Es wurden Probleme in der Version 2024.12.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.12.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.12.0](./upgrade-instructions-2024-12-0.md).

## Authoring

- Die Erstellung einer DITA-Zuordnung für eine UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames` in `XMLEditorConfig` aktiviert ist. 21201)
- Beim Schließen einer Datei werden im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügte Kommentare und Beschriftungen nicht mit der neuen Version im Versionsverlauf gespeichert. Dies gilt speziell für einen Anwendungsfall, bei dem **Beim Schließen nach Einchecken fragen** oder **Beim Schließen nach neuer Version** fragen) in `XMLEditorConfig` aktiviert ist. 20065)
- Der als &quot;**&quot; markierte Dokumentstatus** vor dem Speichern einer neuen Version wieder auf **Entwurf** zurück, was dazu führt, dass der **Fertig**-Status in keiner Dokumentversion bestehen bleibt. 20006)
- Eine PDF-Datei kann nicht als Bildreferenz zu einem Thema im Web-Editor hinzugefügt werden. 21206)
- Wenn Sie in der Assets-Benutzeroberfläche eine DITA-Datei auswählen, wird die Option **Auf FrameMaker öffnen** angezeigt, auch wenn sie in der Konfiguration deaktiviert ist. 20082)

## Veröffentlichung

- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. 21840)


## Verwaltung

- Ressourcenlecks treten aufgrund von „Unclosed ResourceResolver **-Fehlern** Protokollen auf. 18488)
- Beim Erstellen einer neuen oder doppelten Baseline werden Kennzeichnungen in zufälliger Reihenfolge angezeigt. 19307)


## Grundlinie

- Beim Bearbeiten und anschließenden Speichern einer Baseline in einer Cloud-Einrichtung tritt nach einer Minute ein Timeout auf, wenn die Baseline eine große Anzahl von Themen oder Karten hat. 19558)

## Übersetzung

- Die Zuordnungsübersetzung mithilfe der Grundlinie wird langsam und schlägt schließlich fehl, die Liste aller zugehörigen Themen und Zuordnungsdateien zu laden. 19733)

## Bekannte Probleme mit Workaround

Adobe hat die folgenden bekannten Probleme in der Version 2024.12.0 von Adobe Experience Manager Guides as a Cloud Service identifiziert.

**Die Projekterstellung schlägt während der Verarbeitung der Inhaltsübersetzung fehl**

Beim Senden von Inhalten für die Übersetzung schlägt die Projekterstellung mit den folgenden Protokollfehlern fehl:

`com.adobe.cq.wcm.translation.impl.TranslationPrepareResource` bei der Verarbeitung des Übersetzungsprojekts

`com.adobe.cq.projects.api.ProjectException`: Das Projekt kann nicht erstellt werden

Ursache: `org.apache.jackrabbit.oak.api.CommitFailedException`: `OakAccess0000`: Zugriff verweigert


**Problemumgehung**: Führen Sie zur Behebung dieses Problems die folgenden Problemumgehungsschritte aus:

1. Fügen Sie eine repoinit-Datei hinzu. Falls die Datei nicht vorhanden ist, erstellen Sie die Datei, indem Sie die [Erstellungsschritte für die repoinit-Beispielkonfiguration](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-cloud-questions/repoinit-configuration-for-property-set-on-aem-as-cloud-service/m-p/438854?profile.language=de) ausführen.
2. Fügen Sie die folgende Zeile in der Datei hinzu und stellen Sie den Code bereit:

   ```
   { "scripts": [ "set principal ACL for translation-job-service\n allow jcr:all on /home/users/system/cq:services/internal/translation\nend" ] }
   ```

3. Testen Sie die Übersetzung nach der Bereitstellung.

