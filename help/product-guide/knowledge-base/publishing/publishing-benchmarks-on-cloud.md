---
title: Anleitungen zur Veröffentlichung von Benchmarks auf AEMaaCS
description: Machen Sie sich mit den Systembeschränkungen bei der Veröffentlichung in AEM Cloud vertraut.
exl-id: 2cb4dfa4-dafc-409a-8d29-dbb00fabeae5
feature: Publishing
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 8%

---

# AEM Guides Publishing Benchmarks auf AEMaaCS

Der AEM Guides-Cloud-Service hat derzeit einige Einschränkungen hinsichtlich der Größe von Veröffentlichungskarten, die das Guides-Team aktiv lösen möchte.

Das Guides-Team hat einen skalierbaren Publishing-Microservice eingeführt, um große Karten und mehrere gleichzeitige Veröffentlichungen zu unterstützen. Weitere Informationen zum neuen Veröffentlichungs-Microservice finden Sie unter [Architektur des Veröffentlichungs-Microservice](publish-microservice-architecture-and-performance.md)

Informationen zum Konfigurieren des neuen Veröffentlichungsdienstes für eine AEM Cloud-Umgebung finden Sie unter [Konfigurieren einer neuen mikrodienstbasierten Veröffentlichung](configure-microservices.md) .


## Ausführungsumgebung

    AEM Version: 2023.5.11983.20230511T173830Z
    Anleitung Add On Release: 2023.6.0
    AEM Site Template: AEM Guides OTB template
    DITA-OT version: 3.5 4.4
    Publish-Workflow-Typ: Aufspaltung des Publish-Workflows
    Vom Microservice unterstützte Ausgabe: Native PDF, PDF (Dita-OT)

## Generierungsnummern der Ausgabe

| Ausgabetyp | Zuordnungsgröße (Themenverweise) | Ausführungsdauer (in Sekunden) | Publishing-Microservice |
|---------------|------------------------------|----------------------------|-----------------------|
| AEM Site | 3500 | 5220 | Nein |
| Native PDF | 3500 | 780 | Ja |
| PDF (DITA-OT) | 11000 | 960 | Ja |
| HTML5 | 3500 | 240 | Nein |
| Benutzerdefiniert | 300 | 300 | Nein |

## Wichtige Hinweise

- AEM Site erstellt viele cq:Page -Knoten und reduziert sie, indem sie sie während der Generierungszeit einzeln rendert. Aus diesem Grund ist es ratsam, zu vermeiden, dass mehrere gleichzeitige AEM Site-Veröffentlichungen ausgeführt werden, da dies das System überlasten kann.
- AEM die Zeit der Site-Erstellung hängt von der verwendeten Vorlage ab. Die Ausführungszeit kann sich bei Verwendung komplexer Vorlagen erhöhen.
- Die Ausführungszeit der benutzerdefinierten Veröffentlichung ist für eine benutzerdefinierte Beispielausgabe vorgesehen. Die benutzerdefinierte Veröffentlichungszeit hängt ausschließlich von der eigenen Transformationslogik des Kunden ab.
