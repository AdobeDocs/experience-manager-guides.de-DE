---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides 5.1.0 Service Pack 3 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.1.0 Service Pack 3 von Adobe Experience Manager Guides
role: Leader
source-git-commit: 82eb0e18eb285006c66b1fe2b6ecc3ca86fefe61
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---

# Es wurden Probleme in Version 5.1.0 Service Pack 3 (Dezember 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.1.0 Service Pack 3 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für Version 5.1.0 Service Pack 3](upgrade-instructions-5-1-0-sp3.md).


## Authoring

- Benutzerdefiniertes CSS, das auf ein Profil auf Ordnerebene für Themen oder Zuordnungen angewendet wird, wird bei der Browser-Aktualisierung im Vorschaumodus auf den Standardstil zurückgesetzt. (GUIDES-31098)
- Es können nicht mehrere **Versionsbezeichnungen** zu einem Thema im Dialogfeld **Als neue Version speichern** hinzugefügt werden. (GUIDES-32716)


## Asset-Management

- Versionsbeschriftungen können nicht aus dem Bedienfeld **Versionsverlauf** in der Assets-Benutzeroberfläche entfernt werden. (GUIDES-38276)


## Überprüfung

- Wenn ein Reviewer eine Prüfungsaufgabe abschließt oder der Initiator die Prüfungsaufgabe aktualisiert, ohne Kommentare einzugeben, zeigt die gesendete Benachrichtigungs-E-Mail den letzten vorherigen Kommentar an. (GUIDES-33590)

## Publishing

- Wenn Sie AEM Sites-Ausgaben mit der Zuordnung veralteter Komponenten generieren, werden Themen, die das `copy-to` verwenden, mit dem Namen des `copy-from` Themas anstelle des im `copy-to` festgelegten Namens veröffentlicht. (GUIDES-22155)
- Wenn die native PDF-Ausgabe mithilfe einer dynamischen Baseline generiert wird, wird der **PDFProject** als PDF-Titel anstelle des eigentlichen Zuordnungstitels angezeigt. (GUIDES-31102)

## Platform

- Wenn Sie `scope="external"` für einen Verweis auf DAM-Inhalte in einem Thema oder einer Zuordnung verwenden, wird der relative Pfad des Assets durch eine GUID ersetzt. (GUIDES-35605)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem in Version 5.1.0 Service Pack 3 erkannt:

- Wenn Sie eine Prüfungsaufgabe auf der Seite mit den Aufgabendetails als abgeschlossen markieren, wird die Aufgabe abgeschlossen und geschlossen. Ihr Status wird jedoch weiterhin als **In Bearbeitung** im Überprüfungs-Dashboard angezeigt. (GUIDES-39375)




