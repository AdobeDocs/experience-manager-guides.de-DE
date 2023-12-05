---
title: Architektur und Leistung von Cloud Publishing Microservice
description: Erfahren Sie, wie der neue Microservice eine skalierbare Veröffentlichung auf AEMaaCS ermöglicht.
exl-id: 948fce3f-b989-48f0-9a85-e921717e2986
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%

---

# Architektur und Leistungsanalyse von Cloud Publishing Microservice

Dieser Artikel gibt einen Überblick über die Architektur und Leistungszahlen des neuen Cloud Publishing-Microservice.

>[!NOTE]
>
> Die mikrodienstbasierte Veröffentlichung in AEM Guides unterstützt die Typen von PDF (nativ und DITA-OT-basiert), HTML5, JSON und benutzerdefinierten Ausgabevorgaben.

## Probleme mit vorhandenen Veröffentlichungs-Workflows in der Cloud

DITA Publishing ist ein ressourcenintensiver Prozess, der hauptsächlich von verfügbarem Systemspeicher und CPU abhängig ist. Der Bedarf an diesen Ressourcen steigt weiter, wenn Herausgeber große Maps mit vielen Themen veröffentlichen oder wenn mehrere parallele Veröffentlichungsanforderungen ausgelöst werden.

Wenn Sie den neuen Dienst nicht verwenden, erfolgt die gesamte Veröffentlichung auf demselben Kubernetes(k8)-Pod, auf dem auch der AEM Cloud-Server ausgeführt wird. Ein typischer k8-Pod hat eine Beschränkung auf die Menge an Arbeitsspeicher und CPU, die er verwenden kann. Wenn Benutzer von AEM Guides große oder parallele Arbeitslasten veröffentlichen, kann diese Beschränkung schnell überwunden werden. K8 startet Pods neu, die versuchen, mehr Ressourcen als das konfigurierte Limit zu verwenden, was sich ernsthaft auf die AEM Cloud-Instanz selbst auswirken kann.

Diese Ressourcenbegrenzung war die Hauptmotivation, einen dedizierten Dienst einzurichten, der es uns ermöglicht, mehrere gleichzeitige und große Veröffentlichungsarbeitslasten in der Cloud auszuführen.

## Einführung in die neue Architektur

Der Dienst verwendet Adobe-Edge-Cloud-Lösungen wie App Builder, IO Eventing und IMS, um ein Server-loses Angebot zu erstellen. Diese Dienstleistungen basieren selbst auf den allgemein anerkannten Industriestandards wie Kubernetes und Docker.

Jede Anfrage an den neuen Veröffentlichungs-Microservice wird in einem isolierten Docker-Container ausgeführt, der jeweils nur eine Veröffentlichungsanforderung ausführt. Wenn neue Veröffentlichungsanforderungen empfangen werden, werden automatisch mehrere neue Container erstellt. Diese einzelne Container-Konfiguration pro Anfrage ermöglicht es dem Microservice, die beste Leistung für die Kunden bereitzustellen, ohne Sicherheitsrisiken einzuführen. Diese Container werden verworfen, sobald die Veröffentlichung beendet ist, sodass nicht verwendete Ressourcen frei werden.

Alle diese Nachrichten werden durch Adobe IMS mit JWT-basierter Authentifizierung und Autorisierung gesichert und über HTTPS ausgeführt.

<img src="assets/architecture.png" alt="Projekt-Tab" width="600">

>[!NOTE]
>
> Durch den Veröffentlichungsprozess werden einige inhaltsabhängige Teile der Anforderung auf dem AEM-Server selbst ausgeführt, z. B. die Erstellung von Abhängigkeitslisten. Die umfangreichsten Teile des Veröffentlichungsprozesses, wie z. B. die Ausführung von DITA-OT oder der nativen Engine, wurden jedoch in den neuen Dienst abgeladen.


## Leistungsanalyse

In diesem Abschnitt werden die Leistungszahlen des Microservice vorgestellt. Er vergleicht die Leistung des Microservice mit dem On-Premise-Angebot AEM Guides, da die alte Cloud-Architektur Probleme bei gleichzeitiger Veröffentlichung oder der Veröffentlichung sehr großer Karten hatte.

Wenn Sie eine große Karte in On-Premise veröffentlichen, müssen Sie möglicherweise die Java-Heap-Parameter anpassen, da andernfalls Fehler wegen zu wenig Arbeitsspeicher auftreten können. In der Cloud ist der Microservice bereits profiliert und verfügt standardmäßig über optimale Java-Heap- und andere Konfigurationen.

### Ausführen einer Veröffentlichung in Cloud im Vergleich zu On-Premise

* Cloud

  Wenn Sie mit dem neuen Dienst eine einzelne Veröffentlichung in Cloud ausführen, kann die Veröffentlichung im Vergleich zur einmaligen On-Premise-Veröffentlichung etwas länger dauern. Diese leichte Zeiterhöhung ist auf die verteilte Natur der neuen Cloud-Architektur zurückzuführen.

  <img src="assets/cloud_single_publish.png" alt="Projekt-Tab" width="600">

* On-Premise

  Die Ergebnisse der Veröffentlichung mit einer einzigen Veröffentlichung sind in der alten Cloud-Architektur oder On-Premise besser, da die vollständige Veröffentlichung auf demselben Pod/Computer erfolgt, auf dem AEM ausgeführt wird.

  <img src="assets/onprem_single_publish.png" alt="Projekt-Tab" width="600">

### Mehrere Veröffentlichungen in Cloud und On-Premise durchführen

* Cloud

  Der neue Publishing-Microservice scheint in diesem Szenario. Wie Sie aus dem unten stehenden Bild sehen können, kann die Cloud mit der Zunahme an mehreren gleichzeitigen Veröffentlichungsaufträgen diese veröffentlichen, ohne dass die Veröffentlichungszeit erheblich verlängert wird.

  <img src="assets/cloud_bulk_publish.png" alt="Projekt-Tab" width="600">

* On-Premise

  Die gleichzeitige Veröffentlichung auf einem On-Premise-Server führt zu einer erheblichen Leistungsbeeinträchtigung. Dieser Leistungsabfall ist schlimmer, wenn Herausgeber noch mehr Karten gleichzeitig veröffentlichen.

  <img src="assets/onprem_bulk_publish.png" alt="Projekt-Tab" width="600">

## Zusätzliche Vorteile

Ein Teil jeder Veröffentlichungsanforderung muss auf der AEM ausgeführt werden, um den richtigen Veröffentlichungsinhalt abzurufen, der an den Microservice gesendet werden soll. Die neue Cloud-Architektur verwendet AEM Aufträge anstelle AEM Workflows, wie es in der alten Architektur der Fall war. Diese Änderung ermöglicht es AEM Guides-Administratoren, Cloud-Publishing-Warteschlangeneinstellungen individuell zu konfigurieren, ohne andere AEM Aufträge oder Workflow-Konfigurationen zu beeinträchtigen.

Details zur Konfiguration des neuen Veröffentlichungs-Microservice finden Sie hier: [Konfigurieren von Microservice](configure-microservices.md)
