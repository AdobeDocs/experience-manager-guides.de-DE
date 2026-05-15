---
title: Empfehlungen zur Leistungsoptimierung
description: Erfahren Sie mehr über Recommendations zur Leistungsoptimierung
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/6q077Ib1EIQ4AA51ktmZ966RZrSt08xJQh5t4llzgbQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 917
ht-degree: 0%

---

# Empfehlungen zur Leistungsoptimierung {#id213BD0JG0XA}

## Konfigurieren des Datenspeichers \(obligatorisch\)

**Was ist die Änderung?**
Legen Sie die `minRecordLength`-Eigenschaft im `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` für die Konfiguration auf den Wert `100` fest. Weitere Informationen zum Dateidatumsspeicher und zum S3-Datenspeicher finden Sie im [Konfigurieren von Knotenspeichern und Datenspeichern in AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html) .

>[!NOTE]
>
> Bei S3-Datenspeichern hängen die Kosten für die Pflege von Inhalten im Datenspeicher ebenfalls von der Anzahl der Anfragen ab. Daher sollten bei dieser Einstellung mit S3 auch die Einrichtungskosten pro Anfrage und die Cache-Größe berücksichtigt werden.

**Wann konfigurieren?**
Nach der Ersteinrichtung, aber vor der Migration von Inhalten. Sie müssen diese Änderung auch für ein vorhandenes System durchführen, um sicherzustellen, dass alle neuen Inhalte im Datenspeicher und nicht im Segmentspeicher gespeichert werden.

**Ergebnis dieser Änderung**
Die DITA-Dateien werden im Datenspeicher und nicht im Segmentspeicher gespeichert. Dadurch bleibt die Größe des Segmentspeichers unter den empfohlenen Grenzwerten, was die Reaktionsfähigkeit des Systems verbessert.

## Lucene-Index aktualisieren \(obligatorisch\)

**Was ist die Änderung?**
Schließen Sie /var/dxml aus oak/:index aus.

>[!NOTE]
>
> AEM Guides verwendet keine Lucene-Indizes für die Suche nach Inhalten im Knoten /var/dxml.

**Wann konfigurieren?**
Wenn Sie diese Änderung auf einem neuen System vornehmen, bevor Sie Inhalte migrieren, ist nur eine Aktualisierung von Oak:index/Lucene erforderlich. Erstellen Sie andernfalls auf einem vorhandenen System, auf dem der Inhalt bereits migriert ist, nach der Änderung in oak:index/lucene die Indizes für Lucene \(*was einige Stunden dauern kann*\) neu.

**Ergebnis dieser Änderung**
Durch diese Änderung wird verhindert, dass der Knoten &quot;/var/dxml“ indiziert und im Segmentspeicher gespeichert wird.

## Java-Speicheroptimierung \(obligatorisch\)

**Was ist die Änderung?**
Die JVM-Startparameter sollten sorgfältig auf der Grundlage der Infrastruktur und der Festplattengröße angepasst werden. Es wird empfohlen, den Adobe-Support zu konsultieren, um Hilfe beim Zugriff auf die ideale Konfiguration zu erhalten. Sie können jedoch die folgenden Konfigurationen selbst ausprobieren:

: Setzen Sie die JVM-Heap-Größe auf ein Minimum von einem Viertel des insgesamt verfügbaren Speichers. Verwenden Sie den `-Xmx<size>`, um die Heap-Speichergröße festzulegen. Legen Sie für den Wert -`Xms` den Wert `-Xmx` fest.

- Aktivieren Sie `-XX:+HeapDumpOnOutOfMemoryError` und legen Sie den Pfad für die `-XX:HeapDumpPath=</path/to/folder` `>` fest.

- Aktivieren Sie das Java GC-Protokoll als:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- Verwenden Sie im Allgemeinen für Java 11 G1GC \(`-XX:+UseG1GC`\) und für Java 8 CMS \(-`XX:+UseConcMarkSweepGC`\).

- Verwenden Sie `-XX:NewRatio`, um die Größe des Speichers der jungen Generation zu steuern. Der Standardwert ist 2, was bedeutet, dass 1/3 des Speichers für die junge Generation verwendet wird. Da es viele Objekte gibt, die schnell erstellt und zerstört werden, wird bei Verwendung eines Werts von 1 1/2 des Speichers der jungen Generation zugewiesen.

- Steuern der Anzahl der Objekte, die für die alte Generation hochgestuft werden, mithilfe von `-XX:MaxTenuringThreshold`. Verwenden Sie den Wert 15 \(default\), um zu verzögern, wenn Objekte auf die alte Generation hochgestuft werden.

**Wann konfigurieren?**
Wenn Sie diese Änderung auf einem vorhandenen System vornehmen, müssen Sie das System neu starten. Im Falle einer Neuinstallation sollte diese Änderung vor dem Systemstart in der Datei \(.bat oder .sh\) vorgenommen werden.

**Ergebnis dieser Änderung**
Dies führt zu einer optimalen Heap-Größe und einer regulierten Ausführung von GC.

## Minimierung der Client-Bibliothek auf der Autoreninstanz \(optional\)

**Was ist die Änderung?**
Die Client-Bibliotheken sollten so eingestellt sein, dass sie in den Autoreninstanzen minimiert werden. Dadurch wird sichergestellt, dass beim Durchsuchen des Systems von verschiedenen Standorten weniger Bytes heruntergeladen werden müssen. Um diese Änderung vorzunehmen, legen Sie die Konfiguration in **HTML Library Manager** über die Felix-Konsole fest.

**Wann konfigurieren?**
Dies kann zur Laufzeit über die Felix-Konsole oder über die Code-Bereitstellung erfolgen.

**Ergebnis dieser Änderung**
Diese Änderung verbessert die Ladezeit von Seiten in der Autoreninstanz, da weniger Bytes zum Laden der Client-Bibliotheken übertragen werden.

## Konfigurieren gleichzeitiger Veröffentlichungs-Threads \(obligatorisch, je nach Anwendungsfall\)

**Was ist die Änderung?**
Diese Änderung ist erforderlich, wenn Sie DITA-OT zum Veröffentlichen von Ausgaben verwenden und außerdem eine Reihe gleichzeitiger Veröffentlichungs-Threads definiert ist.

Standardmäßig setzt AEM Guides die Veröffentlichungs-Threads auf die Anzahl der CPUs+1. Es wird jedoch empfohlen, diesen Wert auf die Hälfte \(1/2\) oder ein Drittel \(1/3\) der Gesamtzahl der CPUs festzulegen. Legen Sie dazu die Eigenschaft **Pool-Größe** unter der `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` gemäß den Empfehlungen fest.

**Wann konfigurieren?**
Dies kann zur Laufzeit über die Felix-Konsole oder über die Code-Bereitstellung erfolgen.

**Ergebnis dieser Änderung**
Durch diese Änderung wird sichergestellt, dass auf einer laufenden Autoreninstanz nicht alle Ressourcen für die Veröffentlichungsvorgänge zugewiesen werden. Dadurch bleiben die Systemressourcen auch für Autoren verfügbar, was zu einem besseren Benutzererlebnis führt.

## Konfigurieren der Batch-Größe von Knoten für die Erstellung von AEM-Site-Ausgaben \(obligatorisch, je nach Anwendungsfall\)

**Was ist die Änderung?**
Diese Änderung ist erforderlich, wenn Sie eine AEM Sites-Ausgabe generieren.

Legen Sie **Eigenschaft &quot;AEM-Site-Seiten in Heap** unter &quot;`com.adobe.fmdita.config.ConfigManager`&quot; auf eine Zahl fest, die auf der Konfiguration Ihres Systems basiert. Diese Eigenschaft definiert die Batch-Größe von Knoten, für die ein Commit ausgeführt werden soll, wenn die Site-Seiten generiert werden. Auf einem System mit einer größeren Anzahl von CPUs und Heap-Größe können Sie beispielsweise den Standardwert von `500` auf eine größere Anzahl erhöhen. Sie müssen den Testlauf mit dem geänderten Wert durchführen, um einen optimalen Wert für diese Eigenschaft zu erhalten.

**Wann konfigurieren?**
Dies kann zur Laufzeit über die Felix-Konsole oder über die Code-Bereitstellung erfolgen.

**Ergebnis dieser Änderung**
Eine erhöhte Anzahl der Eigenschaft **AEM-Site-Seiten in Heap begrenzen** optimiert den Prozess der Erstellung von AEM-Site-Ausgaben.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Herunterladen und installieren](download-install.md)
