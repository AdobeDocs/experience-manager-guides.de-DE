---
title: Architektur und Leistung des Cloud-Publishing-Microservices
description: Erfahren Sie, wie der neue Microservice skalierbare Veröffentlichungen in AEMaaCS ermöglicht.
exl-id: 948fce3f-b989-48f0-9a85-e921717e2986
feature: Microservice in AEM Guides
role: User, Admin
TQID: https://experienceleague.adobe.com/dXRfQ3DBW-1l-4hy5H0yowfXntJ3jcLU5bHvkquJBOY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b455a250-64c4-4598-b015-7b6b6dc528b1
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 753
ht-degree: 0%

---

# Cloud Publishing Microservice-Architektur und Leistungsanalyse

In diesem Artikel werden die Einblicke in die Architektur und die Leistungszahlen des neuen Cloud Publishing-Microservices vorgestellt.

>[!NOTE]
>
> Die auf Microservices basierende Veröffentlichung in AEM Guides unterstützt PDF (sowohl native als auch DITA-OT-basierte), AEM Site (Verwendung der Zuordnung zusammengesetzter Komponenten), HTML5, JSON und benutzerdefinierte Typen von Ausgabevorgaben.

## Probleme mit vorhandenen Veröffentlichungs-Workflows in der Cloud

DITA-Publishing ist ein ressourcenintensiver Prozess, der hauptsächlich vom verfügbaren Systemspeicher und CPU abhängt. Der Bedarf an diesen Ressourcen steigt weiter, wenn Publisher große Karten mit vielen Themen veröffentlichen oder wenn mehrere parallele Veröffentlichungsanfragen ausgelöst werden.

Wenn Sie den neuen Service nicht verwenden, erfolgt die gesamte Veröffentlichung auf demselben Kubernetes(k8)-Pod, auf dem auch der AEM-Cloud-Server ausgeführt wird. Ein typischer K8-Pod hat eine Begrenzung für den Arbeitsspeicher und die CPU, die er verwenden kann. Wenn AEM Guides-Benutzende große oder parallele Arbeitslasten veröffentlichen, kann diese Grenze schnell überschritten werden. K8 startet Pods neu, die versuchen, mehr Ressourcen als das konfigurierte Limit zu verwenden, was schwerwiegende Auswirkungen auf die AEM-Cloud-Instanz selbst haben kann.

Diese Ressourcenbeschränkung war die Hauptmotivation, einen dedizierten Service zu entwickeln, der es uns ermöglicht, mehrere gleichzeitige und große Veröffentlichungs-Workloads in der Cloud auszuführen.

Weitere Informationen zu Veröffentlichungs-Workflows in der Cloud finden Sie unter [Häufig gestellte Fragen zu Veröffentlichungs-Workflows und Skalierbarkeit](/help/product-guide/user-guide/publishing-scalability-faq.md).

## Einführung in die neue Architektur

Der Service verwendet die hochmodernen Cloud-Lösungen von Adobe wie App Builder, IO Eventing und IMS, um ein Server-loses Angebot zu erstellen. Diese Dienste basieren selbst auf den weithin akzeptierten Industriestandards wie Kubernetes und Docker.

Jede Anfrage an den neuen Veröffentlichungs-Microservice wird in einem isolierten Docker-Container ausgeführt, der jeweils nur eine Veröffentlichungsanfrage ausführt. Es werden automatisch mehrere neue Container erstellt, falls neue Veröffentlichungsanfragen eingehen. Dieser einzelne Container pro Anforderungskonfiguration ermöglicht es dem Microservice, den Kunden die beste Leistung zu bieten, ohne Sicherheitsrisiken einzugehen. Diese Container werden verworfen, sobald die Veröffentlichung abgeschlossen ist, wodurch nicht verwendete Ressourcen freigegeben werden.

Alle diese Kommunikationen werden durch Adobe IMS mithilfe von JWT-basierter Authentifizierung und Autorisierung gesichert und über HTTPS ausgeführt.

<img src="assets/architecture.png" alt="Registerkarte Projekte" width="600">

>[!NOTE]
>
> Der Veröffentlichungsprozess führt einige inhaltsabhängige Teile der Anfrage auf dem AEM-Server selbst aus, z. B. die Erstellung einer Abhängigkeitsliste. Die umfassendsten Teile des Publishing-Prozesses wie die Ausführung von DITA-OT oder die native Engine wurden jedoch auf den neuen Service abgeladen.


## Leistungsanalyse

Dieser Abschnitt zeigt die Leistungsnummern des Microservices. Er vergleicht die Leistung des Microservices mit dem On-Premise-Angebot von AEM Guides, da die alte Cloud-Architektur Probleme bei der gleichzeitigen Veröffentlichung oder der Veröffentlichung sehr großer Karten hatte.

Wenn Sie eine große Karte On-Premise veröffentlichen, müssen Sie möglicherweise die Java-Heap-Parameter anpassen, da sonst Fehler wegen zu wenig Arbeitsspeicher auftreten können. In der Cloud ist der Microservice bereits profiliert und verfügt standardmäßig über optimalen Java-Heap und andere Konfigurationen.

### Ausführen einer Veröffentlichungsinstanz in der Cloud im Vergleich zu On-Premise

* Cloud

  Wenn Sie eine einzelne Veröffentlichung in der Cloud mit dem neuen Service ausführen, kann die Veröffentlichung im Vergleich zur einzigen On-Premise-Veröffentlichung etwas mehr Zeit in Anspruch nehmen. Diese leicht erhöhte Zeit ist auf die verteilte Natur der neuen Cloud-Architektur zurückzuführen.

  <img src="assets/cloud_single_publish.png" alt="Registerkarte Projekte" width="600">

* On-Premise

  Die Ergebnisse der einzelnen Veröffentlichungen sind in der alten Cloud-Architektur oder On-Premise besser, da die vollständige Veröffentlichung auf demselben Pod/Computer erfolgt, auf dem AEM ausgeführt wird.

  <img src="assets/onprem_single_publish.png" alt="Registerkarte Projekte" width="600">

### Ausführen mehrerer Veröffentlichungen in der Cloud im Vergleich zu On-Premise

* Cloud

  In diesem Szenario glänzt der neue Veröffentlichungs-Microservice. Wie Sie in der folgenden Abbildung sehen können, ist Cloud in der Lage, mehrere gleichzeitige Veröffentlichungsaufträge zu veröffentlichen, ohne dass die Veröffentlichungszeit erheblich verlängert wird.

  <img src="assets/cloud_bulk_publish.png" alt="Registerkarte Projekte" width="600">

* On-Premise

  Das gleichzeitige Veröffentlichen auf einem On-Premise-Server führt zu einer erheblichen Leistungsbeeinträchtigung. Dieser Leistungsabfall ist schwerwiegender, wenn Herausgeber noch mehr Karten gleichzeitig veröffentlichen.

  <img src="assets/onprem_bulk_publish.png" alt="Registerkarte Projekte" width="600">

## Zusätzliche Vorteile

Ein Teil jeder Veröffentlichungsanfrage muss auf der AEM-Instanz ausgeführt werden, um den richtigen Veröffentlichungsinhalt abzurufen, der an den Microservice gesendet werden soll. Die neue Cloud-Architektur verwendet AEM-Aufträge anstelle von AEM-Workflows, wie es in der alten Architektur der Fall war. Diese Änderung ermöglicht es AEM Guides-Administratoren, die Einstellungen für die Cloud-Publishing-Warteschlange individuell zu konfigurieren, ohne dass andere AEM-Aufträge oder Workflow-Konfigurationen betroffen sind.

Details zum Konfigurieren des neuen Veröffentlichungs-Microservice finden Sie hier: [Konfigurieren des Microservice](configure-microservices.md)
