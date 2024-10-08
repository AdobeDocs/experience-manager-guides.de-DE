---
title: AEM Guides-Versionen
description: Neueste AEM Guides-Versionen und erforderliche AEM-Versionen
exl-id: 780697a9-bdc6-40c2-b258-64639fe30f88
feature: Release Notes
role: Leader
source-git-commit: ba522b673b359607499288755cac87dbfa24e3cf
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# [!DNL AEM Guides] Versionen

[!DNL Adobe Experience Manager Guides] ist eine Anwendung, die auf AEM bereitgestellt wird. Es handelt sich dabei um eine leistungsstarke, unternehmenseigene Content-Management-Lösung (CCMS), die die native DITA-Unterstützung in Adobe Experience Manager ermöglicht und es AEM ermöglicht, die DITA-basierte Inhaltserstellung und -bereitstellung zu handhaben.

AEM Guides-Pakete sind in zwei Varianten verfügbar: UUID-Build und Nicht-UUID-Builds.

## UUID- und Nicht-UUID-Builds

Die wichtigsten Unterschiede zwischen den UUID- und Nicht-UUID-Builds sind:

|  | Nicht-UUID-Build | UUID-Build |
|---|---|---|
| **Asset-Identifizierung** | Alle Assets werden mithilfe des Pfads des Assets im Repository identifiziert. | Alle Assets werden anhand ihrer UUID (eindeutige ID, die vom System beim ersten Hochladen des Assets generiert wurde) identifiziert. |
| **Referenzerstellung** | Alle Inhaltsverweise werden basierend auf ihren Pfaden erstellt. | Alle Inhaltsreferenzen werden basierend auf ihrer UUID erstellt. |

### Vorteile des UUID-Builds

* Die UUID-Installation ist leistungsfähiger:
   * Verweise sind pfadunabhängig: Das Referenzverwaltungssystem erkennt die Verknüpfungen, da die Verweise auf der Grundlage von UUIDs und nicht der Pfade erstellt werden.
   * Verschieben/Aktualisieren-Vorgänge sind effizient: Die UUIDs bleiben gleich, auch wenn die Assets in einen anderen Pfad im Repository verschoben werden. Daher ist keine Verarbeitung erforderlich, um die Verweise zwischen den Assets bei Verschieben/Aktualisierung zu patchen.
* Der UUID-Build ist zukunftsorientiert, da wir dieses Framework auch für die Cloud-Einrichtung von AEM Guides verwenden.


### Wählen Sie zwischen den beiden Builds

* Wenn Sie ein neuer Kunde sind, empfehlen wir die Verwendung des UUID-Builds.
* Wenn Sie bereits Kunde sind, können Sie zum UUID-Build wechseln, da die Migration vom Build Nicht-UUID zu UUID jetzt möglich ist. Weitere Informationen finden Sie im Abschnitt *Migration von Nicht-UUID-Inhalten zu UUID* im Abschnitt **Installieren und Konfigurieren von Adobe Experience Manager Guides** .

>[!NOTE]
>
>* Kunden müssen zum Zeitpunkt der ersten Einrichtung zwischen dem UUID- und dem Nicht-UUID-Modus entscheiden (falls Sie Hilfe benötigen, wenden Sie sich an den Customer Success Manager, um Ihnen zu helfen, die Entscheidung basierend auf Ihrem Anwendungsfall zu treffen).
>* Beim Upgrade von einer Version von AEM Guides auf eine neuere Version müssen Kunden sicherstellen, dass sie denselben Modus (UUID/Nicht-UUID) auswählen, der dem vorhandenen Modus entspricht. Ein Nicht-UUID-Build sollte nicht direkt auf einen UUID-Build aktualisiert werden. Für den Wechsel vom Nicht-UUID-Build zum UUID-Build ist eine Inhaltsmigration erforderlich.

**Builds aktualisieren**

Wenn Sie von einer älteren Version auf eine neuere Version von [!DNL AEM Guides] aktualisieren, müssen Sie möglicherweise Migrationsskripte ausführen. Aktualisierungsanweisungen finden Sie in den Versionshinweisen und der versionsspezifischen Dokumentation .

Nicht alle Aktualisierungspfade werden direkt unterstützt. Beispielsweise ist ein direktes Upgrade auf Version 4.0 nur ab Version 3.8 möglich.
Wenn Sie eine Version vor 3.8 verwenden, finden Sie in der versionsspezifischen Dokumentation die Upgrade-Anweisungen für [Archiv mit Hilfe](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).
Wenden Sie sich an Ihren Customer Success Manager, um den Aktualisierungspfad zu überprüfen.

**[!DNL AEM Guides]Builds**

>[!NOTE]
>
>Wenden Sie sich an Ihren Customer Success Manager, um Zugriff auf [!DNL AEM Guides] Builds für AEM as a Cloud Service zu erhalten.

Die folgende Liste enthält die neuesten [!DNL AEM Guides]-Pakete, die für die Installation auf AMS oder On-Prem verfügbar sind, Download-Links von Paketen und weitere hilfreiche Informationen. Es wird empfohlen, nur den neuesten Build von [!DNL AEM Guides] zu verwenden. Wenn Sie aus irgendeinem Grund Zugriff auf ältere Builds benötigen, stellen Sie bitte eine Verbindung zum Customer Success Manager Ihres Kontos her.



>[!NOTE]
>
>Stellen Sie vor der Installation von Experience Manager Guides sicher, dass Ihr System die [technischen Anforderungen](../install-guide/download-install-technical-requirements.md) erfüllt.

| [!DNL AEM Guides] Version | Versionshinweise | Downloadlinks erstellen |
|---|---|---|
| **AEM Guides 4.6.0** | [4.6.0 Upgrade-Anweisungen](./upgrade-instructions-4-6-0.md)<br><br>[4.6.0 Neue Funktionen](./whats-new-4-6.md)<br><br> [4.6.0 Behobene Probleme](./fixed-issues-4-6-0.md) | **Nicht-UUID AEM 6.5** <br> [4.6.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-6%2Fcom.adobe.fmdita-6.5-4.6.0.164.zip) <br> **UUID AEM 6.5** <br>[4.6.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-6%2Fcom.adobe.fmdita-6.5-uuid-4.6.0.164.zip) |
| **AEM Guides 4.4.0** | [4.4.0 Aktualisierungsanweisungen](./upgrade-instructions-4-4.md)<br><br>[4.4.0 Neue Funktionen](./whats-new-4-4.md)<br><br> [4.4.0 Behobene Probleme](./fixed-issues-4-4.md) | **Nicht-UUID AEM 6.5** <br> [4.4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-4%2Fcom.adobe.fmdita-6.5-4.4.0.40.zip) <br> **UUID AEM 6.5** <br>[4.4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-4%2Fcom.adobe.fmdita-6.5-uuid-4.4.0.40.zip) |
| **AEM Guides 4.3.0** | [4.3.1.5 Aktualisierungsanweisungen](./upgrade-instructions-4-3-1-5.md)<br><br> [4.3.1 Versionshinweise](./release-notes-4-3-1.md)<br><br>[4.3.0 Versionshinweise](./release-notes-4-3.md) | **Nicht-UUID AEM 6.5** <br>[4.3.1.5](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3-1-5%2Fcom.adobe.fmdita-6.5-hotfix-4.3.1.5.1.zip)<br> [4.3.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3-1%2Fcom.adobe.fmdita-6.5-4.3.1.390.zip) <br> [4.3.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3%2Fcom.adobe.fmdita-6.5-4.3.0.347.zip)<br> **UUID AEM 6.5** <br>[4.3.1.5](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3-1-5%2Fcom.adobe.fmdita.uuid-6.5-hotfix-4.3.1.5.1.zip)<br> [4.3.1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3-1%2Fcom.adobe.fmdita-6.5-uuid-4.3.1.390.zip)<br>[4.3.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-3%2Fcom.adobe.fmdita-6.5-uuid-4.3.0.347.zip) |
| **AEM Guides 4.2** | [4.2.1 - Versionshinweise](release-notes-4-2-1.md)<br> <br> [4.2 Versionshinweise](./release-notes-4-2.md) | **non-UUID**: <br> **AEM 6,5** <br>[4,2,1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2-1%2F4-2-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.2.1.270.zip)<br>[4,2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2%2F4-2-non-uuid%2Fcom.adobe.fmdita-6.5-4.2.229.zip)<br><br> **UUID** <br>**AEM 6,5** <br>[4,2,1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2-1%2F4-2-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.2.1.270.zip)<br>[4,2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-2%2F4-2-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.2.229.zip)<br> |
| **AEM Guides 4.1** | [4.1.x - Versionshinweise](release-notes-4-1.md) | **non-UUID**: <br> **AEM 6,5** <br>[4,1,3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.3.2.zip)<br>[4,1,2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.1.2.11.zip)<br>[4,1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-non-uuid%2Fcom.adobe.fmdita-6.5-4.1.159.zip)<br><br> **UUID** <br>**AEM 6,5** <br>[4,1,3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-3%2F4-1-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.3.2.zip)<br>[4,1,2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1-2%2F4-1-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.1.2.11.zip)<br>[4,1](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-1%2F4-1-uuid%2Fcom.adobe.fmdita-6.5-uuid-4.1.159.zip) |
| **AEM Guides 4.0** | [4.0.x - Versionshinweise](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html) | **non-UUID**: <br> **AEM 6.5** <br>[4.0.3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-hotfix-4.0.3.1.zip)<br>[4.0.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-non-uuid%2Fcom.adobe.fmdita-6.5-sp-4.0.2.10.zip) <br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-non-uuid/com.adobe.fmdita-6.5-4.0.70.zip) <br><br> **UUID** <br>**AEM 6,5** <br>[4,0,3](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-3%2F4-0-3-uuid%2Fcom.adobe.fmdita.uuid-6.5-hotfix-4.0.3.1.zip) <br>[4,0,2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2F4-0-2%2F4-0-2-uuid%2Fcom.adobe.fmdita.uuid-6.5-sp-4.0.2.10.zip)<br> [4.0](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/4-0/4-0-uuid/com.adobe.fmdita-6.5-uuid-4.0.70.zip) |
| **AEM Guides 3.8.5** <br> 3.8.5 ist eine SP-Version, die auf Version 3.8 basiert. Die Version <br>3.8 darf nicht eigenständig installiert werden, da 3.8.5 SP eine kritische Korrektur enthält. <br>Kunden müssen zuerst 3.8 und dann SP 3.8.5 installieren. | [3.8.x - Versionshinweise](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-3-8.html) | **non-UUID**: <br> **AEM 6.5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.5-hotfix-3.8.5.2.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.5-3.8.166.zip)<br> **AEM 6.4** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.4-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.4-3.8.166.zip) <br> **AEM 6.3** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5/com.adobe.fmdita-6.3-hotfix-3.8.5.1.zip) <br>[3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8/com.adobe.fmdita-6.3-3.8.166.zip) <br><br> **UUID** <br>**AEM 6,5** <br> [3.8.5 SP](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8-5uuid/com.adobe.fmdita.uuid-6.5-hotfix-3.8.5.2.zip) <br> [3.8](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/3-8uuid/com.adobe.fmdita.uuid-6.5-3.8.168.zip) |
