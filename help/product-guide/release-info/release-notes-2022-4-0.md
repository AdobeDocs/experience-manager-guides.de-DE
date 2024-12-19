---
title: Versionshinweise zu | Adobe Experience Manager Guides as a Cloud Service, Version April 2022
description: April-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: c735ba24-a803-454b-8723-57dacf90061b
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---

# April-Version von Adobe Experience Manager Guides as a Cloud Service

## Upgrade auf die April-Version

Führen Sie ein Upgrade Ihres aktuellen [!DNL Adobe Experience Manager Guides] as a Cloud Service-Setups (später *[!DNL AEM Guides]as a Cloud Service*-Setup genannt) durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Service aus und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Service-Git-Codes auf Version 2022.4.133.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die April-Version von [!DNL AEM Guides] as a Cloud Service zu aktualisieren.

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von [!DNL AEM Guides] as a Cloud Service-Version April 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 2020 4 und höher |
| | |


### Sauerstoffanschluss

| AEM Guides Cloud-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac |
| --- | --- | --- |
| 2022.4.0 | 2,5,6 | 2,5,6 |
|  |  |  |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

## Neue Funktionen und Verbesserungen

Im Web-Editor wurden viele Verbesserungen und neue Funktionen hinzugefügt:

### Verbesserte Schlüsselauflösung

Ein DITA-Inhaltsschlüssel-Verweis fügt einen Teil des Inhalts von einem Thema in ein anderes ein. Sie verwendet eine -Taste, um den Inhalt zu finden. Die wichtigsten Referenzen, die mit einem DITA-Thema verbunden sind, müssen aufgelöst werden. Die ausgewählte Stammzuordnung hat die höchste Priorität, um Schlüsselverweise aufzulösen.

![Dialogfeld „Benutzereinstellungen“](assets/user-preferences.png)

Jetzt werden die Schlüsselverweise auf der Grundlage der Stammzuordnung aufgelöst, die in der folgenden Prioritätsreihenfolge festgelegt ist:

1. Benutzereinstellungen
1. Kartenansichtsbereich
1. Ordnerprofil

Weitere Informationen finden Sie *Abschnitt &quot;* auflösen“ im Benutzerhandbuch.

### Hinzufügen eines benutzerdefinierten Bereichs im linken Bereich

Jetzt können Sie ein benutzerdefiniertes Bedienfeld im linken Bedienfeld des Web-Editors hinzufügen. Sie können ein benutzerdefiniertes Bedienfeld für verschiedene Zwecke verwenden, z. B. für die Bereitstellung von Hilfe oder für Tests für ein Projekt. Wenn ein benutzerdefiniertes Bedienfeld konfiguriert wurde, wird es auch in der Liste der Bedienfelder in den **Editor-Einstellungen** angezeigt. Sie können den Schalter umschalten, um das benutzerdefinierte Bedienfeld ein- oder auszublenden.

### Möglichkeit, den Dokumentstatus von Themen in einer DITA-Zuordnung zu ändern

Jetzt können Sie den Dokumentstatus ausgewählter Themen innerhalb einer DITA-Karte einfach ändern. Sie können die Eigenschaften ausgewählter Themen in einer DITA-Karte auch über das Menü **Weitere Optionen** unten im Kartenansichtsfenster öffnen und bearbeiten.

![Ausgewählte Themeneigenschaften](assets/map-view-properties.png)

### Im Vorschaumodus angezeigte Versionsinformationen

Der Web-Editor hilft Ihnen bei der Verwaltung Ihrer Versionen. Jetzt können Sie im Vorschaumodus eines Themas auch die Version des aktiven Themas oder die DITA-Map in der oberen rechten Ecke der Datei-Registerkarte des Themas sehen.

![Vorschauversion](assets/preview-version.png)

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Neue Beschriftungen werden nicht automatisch in der Dropdown-Liste Beschriftung hinzufügen/entfernen angezeigt. Stattdessen ist eine Aktualisierung der Grundlinie erforderlich. (9249)
* Der Titel der Baseline kann nicht bearbeitet werden, wenn eine Baseline durch Kennzeichnungskriterien erstellt wird. (9171)
* Der Veröffentlichungsauftrag mit einer Baseline bleibt im Status „Warten“ stecken, wenn sich der Baseline-Status in „Fehlgeschlagen“ ändert. (9194)
* Durch das Entfernen von Beschriftungen von direkten Verweisen werden auch die Beschriftungen von indirekten Verweisen entfernt. (9257)
* Die Suche während der Eingabe führt zu unerwünschten Suchanfragen in der Repository-Ansicht. (9307)
* Probleme treten auf, wenn ein beliebiges Keyword im Titel für eine Registerkarte verwendet wird. (9318)
* Baseline schlägt beim Hinzufügen einer Beschriftung mit Leerzeichen fehl. (9362)
* In der AEM-Site-Ausgabe wird das Glossusage-Element nicht korrekt angezeigt. (8 936)
* Konsolenfehler beim Öffnen der Registerkarte **Ausgabe** im Web-Editor. (8715)
* Die Fehlermeldung, die beim Veröffentlichen eines manuellen Datensatztyps über Salesforce angezeigt wird, ist nicht intuitiv. (8952)
* Die Einstellung Mit Bedingungsattributen validieren wird nicht sofort geöffnet, sondern der Benutzer muss die Datei erneut öffnen, um die Validierungen sehen zu können. (9300)
* Metadaten können nicht entfernt werden, sobald eine DITA-Zuordnung mit Metadaten veröffentlicht wurde.  (9178)
* Das Übersetzungsbedienfeld ist selbst beim Öffnen der DITA-Karte im Karten-Editor sichtbar. (9053)
* Die vom Benutzer definierte benutzerdefinierte DTD hat keinen Vorrang vor der in DITA-OT eingebetteten standardmäßigen DITA-DTD. (9104)
* Bei der Native PDF-Funktion schlägt der Upload in den Vorlagen für Nicht-DITA- und Nicht-Bilddateien fehl. (9070)
* Der Autorisierungsmechanismus führt in einigen spezialisierten Szenarien zwei Abfragen anstelle von einer aus. (9221)
* Das Veröffentlichen der AEM-Site-Ausgabe schlägt bei der Verwendung der benutzerdefinierten DTD fehl. (9243)
* In der Ausgabe der AEM-Site wird die Fußnote als Verweis verwendet, aber es wird nicht zum Fußnotenabschnitt gescrollt. (9234)

## Bekannte Probleme

Adobe hat das folgende bekannte Problem in der Version [!DNL AEM Guides] as a Cloud Service April festgestellt.

* Der Web-Editor meldet keinen Fehler, wenn zwei oder mehr Baselines mit demselben Namen erstellt werden, aber Unterschiede in Leerzeichen oder Groß-/Kleinschreibung aufweisen. Zum Beispiel „adobe“ und &quot;Adobe &quot; oder &quot;Adobe&quot;.
* Der Oxygen-Connector hängt gelegentlich, während er häufige Anmelde- oder Abmeldevorgänge durchführt oder zwischen verschiedenen Authentifizierungstypen wechselt.
