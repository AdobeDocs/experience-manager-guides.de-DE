---
title: SCORM-Schlüsselmetriken für Lernfortschritt und Kursabschluss
description: Erfahren Sie mehr über die SCORM-Schlüsselmetriken für den Fortschritt der Teilnehmer und den Abschluss des Kurses
feature: Authoring
role: Admin
level: Experienced
exl-id: f25cbbbd-5d9f-47b0-9260-8062e026913d
TQID: https://experienceleague.adobe.com/ZyY9sjaqGANXlUI5l3OsP-i1Pu-es-B-iGnpPJjQYrY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 1%

---

# SCORM-Schlüsselmetriken für Lernfortschritt und Kursabschluss

In diesem Artikel werden die in einem SCORM-Paket erfassten Schlüsselparameter zusammen mit den entsprechenden Feldern und Beispielen aufgeführt. Diese Parameter bieten wichtige Einblicke in den Fortschritt der Lernenden, den Abschluss des Kurses, Interaktionsdetails und die Quizleistung. Administratoren können diese Informationen verwenden, um das Tracking zu validieren, das Reporting zu konfigurieren und genaue Analysen innerhalb der LMS-Umgebung sicherzustellen. Nachfolgend finden Sie Beispielwerte für jeden Parameter, wie er im SCORM-Paket angezeigt wird.

| **Parametername** | **Beschreibung** | **Felder** | **Beispiel** |
|---|---|---|---|
| **Kursabschlussstatus** | Gibt an, ob der Kurs abgeschlossen ist oder nicht | cmi.completion_status | unvollständig |
| **Anzahl der Versuche** | Anzahl der Versuche, die der Teilnehmer unternommen hat | LMS-seitiger Versuchszähler/Inhalt | Versuche: 1 |
| **Speicherort des SCORM-Pakets** | Aktuelles Lesezeichen oder aktuelle Position im Kurs | cmi.location | – |
| **Fortschritt abgeschlossen** | Learner&#39;s progress | cmi.progress_measurement | 0,87 |
| **Gesamtzeit (Versuch)** | Gesamtbesuchszeit für den aktuellen Versuch | cmi.total_time | 0000:01:09.87 |
| **Inhaltsverzeichnissichtbarkeit und Themenanzahl** | Zeigt Details zur Inhaltsverzeichnissichtbarkeit und zum Themenabschluss an | project.hideTOC, project.totalTopics, project.topicsCompleted | – |
| **Status pro Thema** | Abschlussstatus und Bestanden-Status für jedes Thema | Benutzerdefinierter Status pro Lektion | – |
| **Status der Auswahl pro Frage** | Verfolgt die von Teilnehmern ausgewählten Auswahlmöglichkeiten pro Frage. | Wert, generate_id, geprüft | – |
| **Bewertung allgemeiner Fragen** | Auf Fragenebene erzielte Punktzahl und Aggregat | {„score“:0,„maxScore“:1} und % | „score“:33.33,„maxScore“:100,„minScore“:0 |
| **Interaktionen auf jeder Fragenebene** | Details zur Teilnehmerinteraktion pro Frage | ID/Typ/Zeitstempel/Correct_Response/Learner_Response/Result/Latency | – |
| **Gesamtstatus des Kurses** | Zeigt Bestanden/Fehlgeschlagen und Gesamtfortschritt an | success_status, completion_status, score, progress_measurement | Ob bestanden oder nicht bestanden |
| **Teilnehmerdetails** | Identifiziert den Teilnehmer nach ID und Namen | cmi.learner_id, cmi.learner_name | Albert |
| **Quiz-Parameter** | Konfigurationen für Quiz-Timing und Bestehen der Punktzahl | CMI.MAX_TIME_ALLOWED, CMI.SCALED_PASSING_SCORE, CMI.TIME_LIMIT_ACTION | Nicht definierte oder konfigurierte Werte |
