---
title: REST-API zum Registrieren eines Datenquellen-Connectors
description: Erfahren Sie mehr über die REST-API zum Registrieren eines Datenquellen-Connectors
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 7%

---

# REST-API zum Registrieren eines Datenquellen-Connectors {#id236LG0Y0CXA}

Mit der folgenden REST-API können Sie einen Datenquellen-Connector registrieren.

## Registrieren eines Datenquellen-Connectors

Eine GET-Methode, die einen Datenquellen-Connector registriert.

**Anfrage-URL**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `path` | Zeichenfolge | Ja | Eine Zeichenfolge, die auf einen Pfad im AEM-Repository verweist. Es kann sich um einen Pfad im `/content/dam or /var/dxml` handeln. |

**Beispiel**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
