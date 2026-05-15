---
title: Versionshinweise für [!DNL AEM Guides], März 2022
description: März-Version von  [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/--ZHijFEci8WcWunPdIVL67S0ipVDzifIIDl6VLK7dg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 774
ht-degree: 1%

---

# März-Version von [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Upgrade auf die März-Version

Führen Sie ein Upgrade Ihres aktuellen [!DNL Adobe Experience Manager Guides] as a Cloud Service-Setups (später *[!DNL AEM Guides]as a Cloud Service* bezeichnet) durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2022.3.123.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die März-Version von [!DNL AEM Guides] as a Cloud Service zu aktualisieren.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von [!DNL AEM Guides] as a Cloud Service-Version März 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 2020 4 und höher |
| | |


### Sauerstoffanschluss

| [!DNL AEM Guides] Cloud-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

## Neue Funktionen und Verbesserungen

### Neues Baseline-Dashboard

[!DNL AEM Guides] as a Cloud Service-Version März bietet die in den Web-Editor integrierte Funktion „Baseline“. Sie können jetzt aus dem Web-Editor Baselines erstellen und diese zum Veröffentlichen oder Übersetzen von Themen verschiedener Versionen verwenden.

Hinweis: Aktualisieren Sie für ein System-Upgrade die neueste Datei **ui_config.json** für das Ordnerprofil.

Verwenden Sie diese Funktion, um eine Baseline mit einer bestimmten Version der Themen zu erstellen, die an einem bestimmten Datum und zu einer bestimmten Uhrzeit verfügbar sind. Außerdem erhalten Sie API-Unterstützung zum Erstellen oder Aktualisieren einer Baseline mit einer für eine Themenversion definierten Bezeichnung.

![Registerkarte „Baseline verwalten“](assets/baseline-manage.png)

Sie können die Dateien nach Dateinamen oder Speicherort durchsuchen. Sie können auch die Themen filtern, die im Baseline-Bearbeitungsfenster angezeigt werden sollen, und sie nach bestimmten Spalten sortieren.

![Registerkarte „Baseline verwalten“](assets/baseline-filter.png)

Die Leistung für den grundlegenden Erstellungsprozess wurde weiter verbessert. Der Prozess zum Erstellen von Grundlinien ist asynchron, sodass Sie andere Dateien im Web-Editor weiter bearbeiten können, während die Grundlinie erstellt wird. Weitere Informationen finden Sie unter *Erstellen und Verwalten von Baselines im Web* Editor im Benutzerhandbuch.

Hinweis: Die Registerkarte Baseline im Zuordnungs-Dashboard ist standardmäßig ausgeblendet. Ihre bzw. Ihr Admin kann die Registerkarte Baseline im Zuordnungs-Dashboard aktivieren.

### Verbessertes Aktualisierungsverhalten des Web-Editors

Die folgenden Verbesserungen sind jetzt mit dem Browser-Aktualisierungsvorgang im Web-Editor verfügbar:

* Jetzt erhalten Sie die Unterstützung, den Browser zu aktualisieren, während Sie Ihre
Inhalte im Web-Editor. Wenn Sie auf das Browser-Aktualisierungssymbol klicken, während eine oder mehrere Dateien mit
Nicht gespeicherte Änderungen werden zur Bearbeitung geöffnet. Sie werden aufgefordert, Ihre Dateien zu speichern oder die Aktualisierungsaktion abzubrechen.

* Selbst beim Aktualisieren des Browsers werden die Ansichten des linken und des rechten Bedienfelds beibehalten.

* Das aktive Thema oder die DITA-Karte wird im Inhaltsbearbeitungsbereich erneut geöffnet.

### Verbesserungen beim Veröffentlichen

Der Veröffentlichungsprozess wurde mit der März-Version von [!DNL AEM Guides] as a Cloud Service weiter verbessert:

* Für die Metadaten der AEM-Site-Ausgabe wurden Baselines berücksichtigt. Sie können auch die Eigenschaften einer Baseline-Version als Metadaten verarbeiten. Wenn keine Baseline definiert ist, werden die Eigenschaften der neuesten Version als Metadaten verarbeitet.

* Die **Dateiname** und **DITA-OT-Befehlszeilenargumente** wurden für HTML5-, EPUB- und benutzerdefinierte Ausgabevorgaben hinzugefügt. Jetzt können Sie den Dateinamen angeben, mit dem Sie die Ausgabe speichern möchten. Sie können auch die zusätzlichen Argumente angeben, die DITA-OT beim Generieren der Ausgabe verarbeiten soll.

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Es ist nicht möglich, mit der Autorenansicht des Web-Editors Frontend- und Backmatter-Elemente in einer Lesekarte hinzuzufügen. (7652)
* Nach dem Entfernen eines Themas und dem Ausführen eines Verschiebungsvorgangs wird die Referenzstruktur unterbrochen. (8804)
* Ausnahme bei der Anzeige des Inhalts nach dem Hochladen eines Assets. (3638)
* Der Fehler tritt auf, wenn Dateien, deren übergeordneter Ordner Sonderzeichen im Dateinamen enthält, in Oxygen geöffnet werden (über die **Bearbeiten in Oxygen**). (8918)
* Mit **Option „Im Repository suchen** wird die DITA-Zuordnung im XML-Editor nicht gefunden und hervorgehoben. (8796)
* Beim Filtern werden nicht die entsprechenden Ergebnisse angezeigt, wenn dem Inhalt im XML-Editor mehrere Attribute hinzugefügt werden. (8795)
* Fehler beim Hinzufügen eines Benutzers als Administrator zum Profilordner, wenn die Benutzer-ID numerisch ist. (8908)

## Bekannte Probleme

Adobe hat das folgende bekannte Problem in der [!DNL AEM Guides] as a Cloud Service-Version vom März erkannt.

* Durch das Entfernen von Beschriftungen von direkten Verweisen werden auch die Beschriftungen von indirekten Verweisen entfernt.

* Der aktualisierte Baseline-Titel kann nicht angezeigt werden, ohne dass das Baseline-Bedienfeld manuell aktualisiert wird.

* Die Versionsvorschau-Funktion im Bedienfeld Versionsverlauf zeigt keine Vorschau eines ausgewählten Themas an.
