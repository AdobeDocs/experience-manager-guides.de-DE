---
title: Handbücher zur Veröffentlichung von Benchmarks in AEMaaCS
description: Machen Sie sich mit den Systembeschränkungen für die Veröffentlichung in der AEM Cloud vertraut.
exl-id: 2cb4dfa4-dafc-409a-8d29-dbb00fabeae5
feature: Publishing
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 8%

---

# AEM Guides-Veröffentlichungs-Benchmarks in AEMaaCS

Derzeit hat AEM Guides Cloud Service einige Einschränkungen bei der Veröffentlichung von Zuordnungsgrößen, an deren Behebung das Guides-Team aktiv arbeitet.

Das Guides-Team hat einen skalierbaren Veröffentlichungs-Microservice eingeführt, um große Karten und mehrere gleichzeitige Veröffentlichungen zu unterstützen. Weitere Informationen zum neuen Veröffentlichungs-Microservice finden Sie unter [Veröffentlichungs-Microservice-Architektur](publish-microservice-architecture-and-performance.md)

Informationen zum Konfigurieren des neuen Veröffentlichungs-Services für eine beliebige AEM-Cloud-Umgebung finden Sie [Konfigurieren der neuen, auf Microservices basierenden Veröffentlichung](configure-microservices.md)


## Ausführungsumgebung

    AEM-Version: 2023.5.11983.20230511T173830Z
    Guide Add-on-Version: 2023.6.0
    AEM-Site-Vorlage: AEM Guides OOTB-Vorlage
    DITA-OT-Version: 3.5.4
    Publish-Workflow-Typ: Aufspaltung Publish-Workflow
    Ausgabe unterstützt von Microservice: Native PDF, PDF (DITA-OT)

## Ausgabegenerierungsnummern

| Ausgabetyp | Zuordnungsgröße (Themenreferenzen) | Ausführungszeit (in Sekunden) | Veröffentlichungs-Microservice |
|---------------|------------------------------|----------------------------|-----------------------|
| AEM-Site | 3500 | 5220 | Nein |
| Native PDF | 3500 | 780 | Ja |
| PDF (DITA-OUT) | 11000 | 960 | Ja |
| HTML5 | 3500 | 240 | Nein |
| Benutzerdefiniert | 300 | 300 | Nein |

## Wichtige Hinweise

- AEM Site erstellt viele cq:Page-Knoten und reduziert sie, indem sie während der Generierungszeit einzeln gerendert werden. Aus diesem Grund ist es ratsam, zu vermeiden, mehrere große gleichzeitige AEM-Site-Veröffentlichungen auszuführen, da dies das System überlasten kann.
- Die Generierungszeit der AEM-Site hängt von der verwendeten Vorlage ab. Die Ausführungszeit kann sich bei Verwendung einer komplexen Vorlage erhöhen.
- Die Ausführungszeit für benutzerdefinierte Veröffentlichungen wird für eine beispielhafte benutzerdefinierte Ausgabe festgelegt. Die Zeit der benutzerdefinierten Veröffentlichung hängt ausschließlich von der eigenen Transformationslogik des Kunden ab.
