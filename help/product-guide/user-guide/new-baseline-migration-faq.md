---
title: Häufig gestellte Fragen zur neuen Baseline-Migration in Adobe Experience Manager Guides
description: Erfahren Sie mehr über die häufig gestellten Fragen zur neuen grundlegenden Migration in Adobe Experience Manager Guides.
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: 919
ht-degree: 0%

---

# Häufig gestellte Fragen zur Baseline-Migration

In diesen häufig gestellten Fragen werden häufig gestellte Fragen zur neuen Baseline-Migration, zu Verhaltensänderungen, Überlegungen zur Migration und erwarteten Ergebnissen bei der Aktualisierung auf das neue Baseline-Modell behandelt.

## Was sind die wichtigsten Vorteile der Migration auf die neue Baseline?

Das neue Baseline-Modell bietet verschiedene Verbesserungen, darunter:

- Verbesserte Leistung und Skalierbarkeit
- Bessere Konsistenz der Benutzeroberfläche und des Backends
- Deterministisches Bearbeitungs- und Speicherverhalten
- Verbesserte Filter- und Navigationsfunktionen
- Vorschau der Auswirkungen von Abhängigkeiten
- Verbesserte Zuverlässigkeit bei der grundlegenden Erstellung und Aktualisierung
- Bessere API- und Automatisierungsunterstützung

## Erstellt die Baseline-Migration neue Baselines für alle Versionen einer Zuordnung?

Nein, der Migrationsprozess erstellt neue Baselines nur für die **aktuelle Arbeitskopie** der Zuordnung. Baselines, die mit anderen Arbeitskopien verknüpft sind, werden bei der Migration nicht berücksichtigt.

## Was passiert, wenn ein Benutzer zu einer früheren Version einer Zuordnung zurückkehrt?

Wenn eine frühere Version einer Zuordnung wiederhergestellt oder aufgerufen wird, werden die mit dieser Version verknüpften Baselines durch einen asynchronen Migrationsprozess automatisch zum neuen Baseline-Modell migriert.

## Werden ungültige Verweise auf die neue Baseline migriert?

Nein, ungültige Verweise werden während der Migration übersprungen, um die Baseline-Konsistenz zu wahren und die Zuverlässigkeit der migrierten Baseline sicherzustellen.

## Ändert die Baseline-Migration die Baseline?

Bei der Baseline-Migration werden alle gültigen Baseline-Inhalte und -Verweise genau so beibehalten, wie sie sind. Ungültige Verweise sind jedoch nicht in der migrierten Baseline enthalten. Abgesehen von der Entfernung ungültiger Verweise führt die Migration nicht zu Änderungen an Verweisen oder am Verhalten bei der Abhängigkeitsauflösung.

Alle weiteren Änderungen an Verweisen oder Abhängigkeitsauflösungen können erst vorgenommen werden, nachdem die migrierte Baseline mit dem neuen Baseline-Modell geändert, neu erstellt oder neu erstellt wurde.

Bis eine dieser Aktionen ausgeführt wird, spiegelt die migrierte Baseline weiterhin die ursprüngliche Baseline-Definition wider.

## Sind `reltable` Verweise im neuen Basismodell enthalten?

Nein, Referenzen, die von `reltable` Elementen stammen, werden von der Grundlinienauflösung ausgeschlossen, was dem Verhalten des alten Grundlinienmodells entspricht.

## Wie werden DIREKTE Verweise in der neuen Grundlinie gehandhabt?

Im neuen Baseline-Modell werden die direkten Zuordnungsverweise explizit als &quot;**&quot;**. Während der Migration und der Auflösung der Baseline erhalten diese Verweise die höchste Priorität und werden vor allen anderen Verweistypen aufgelöst.

## Sind `scope="peer"` Verweise in der Baseline enthalten?

Nein, Verweise mit `scope="peer"` sind nicht im Basismodell enthalten. Das Ausschließen dieser Verweise verbessert die Veröffentlichungsleistung und vermeidet unnötige Abhängigkeitsauflösungen.

## Können Baselines weiterhin über das Zuordnungs-Dashboard verwaltet werden?

Nein, die Baseline-Verwaltung wird nur über die **Map-Konsole** in „Neue Baseline“ unterstützt. Das Erstellen und Verwalten von Baselines über **Map-Dashboard** wird nicht unterstützt.

## Ist bei der Migration Vorsicht geboten?

Ja, Baseline-Änderungen sollten während einer Migration vermieden werden, insbesondere in Arbeitskopien. Änderungen an Baselines während der Migration können zu Migrationsfehlern führen und dazu, dass die Baselines in einem inkonsistenten Zustand verbleiben.

## Was passiert, wenn nach der Migration Versionen fehlen?

Einige Baselines müssen nach der Migration möglicherweise neu erstellt werden, wenn die Versionen, auf die diese Baselines verweisen, nicht mehr verfügbar oder nicht mehr zugänglich sind.


## Wie viel Zeit wird ungefähr benötigt, um die Baselines für eine On-Premise-Einrichtung zu migrieren?

Die Migrationszeit hängt von mehreren Faktoren ab, darunter:

- Die Anzahl der Baselines, die migriert werden
- Die Gesamtzahl der Verweise in diesen Baselines
- Größe und Komplexität des Repositorys
- Hardwarekonfiguration
- Verfügbare Systemressourcen

Basierend auf internen Tests und Beobachtungen aus Repositorys mit etwa 18.000 Referenzen kann die Migrationsdauer je nach Repository-Struktur und Betriebsumgebung erheblich variieren.

| Migrationsbereich | Typische Dauer |
|-----------------|------------------|
| Einzelne Baseline | Ein paar Sekunden |
| 10-15 Baselines | Ein paar Dutzend Sekunden |
| 25-50 Baselines | Ca. 1-2 Minuten |

>[!NOTE]
>
> Diese Zahlen dienen nur als Referenz und basieren auf einer On-Premise-Umgebung. Die tatsächlichen Werte können je nach Repository-Komplexität, Infrastrukturkapazität, Hardware-Konfiguration und allgemeinen Betriebsbedingungen variieren.

## Können wir wieder zu alten Ausgangswerten zurückkehren?

Ja. Wenn jedoch ein Rollback durchgeführt wird, werden die alten Baselines in den Zustand zurückgesetzt, in dem sie sich zum Zeitpunkt der Migration befinden. Änderungen, die vorgenommen wurden, während die alte Baseline-Konfiguration deaktiviert und die neue Baseline-Konfiguration aktiv ist, werden in den wiederhergestellten Baselines nicht übernommen.

Die ursprünglichen alten Basisobjekte bleiben an ihrer ursprünglichen Position verfügbar. Wenn die neue Basiskonfiguration deaktiviert ist, wechselt das System automatisch zur Verwendung dieser ursprünglichen Objekte zurück.

## Wie können wir zu neuen Baselines migrieren?

Um zu einer neuen Baseline zu migrieren, führen Sie die Schritte unter [Zu neuer Baseline migrieren](./web-editor-baseline-v2.md#migrate-to-new-baseline) aus.

## Können wir jederzeit zur neuen Baseline migrieren? Gibt es Voraussetzungen?

Ja. Sie können die neue Baseline jederzeit aktivieren, solange Ihre Umgebung die Mindestanforderungen an die Version erfüllt.

**Voraussetzungen:**

- AEM Guides (On-Premise): Version 5.2 oder höher
- AEM Guides (Cloud Service): Version 2026.05.0 oder höher

Sobald diese Anforderungen erfüllt sind, können Sie Ihre bestehenden alten Baselines zum neuen Baseline-Modell migrieren und mit der Verwendung seiner Funktionen beginnen.

## Muss der aktuelle Serverstatus gesichert werden, bevor zur neuen Baseline migriert wird?

Speziell für die Migration auf die neue Baseline ist keine zusätzliche Sicherung erforderlich.

Baselines, die mit der Arbeitskopie verknüpft sind, können jedoch verloren gehen, wenn ein Benutzer später einen Vorgang zum Zurücksetzen der Version ausführt. Dieses Verhalten ist nicht nur auf das neue Baseline-Modell beschränkt. Wenn Sie zu einer früheren Version zurückkehren, können Sie auch die entsprechenden alten Baseline-Arbeitskopie-Knoten entfernen.

Wenn es wichtig ist, die Baselines der Arbeitskopie beizubehalten, wird empfohlen, sie vor der Migration zu sichern. Nach der Migration arbeiten Benutzer hauptsächlich mit neuen Baselines, aber eine spätere Versionsrücksetzung kann immer noch zum Verlust von Arbeitskopie-Baselines führen.


