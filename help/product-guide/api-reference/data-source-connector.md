---
title: REST-API zur Registrierung eines Datenquellen-Connectors
description: Erfahren Sie mehr über die REST-API zur Registrierung eines Datenquellen-Connectors.
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 0%

---

# REST-API zur Registrierung eines Datenquellen-Connectors {#id236LG0Y0CXA}

Mit der folgenden REST-API können Sie einen Datenquellen-Connector registrieren.

## Datenquellen-Connector registrieren

Eine GET, die einen Datenquellen-Connector registriert.

**Anforderungs-URL**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`path`|String|Ja|Ein String, der auf einen Pfad im AEM Repository verweist. Es kann sich um einen Pfad im `/content/dam or /var/dxml`| handeln.

**Beispiel**:\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
