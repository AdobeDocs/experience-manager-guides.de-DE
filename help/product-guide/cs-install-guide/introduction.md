---
title: Über dieses Handbuch
description: Weitere Informationen zu diesem Handbuch
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 3%

---

# Über dieses Handbuch {#id175MC0P0S5Z}

Adobe Experience Manager Guides \(später als *AEM Guides*\ bezeichnet) ist eine leistungsstarke, Cloud-basierte, für Unternehmen geeignete Komponenten-Content-Management-Lösung \(CCMS\). Sie unterstützt native DITA-Unterstützung in Adobe Experience Manager und ermöglicht AEM die Verarbeitung der DITA-basierten Inhaltserstellung und -bereitstellung. Sie ermöglicht es Autoren, Inhalte mit dem benutzerfreundlichen integrierten Web-Editor zu erstellen und in verschiedenen Ausgabeformaten zu veröffentlichen.

Dieses Handbuch enthält die Anweisungen zum Herunterladen, Installieren und Konfigurieren von AEM Guides. In diesem Handbuch finden Sie detaillierte Anweisungen zum Einrichten von AEM Guides entsprechend den Authoring- und Publishing-Anforderungen Ihres Unternehmens.

Dieses Handbuch richtet sich an die folgende Art von Zielgruppen:

- Administratoren, die AEM Guides installieren und verwalten.

- Herausgeber, die die Veröffentlichungsaufgabe ausführen würden, um Ausgaben in verschiedenen Formaten zu generieren.


## Inhaltsstruktur

Die Informationen in diesem Handbuch sind wie folgt aufgebaut:

- [Über dieses Handbuch](#id175MC0P0S5Z): Dieses Thema bietet eine Einführung in dieses Handbuch, die vorgesehene Zielgruppe und wie die Informationen in diesem Handbuch organisiert sind.

- [Herunterladen und Installieren](download-install.md#): In diesem Thema wird beschrieben, wie Sie AEM Guides herunterladen, installieren oder aktualisieren.

- [Benutzerverwaltung und Sicherheit](user-admin-sec.md#): In diesem Thema werden das Kernkonzept der Benutzenden und die Authentifizierung in AEM sowie die von AEM Guides erstellten Standardbenutzergruppen beschrieben.

- [Verwenden benutzerdefinierter DITA-OT- und DITA-](dita-ot-specialization.md#): In diesem Thema wird beschrieben, wie Sie benutzerdefinierte DITA-OT-Plug-ins konfigurieren und die DITA-Spezialisierung verwenden.

- [Dokumentstatus konfigurieren](customize-doc-state.md#) In diesem Thema wird beschrieben, wie Sie benutzerdefinierte Status für Ihre DITA-Dokumente konfigurieren.

- [Migrieren vorhandener Inhalte](migrate-content.md#) In diesem Thema wird beschrieben, wie Sie Ihre vorhandenen Inhalte in das AEM-Repository integrieren.

- [Dateinamen konfigurieren](conf-file-names.md#) In diesem Thema wird erläutert, wie Sie eine Einstellung konfigurieren können, um Dateinamen automatisch zuzuweisen und einen Regex für gültige Dateinamenzeichen zu definieren.

- [Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md#) In diesem Thema wird beschrieben, wie Sie Themen- und Zuordnungsvorlagen entsprechend Ihren Authoring-Anforderungen konfigurieren. Erfahren Sie mehr über das Tagging-System in AEM und darüber, wie Sie Tags für die Verwendung mit AEM Guides konfigurieren.

- [Web-Editor anpassen](conf-web-editor.md#): In diesem Thema werden die verschiedenen Anpassungen erläutert, die Sie im Web-Editor vornehmen können, um dessen Funktionalität zu verbessern.

- [@navtitle-Attribut standardmäßig einbeziehen](auto-add-navtitle.md#) In diesem Thema wird erläutert, wie Sie das `@navtitle`-Attribut standardmäßig zu einer Referenzdatei in einer Zuordnung hinzufügen.

- [Konfigurieren von globalen Profilen oder Profilen auf Ordnerebene](conf-folder-level.md#) In diesem Thema wird der Prozess zum Erstellen von Ordnerprofilen und das Erteilen von Berechtigungen für bestimmte Benutzende erläutert.

- [Versionsverwaltung](version-management.md#) In diesem Thema wird beschrieben, wie Sie das automatische Auschecken von Dateien für Dateien konfigurieren, die im Web-Editor zur Bearbeitung geöffnet werden.

- [Einstellungen für die Ausgabenerstellung konfigurieren](conf-output-generation.md#) In diesem Thema werden die verschiedenen Konfigurationen beschrieben, die Sie vornehmen können, um den standardmäßigen Ausgabenerstellungsprozess anzupassen.

- [Konfigurieren und Anpassen von Workflows](customize-workflows.md#): In diesem Thema werden verschiedene Konfigurationen beschrieben, mit denen die in der AEM Guides bereitgestellten Standard-Workflows angepasst werden können.

- [Inhalte übersetzen](translation.md#): Dieses Thema enthält Links zu den entsprechenden Hilfeartikeln in der AEM-Dokumentation, die Ihnen dabei helfen, das Übersetzungs-Framework zu verstehen und zu konfigurieren. Erfahren Sie außerdem, wie Sie einen komponentenbasierten Übersetzungs-Workflow aktivieren.

- [Suche für AEM Assets-Benutzeroberfläche konfigurieren](conf-dita-search.md#) In diesem Thema wird beschrieben, wie Sie die DITA-Inhaltssuche in der Assets-Benutzeroberfläche konfigurieren und Ihre benutzerdefinierten Attribute bei der Suche hinzufügen.


## Überblick über Adobe Experience Manager \(AEM\)

[Adobe Experience Manager \(AEM\)](https://business.adobe.com/de/products/experience-manager/adobe-experience-manager.html) ist eine umfassende Content-Management-Lösung zum Erstellen von Websites, Mobile Apps und Formularen. AEM unterstützt Sie bei der Verwaltung Ihrer Marketing-Inhalte und -Assets. AEM ist as a Cloud Service verfügbar. AEM as a Cloud Service hilft Ihnen, Ihren Kunden personalisierte, inhaltsgesteuerte Erlebnisse bereitzustellen, indem es die Leistungsfähigkeit des AEM Content Management Systems mit AEM Digital Asset Management kombiniert.Zu den wichtigsten Ressourcen, die Ihnen bei den ersten Schritten und der Bereitstellung für AEM as a Cloud Service helfen können, gehören die folgenden:

- [Experience Manager as a Cloud Service - Überblick](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=de)
- [Erste Schritte mit der Migrations-Journey zu AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=de)
- [Starten Sie das Onboarding bei Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=dehttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
- [Implementieren von Programmen für AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=de)
- [Bereitstellen in AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=de)
- [Assets as a Cloud Service-Handbuch](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=de)

## Zusätzliche Ressourcen

Im Folgenden finden Sie eine Liste weiterer hilfreicher Ressourcen von AEM Guides, die auf der Seite [Lernen und Support](https://helpx.adobe.com/de/support/xml-documentation-for-experience-manager.html) verfügbar sind:

- Benutzerhandbuch
- API-Referenzhandbuch
