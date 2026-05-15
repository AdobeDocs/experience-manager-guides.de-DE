---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.1.0 Service Pack 3 von Adobe Experience Manager Guides
role: Leader
exl-id: faa9a5d7-616f-4692-98d1-23abc78556b6
TQID: https://experienceleague.adobe.com/qiVY-B-D3FcHq2PH7Go2AAFpnstCrPJ2MVLEalQCVn0
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 297
ht-degree: 2%

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
