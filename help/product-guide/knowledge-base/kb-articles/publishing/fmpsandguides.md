---
title: Veröffentlichen mit FrameMaker Publishing Server (FMPS) in AEM Guides
description: Veröffentlichen mit FMPS unter Verwendung von AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Veröffentlichen mit FrameMaker Publishing Server (FMPS) in AEM Guides

Die Integration von AEM Guides mit FrameMaker Publishing Server könnte Ihre Lösung sein, wenn Sie qualitativ hochwertige automatisierte Veröffentlichungen suchen.\
Dieser Artikel hilft Ihnen beim Einrichten und Ausführen von FMPS mit AEM Guides.

## Kompatibilität von FMPS mit AEM Guides

- Kompatibilität mit AEM Guides 4.1: [4.1-Kompatibilitätsmatrix](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=de/#compatibility-matrix)
- Kompatibilität mit AEM Guides 4.0: [4.0-Kompatibilitätsmatrix](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Neueste Version: [Aktuelle Versionsinformationen](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=de)

## Installation

Siehe Folgendes für die Installation und Konfiguration von AEM Guides und FMPS

### AEM Guides

Installation und Konfiguration siehe: [4.1 Installation und Konfigurationen](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Für die FMPS-Installation können Sie den angegebenen [YouTube-Link](https://www.youtube.com/watch?v=2deelyM5VA8&t) oder [FMPS-Installation und -Konfiguration](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&rhtocid=_2)

## Erforderliche Konfigurationen

FrameMaker Publishing Server (FMPS) kann zum Generieren Ihres DITA-Inhalts verwendet werden. FMPS unterstützt eine Vielzahl von Ausgabeformaten. Ändern Sie die folgenden Eigenschaften des „com.adobe.fmdita.config.ConfigManager-Bundles“ in der Web-Konsole, um AEM Guides für die Verwendung von FMPS zu konfigurieren.

Wechseln Sie zum Öffnen der Web-Konsole zur URL Zugriff http://\&lt;Server-Name>:\&lt;Port\>/system/console/configMgr.

**Konfigurationseigenschaften und ihre Beschreibung** [4.1 Installation und Konfiguration](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test wird ausgeführt:

Mithilfe von FMPS können Sie **PDF, Responsive HTML5** und **Epub** automatisch für Ihre DITA- und FM-Assets veröffentlichen.

Wählen Sie im Menü &quot;PDF generieren mit“ die Option &quot;FrameMaker Publishing Server&quot;.

Der Benutzer kann die Einstellungen „File(.sts)“ und „ditaval“ angeben. Die Filterung erfolgt mithilfe von ditaval auf der Grundlage der von Ihnen angegebenen Bedingungen.

- **Einstellungsdatei**: Eine FrameMaker-/FMPS-Einstellungsdatei für Veröffentlichungseinstellungen, die alle Einstellungen enthält, die FMPS beim Veröffentlichen berücksichtigen soll. Beispielsweise das Erstellen einer Ausgabe mit einer benutzerdefinierten Vorlage, das Erstellen von Markierungen und Anschnitten (PDF) und das Erstellen von PDF mit Inhaltsverzeichnis.
- **FMPS-Voreinstellung** Es handelt sich um eine vordefinierte Kombination aus ditaval und Einstellungsdatei. Anstatt separate ditaval- und settings-Dateien bereitzustellen, kann der Benutzer eine FMPS-Voreinstellung vorab erstellen, die für Veröffentlichungsanforderungen wiederverwendet werden kann.

**Hinweis:** Die Standardsystemeinstellung wird von FMPS zur Veröffentlichung verwendet, wenn Sie keine der Einstellungen oder die FMPS-Vorgabe auswählen.

Es ist ein Konflikt, wenn Sie die FMPS-Vorgabe auswählen und auch benutzerdefinierte Einstellungen oder eine ditaval-Datei aus AEM bereitgestellt haben. In diesem Fall hat die FMPS-Voreinstellung Vorrang vor den benutzerdefinierten Einstellungen oder der ditaval-Datei.

### Grundlegende Veröffentlichung mithilfe von FMPS:

Sie können Ihre bereits erstellten Baselines mit FMPS2020.0.2 oder einer höheren Version veröffentlichen.

**Beispiel-FMPS-Einstellungsdatei (.sts-Datei) für die ersten Schritte:** [Beispiel-FMPS-Einstellungsdatei](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (diese Datei entpacken)

## Häufig gestellte Fragen und Fehlerbehebung:

- ### Die FMPS-Veröffentlichung schlägt mit „Timeout-Ausnahme“ fehl

>Überprüfen und erhöhen Sie den Wert von „FMPS-Zeitüberschreitung“ (Sekunden) in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager“

- ### FMPS-Vorgabe kann nicht im Dropdown-Menü abgerufen werden

>Stellen Sie sicher, dass eine vordefinierte FMPS-Voreinstellung auf dem Server erstellt wurde und dass Ihre Verbindungseinstellungen korrekt sind.

- ### Beim Veröffentlichen erhalte ich leere PDFs

>Wenn Sie UUID verwenden, stellen Sie sicher, dass Sie „UUID-basierten Verweis verwenden“ in den FrameMaker-Bearbeitungsvoreinstellungen und umgekehrt für AEM-Handbücher ohne UUID aktiviert haben.

- ### Meine Einstellungen/Werte werden in der endgültigen veröffentlichten Ausgabe nicht angewendet

>Stellen Sie sicher, dass Sie nicht gleichzeitig die FMPS-Voreinstellung und die Einstell-/Wähldatei wählen. Verwenden Sie FrameMaker, um die Ausgabe manuell zu überprüfen.

- ### Die Baseline wird nicht aus FMPS veröffentlicht

>FMPS2020.0.2 oder neuere Versionen sind mit der grundlegenden Veröffentlichung kompatibel.
>Vergewissern Sie sich, dass Ihre Baseline ordnungsgemäß erstellt wurde. Um dies zu überprüfen, gehen Sie zum Karten-Dashboard > Themen > Herunterladen  Ordnen Sie Baseline zu und wählen Sie sie aus.

- ### Veröffentlichungsaufgaben aus FMPS dauern länger als andere Engines

>Bei der Veröffentlichung aus FMPS beträgt die ideale feste Header-Zeit etwa 3-4 Minuten. Wenn Sie glauben, dass dies länger ist, wenden Sie sich an Ihren FMPS-Administrator oder den Adobe-Support.

## Weitere Ressourcen:

[FMPS: Lernen und Support](https://helpx.adobe.com/de/support/framemaker-publishing-server.html)

[AEM Guides: Lernen und Support](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker- und FMPS-Community](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&sort=latest_replies&lang=all&tabid=all)

[AEM Guides-Community](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation?profile.language=de)
