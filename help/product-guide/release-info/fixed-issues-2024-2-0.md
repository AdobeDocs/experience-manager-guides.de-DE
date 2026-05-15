---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2024.2.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.2.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
TQID: https://experienceleague.adobe.com/z-L0sZ2HH720nI3LyDjiIqujxSBP-QLdPqvEInNNRnE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 8%

---

# Es wurden Probleme in der Version 2024.2.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.2.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.2.0](whats-new-2024-2-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Authoring

- Die Rechtschreibprüfung im Editor erlaubt keine Auswahl von Vorschlägen. (15045)
- Die Schaltfläche für die globale Navigation funktioniert nicht und das Dashboard kann nicht geladen werden. (14968)
- Im Web-Editor kann mit der Funktion „Zuordnung herunterladen“ keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. (14626)
- Im Web-Editor kann mit der Funktion „Karte herunterladen“ keine Karte mit Grundlinie heruntergeladen werden. (14622)
- Ungültiger DTD-Fehler in der Version vom Oktober 2023 von Experience Manager Guides as a Cloud Service. (14482)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref` erstellt. (10767)
- Der Vorschaubildschirm für Snippets ist eingefroren. (14840)
- Kennzeichnungen aus der `labels.json`-Datei werden im Web-Editor in zufälliger Reihenfolge angezeigt. (10508)

## Publishing

- In der nativen PDF-Veröffentlichung funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für die native PDF-Veröffentlichung. (14943)
- In der nativen PDF-Veröffentlichung werden die wichtigsten Verweise für die Adobe Experience Manager Guides-Version vom Dezember 2023 nicht aufgelöst. (15085)
- Die AEM Sites-Veröffentlichung schlägt fehl und verursacht Bereichsfehler für Dateien, die mit der DITA-Datei `xref` sind, die mit „HTTP“ beginnt. (15154)
- Es kann keine benutzerdefinierte Vorlage über die Registerkarte **Ausgaben** im Editor hinzugefügt werden. (14846)
- **AEM Site**-Voreinstellung funktioniert nicht, da der Vorlagenpfad leer ist. (14804)
- Die AEM-Site-Regenerierung schlägt für DITA-Zuordnungen mit Themen fehl, die MathML-Gleichungen enthalten. (14790)
- In der nativen PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für die `Node.js`-Veröffentlichung aus. (14445)
- Die AEM-Vorgabe lässt die Auswahl einer Vorlage außerhalb der `/content` im Web-Editor nicht zu. (14260)
- In der AEM Sites-Ausgabe gingen der Stil bzw. die Zeilenumbrüche für das `<lines>` mit Unterelementen verloren. (12542)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. (12116)
- In der nativen PDF-Veröffentlichung können die Metadateneigenschaften der DITA-Zuordnung nicht zum Ausfüllen der Metadaten für die PDF-Dateiausgabe verwendet werden. (15159)



## Verwaltung

- **Grundlinienfilter**-Dateien funktionieren im Web-Editor nicht mit Dateinamen. (13486)
- Wenn Sie die Indizierung der übergeordneten DITA-Zuordnung deaktivieren, um eine bessere Leistung zu erzielen, kann dies Auswirkungen auf die Funktionalität bestimmter Funktionen haben.(12213)


## Überprüfung

- Das Kontextmenü mit der rechten Maustaste funktioniert nicht für **Akzeptieren** oder **Ablehnen** Tracking von Änderungen. (14607)
- Das Umschalten zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in der Adobe Experience Manager Guides-Version Dezember 2023 nicht. (14537)
- Das Anpassen von E-Mail-Vorlagen für den Überprüfungs-Workflow funktioniert nicht mit Überlagerung. (13954)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem in Version 2024.2.0 identifiziert:

- Version 1.0 wird für die duplizierte DITA-Datei nicht auf der Benutzeroberfläche angezeigt.
- Die Übertragung von Asset-Metadaten funktioniert in der Version 2024.2.0 nicht, wenn der Microservice für eine Vorgabe aktiviert ist.
