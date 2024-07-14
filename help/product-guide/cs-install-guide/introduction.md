---
title: Informationen zu diesem Handbuch
description: Informationen zu diesem Handbuch
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 3%

---

# Informationen zu diesem Handbuch {#id175MC0P0S5Z}

Adobe Experience Manager Guides \(später als *AEM Guides*\) ist eine leistungsstarke, Cloud-basierte Inhaltsverwaltungslösung für Unternehmen mit Unternehmensqualität \(CCMS\). Sie ermöglicht native DITA-Unterstützung in Adobe Experience Manager und ermöglicht AEM die Bearbeitung der DITA-basierten Inhaltserstellung und -Bereitstellung. Sie ermöglicht es Autoren, Inhalte mithilfe des benutzerfreundlichen integrierten Web-Editors zu erstellen und in verschiedenen Ausgabeformaten zu veröffentlichen.

Dieses Handbuch enthält Anweisungen zum Herunterladen, Installieren und Konfigurieren von AEM Guides. In diesem Handbuch finden Sie detaillierte Anweisungen zum Einrichten von AEM Guides entsprechend Ihren Anforderungen an die Erstellung und Veröffentlichung im Unternehmen.

Dieses Handbuch richtet sich an folgende Zielgruppentypen:

- Administratoren, die AEM Guides installieren und verwalten.

- Herausgeber, die die Veröffentlichungsaufgabe ausführen, um Ausgabe in verschiedenen Formaten zu generieren.


## Inhaltsstruktur

Die Informationen in diesem Handbuch sind wie folgt organisiert:

- [Info zu diesem Handbuch](#id175MC0P0S5Z): Dieses Thema enthält eine Einführung in dieses Handbuch, die gewünschte Zielgruppe und die Organisation der Informationen in diesem Handbuch.

- [Herunterladen und Installieren](download-install.md#): Hier wird das Herunterladen, Installieren oder Aktualisieren von AEM Guides beschrieben.

- [Benutzerverwaltung und Sicherheit](user-admin-sec.md#): Hier wird das Kernkonzept der Benutzer und Authentifizierung in AEM und die von AEM Guides erstellten Standardbenutzergruppen beschrieben.

- [Verwenden Sie benutzerdefinierte DITA-OT- und DITA-Spezialisierung](dita-ot-specialization.md#): In diesem Thema wird erläutert, wie Sie benutzerdefinierte DITA-OT-Plug-ins konfigurieren und DITA-Spezialisierung verwenden.

- [Dokumentstatus konfigurieren](customize-doc-state.md#): In diesem Thema wird beschrieben, wie Sie benutzerdefinierte Status für Ihre DITA-Dokumente konfigurieren.

- [Vorhandenen Inhalt migrieren](migrate-content.md#): Hier wird beschrieben, wie Sie vorhandenen Inhalt in AEM Repository einbinden.

- [Dateinamen konfigurieren](conf-file-names.md#): In diesem Thema wird beschrieben, wie Sie Einstellungen konfigurieren, um Dateinamen automatisch zuzuweisen und einen Regex für gültige Dateinamenzeichen zu definieren.

- [Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md#): Hier wird beschrieben, wie Themen- und Zuordnungsvorlagen entsprechend Ihren Authoring-Anforderungen konfiguriert werden. Erfahren Sie mehr über das Tagging-System in AEM und wie Tags für die Verwendung mit AEM Guides konfiguriert werden.

- [Web-Editor anpassen](conf-web-editor.md#): In diesem Thema werden die verschiedenen Anpassungen erläutert, die Sie im Web-Editor vornehmen können, um seine Funktionalität zu verbessern.

- [Standardmäßig @navtitle-Attribut einschließen](auto-add-navtitle.md#): In diesem Thema wird erläutert, wie das Attribut `@navtitle` standardmäßig einer Referenzdatei in einer Zuordnung hinzugefügt wird.

- [Globale Profile oder Profile auf Ordnerebene konfigurieren](conf-folder-level.md#): In diesem Thema wird der Prozess zum Erstellen von Ordnerprofilen und zum Gewähren von Berechtigungen für bestimmte Benutzer erläutert.

- [Versionsverwaltung](version-management.md#): Hier wird beschrieben, wie Sie das automatische Auschecken von Dateien konfigurieren, die zur Bearbeitung im Web Editor geöffnet sind.

- [Einstellungen zur Ausgabenerstellung konfigurieren](conf-output-generation.md#): Hier werden die verschiedenen Konfigurationen beschrieben, die Sie zum Anpassen des standardmäßigen Prozesses zur Ausgabenerstellung vornehmen können.

- [Konfigurieren und Anpassen von Workflows](customize-workflows.md#): Hier werden verschiedene Konfigurationen beschrieben, um die in der AEM Guides bereitgestellten standardmäßigen Workflows anzupassen.

- [Inhalt übersetzen](translation.md#): Dieses Thema enthält Links zu den entsprechenden Hilfeartikeln in AEM Dokumentation, die Ihnen helfen, das Übersetzungs-Framework zu verstehen und zu konfigurieren. Erfahren Sie außerdem, wie Sie einen komponentenbasierten Übersetzungs-Workflow aktivieren.

- [Konfigurieren der Suche für die AEM Assets-Benutzeroberfläche](conf-dita-search.md#): Hier wird beschrieben, wie Sie die DITA-Inhaltssuche in der Assets-Benutzeroberfläche konfigurieren und Ihre benutzerdefinierten Attribute bei der Suche hinzufügen.


## Überblick über Adobe Experience Manager \(AEM\)

[Adobe Experience Manager \(AEM\)](https://business.adobe.com/de/products/experience-manager/adobe-experience-manager.html) ist eine umfassende Inhaltsverwaltungslösung zum Erstellen von Websites, mobilen Apps und Formularen. AEM hilft Ihnen bei der Verwaltung Ihrer Marketing-Inhalte und -Assets. AEM ist as a Cloud Service verfügbar. AEM as a Cloud Service unterstützt Sie dabei, Ihren Kunden personalisierte, inhaltsgesteuerte Erlebnisse bereitzustellen, indem die Leistungsfähigkeit des AEM Content Management Systems mit AEM Digital Asset Management kombiniert wird. Einige der wichtigsten Ressourcen, die Ihnen beim Einstieg in AEM as a Cloud Service helfen können, lauten wie folgt:

- [Überblick über Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=en)
- [Erste Schritte mit der Migration Journey zu AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=en)
- [Einstieg in Experience Manager as a Cloud Service starten](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=enhttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
- [Implementieren von Programmen für AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=de)
- [Bereitstellen in AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=de)
- [Assets as a Cloud Service Guide](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=de)

## Zusätzliche Ressourcen

Im Folgenden finden Sie eine Liste weiterer hilfreicher Ressourcen von AEM Guides, die auf der Seite [Lernen und Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) verfügbar sind:

- Benutzerhandbuch
- API-Referenzhandbuch
