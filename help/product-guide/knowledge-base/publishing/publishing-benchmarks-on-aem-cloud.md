---
title: Handbücher zur Veröffentlichung von Benchmarks in AEMaaCS
description: Machen Sie sich mit den Systembeschränkungen für die Veröffentlichung in der AEM Cloud vertraut.
feature: Publishing
role: User, Admin
source-git-commit: 6e2577f04f1092ec9d8445ddbb97aa34be1e53a4
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 21%

---

# AEM Guides-Veröffentlichungs-Benchmarks in AEMaaCS

Dieser Benchmark bewertet die Leistung der neuen Veröffentlichungs-APIs für verschiedene Ausgabevorgaben und die Steigerung der Zuordnungsgrößen in AEM Guides as a Cloud Service. Ziel ist es, das Skalierungsverhalten zu verstehen und Leistungsengpässe zu identifizieren.

Der Publishing-Service verwendet eine [Microservice-basierte Architektur](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) mit automatischer Skalierung, die die Handhabung größerer Workloads durch zusätzliche Pods ermöglicht.

## Ausführungsumgebung

- **AEM-Version**:2026.4.25322.20260407T085152Z
- **Guides-Add-on**: 2026.5.0
- **Ursprüngliche Pod-Anzahl**: 2 Pods
- **Verhalten bei automatischer Skalierung** Wird bei erhöhter Last auf bis zu 4 Pods über 4 Knoten skaliert
- **vCPUs**: 10
- **RAM pro Pod**: 8 GB
- **Gleichzeitige Benutzer**: 1 Benutzer

>[!NOTE]
>
> Im Mittelpunkt dieser Übung stand das Verhalten der Veröffentlichung bei zunehmender Zuordnungsgröße, wobei die Auswirkungen größerer Zuordnungen auf den Durchsatz, die Latenz und den gesamten Abschluss der Veröffentlichung unter Last hervorgehoben wurden.


## Ausgabegenerierungsnummern

**Native AEM-Site**

| MapSize | Ausführungszeit (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 62.378 | Ja |
| 100 | 64.27 | Ja |
| 1000 | 93.091 | Ja |
| 5000 | 496.319 | Ja |
| 10000 | 922.602 | Ja |

**Native PDF**

| MapSize | Ausführungszeit (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 62.302 | Ja |
| 100 | 62.431 | Ja |
| 1000 | 108.666 | Ja |
| 5000 | 201.379 | Ja |
| 10000 | 1170.689 | Ja |

**PDF**

| MapSize | Ausführungszeit (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 30.926 | Ja |
| 100 | 30.987 | Ja |
| 1000 | 77.007 | Ja |
| 5000 | 247.505 | Ja |
| 10000 | 686.61 | Ja |

**HTML**

| MapSize | Ausführungszeit (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10 | 30.844 | Ja |
| 100 | 30.834 | Ja |
| 1000 | 77.384 | Ja |
| 5000 | 170.237 | Ja |
| 10000 | 419.166 | Ja |


## Wichtigste Bemerkungen

- Die Zeit für die Erstellung der AEM-Site hängt von der verwendeten Vorlage ab. Die Ausführungszeit kann sich bei Verwendung einer komplexen Vorlage erhöhen.
- Die Ausführungszeit der benutzerdefinierten Veröffentlichung basiert auf einer benutzerdefinierten Beispielausgabe. Die Zeit der benutzerdefinierten Veröffentlichung hängt ausschließlich von der eigenen Transformationslogik des Kunden ab.