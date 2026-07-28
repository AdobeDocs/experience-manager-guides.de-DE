---
title: API-Aktualisierungen in Experience Manager Guides-Versionen
description: Erfahren Sie mehr über die verschiedenen API-Aktualisierungen in Experience Manager Guides-Versionen
source-git-commit: 24637376024107ae575620e5491c0150da6cc956
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 7%

---


# API-Aktualisierungen in Experience Manager Guides-Versionen

Dieser Artikel enthält Details zu den neu hinzugefügten APIs in der Swagger-Dokumentation für Adobe Experience Manager Guides-Versionen. Sie können über die AEM-Benutzeroberfläche auf die Swagger-Dokumentation zugreifen, indem Sie zu **Tools** > **Handbücher** > **API Swagger** navigieren.

<table style="border: 1; border-collapse: collapse; table-layout:fixed">
    <tr>
        <td colspan="5"><strong>Version 2026.08.0</strong></td>
    </tr>
    <tr>
        <td>Funktion</td>
        <td>Unterfunktion</td>
        <td>Methode</td>
        <td>API</td>
        <td>Beschreibung</td>
    </tr>
    <tr>
        <td rowspan="7"><b>Assets</b></td>
        <td rowspan="7"></td>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/import“</td>
        <td>Importiert ein oder mehrere Assets in einen Zielordner und unterstützt mehrteiliges Hochladen und Konfliktlösung</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/list“</td>
        <td>Gibt eine paginierte Liste der Assets unter einem Ordnerpfad zurück.</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/validatexml“</td>
        <td>Validiert DITA XML auf Korrektheit, Schemagültigkeit und Context-Integrität</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/version/revert“</td>
        <td>Setzt ein Asset auf eine angegebene Version zurück</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/asset/currentVersion/detail“</td>
        <td>Gibt aktuelle Versionsdetails zurück (Versionsname, Änderungsstatus, Kennzeichnungen usw.)</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/assets/status“</td>
        <td>Startet einen asynchronen Vorgang, um den Guides-Status von Assets unter den angegebenen Pfaden zu überprüfen</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/assets/status“</td>
        <td>Ruft Status/Ergebnisse eines Asset-Statusauftrags nach Auftrags-ID ab</td>
    </tr>
    <tr>
        <td rowspan="3"><b>Publishing</b></td>
        <td rowspan="3"></td>
        <td>POST</td>
        <td>"/bin/guides/v1/output/generate“</td>
        <td>Startet die Ausführung der Voreinstellung, um eine Ausgabe für eine Zuordnung zu erzeugen</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/output/status“</td>
        <td>Gibt den Status einer einzelnen Ausgabegenerierung nach Zuordnungspfad und Erzeugungs-ID zurück.</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/output/status/list“</td>
        <td>Gibt den Status aller generierten Voreinstellungen für einen Zuordnungspfad zurück.</td>
    </tr>
    <tr>
        <td rowspan="18"><b>Übersetzung</b></td>
        <td rowspan="6">Sprache</td>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/copy“</td>
        <td>Sprachkopien eines Assets nach Pfad oder UUID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/groups“</td>
        <td>Sprachgruppen für ein Ordnerprofil</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/list“</td>
        <td>Unterstützt Übersetzungssprachen (gefiltert)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/root“</td>
        <td>Für einen Asset-Pfad verfügbare Stammsprachen</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/variable“</td>
        <td>Sprachvariablen nach Typ und Sprach-Codes</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/language/variable“</td>
        <td>Erstellt, aktualisiert oder löscht Sprachvariablen</td>
    </tr>
    <tr>
        <td rowspan="7">Projekt</td>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/project/create“</td>
        <td>Übersetzungsprojekt für eine DITA-Map erstellen/aktualisieren</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/project/sync“</td>
        <td>Erstellt/aktualisiert ein Übersetzungsprojekt (Synchronisierungsfluss)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/creationstatus“</td>
        <td>Synchronisierungsstatus für eine Übersetzung für ein Projekt nach Pfad</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/existing“</td>
        <td>Vorhandene Übersetzungsprojekte für den aktuellen Benutzer</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/inProgress“</td>
        <td>In Bearbeitung befindliche Projekte für ein bestimmtes Asset</td>
    </tr>
    <tr>
        <td>LÖSCHEN</td>
        <td>"/bin/guides/v1/translation/project/delete“</td>
        <td>Vorabaktualisierung von Asset-Übersetzungsstatus/-eigenschaften</td>
    </tr>
    <tr>
        <td>LÖSCHEN</td>
        <td>"/bin/guides/v1/translation/project/job/delete“</td>
        <td>Vorabaktualisierung des Asset-Status vor dem Entfernen des Auftrags</td>
    </tr>
    <tr>
        <td rowspan="5">Referenz</td>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/accepted“</td>
        <td>Übersetzte Inhalte von untergeordneten Auftragsseiten akzeptieren</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/ject“</td>
        <td>Ablehnen übersetzter Inhalte von untergeordneten Auftragsseiten</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/sync“</td>
        <td>Erstellen von Sprachkopien in Zielordnern</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/baseline/export“</td>
        <td>Export der Übersetzungsgrundlinie in die Zielsprachen</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/status/forceSync“</td>
        <td>Erzwingen einer Aktualisierung von nicht synchronisierten Assets in synchronisierten Assets</td>
    </tr>
</table>
