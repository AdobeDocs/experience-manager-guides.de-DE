---
title: Konfigurieren des KI-Assistenten im Agentenmodus
description: Erfahren Sie, wie Sie den Agenten-KI-Assistenten in Experience Manager Guides konfigurieren
source-git-commit: 5ed0a5191e1852dd65e0461f02d520b195f7cc39
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 2%
---

# Konfigurieren des KI-Assistenten im Agentenmodus für Cloud Service

Als Administrator können Sie den KI-Assistenten im Agentenmodus für Ihr Unternehmen in Experience Manager Guides konfigurieren. Die Konfigurationsschritte variieren je nachdem, ob die Unified Shell-Einstellung in Ihrer AEM as a Cloud Service-Umgebung aktiviert ist und ob die Benutzenden über SSO- oder Nicht-SSO-Authentifizierung angemeldet sind. In diesem Artikel wird der Konfigurationsprozess für jedes Szenario beschrieben.

## Voraussetzung

Ihr Unternehmen muss in die **CX Enterprise Coworker integriert werden** bevor Sie den KI-Assistenten im Agentenmodus konfigurieren.

## Konfigurieren des KI-Assistenten basierend auf Ihrer Umgebung

Verwenden Sie die folgende Tabelle, um zu ermitteln, welcher Konfigurationspfad für Ihre Benutzer gilt, und führen Sie dann die entsprechenden Schritte aus.

| Unified Shell | Anmeldetyp | Konfiguration erforderlich |
|---|---|---|
| Aktiviert | SSO | Keine zusätzliche Konfiguration. Alles funktioniert sofort |
| Aktiviert | Nicht-SSO | Hinzufügen der IMS-Konfiguration zur Umgebung |
| Deaktiviert | SSO | Hinzufügen der IMS-Konfiguration zur Umgebung |
| Deaktiviert | Nicht-SSO | Hinzufügen der IMS-Konfiguration zur Umgebung |

### Benutzende mit aktivierter Unified Shell

**SSO-Anmeldung**

Wenn Unified Shell aktiviert ist und sich Ihre Benutzer über SSO anmelden, ist keine zusätzliche Konfiguration erforderlich. Der KI-Assistent im Agentenmodus funktioniert automatisch, sobald Ihr Unternehmen in CX Enterprise Coworker integriert wurde.

**Nicht-SSO-Anmeldung**

Wenn Unified Shell aktiviert ist, Ihre Benutzer sich jedoch ohne SSO anmelden, müssen Sie [Hinzufügen der IMS-Konfiguration zur Umgebung](#add-ims-configuration-to-the-environment) unten angeben.

### Benutzer mit deaktivierter Unified Shell

Wenn Unified Shell deaktiviert ist, müssen Sie [IMS-Konfiguration zur Umgebung hinzufügen](#add-ims-configuration-to-the-environment) für beide:

- SSO-Anmeldung
- Nicht-SSO-Anmeldung

## Hinzufügen der IMS-Konfiguration zur Umgebung

Führen Sie die folgenden Schritte aus, um die IMS-Konfiguration zur Umgebung hinzuzufügen:

1. Öffnen Sie Experience Manager und wählen Sie dann Ihr Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.

2. Wechseln Sie zur Registerkarte **Umgebungen**.

3. Wählen Sie den Namen der Umgebung aus, die Sie konfigurieren möchten. Dadurch gelangen Sie zur Seite **Umgebungsinformationen**.

4. Wechseln Sie zur Registerkarte **Konfiguration** .

5. Fügen Sie die JSON-Service-Details (heruntergeladen, als Sie die IMS-Konfiguration in Adobe Developer Console erstellt haben) in das Feld **Wert** ein, das `SERVICE_ACCOUNT_DETAILS` entspricht. Stellen Sie sicher, dass Sie denselben Namen und dieselbe Konfiguration verwenden, die von der Umgebung erwartet werden.

>[!NOTE]
>Wenn Sie noch keine OAuth/IMS-Anmeldeinformationen für Ihre Umgebung erstellt haben, führen Sie diese zuerst in Adobe Developer Console aus, bevor Sie diesen Schritt abschließen.

![Konfiguration des IMS-Dienstkontos](assets/ims-service-account-config.png){width="800"}

## Aktivieren des Agenten-Modus

Nachdem die Konfiguration für Ihre Umgebung abgeschlossen ist, wenden Sie sich an das Customer Success-Team , um den Agentenmodus zu aktivieren.

Navigieren Sie bei für Ihre Umgebung aktiviertem Agentenmodus zu **Workspace-Einstellungen** und aktivieren Sie den Umschalter **Agent** auf der Registerkarte **Allgemein** im Abschnitt **KI-Assistent**.
