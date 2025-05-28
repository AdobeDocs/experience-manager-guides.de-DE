---
title: Verstehen der Sitzungs-Timeouts in Experience Manager Guides
description: Erfahren Sie mehr über Sitzungs-Timeouts in Experience Manager Guides.
feature: Authoring, Publishing
role: User
source-git-commit: a6e015817bc9a964e3ca6a83c50089e7fabcdd94
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Warum meldet mich Experience Manager Guides nach einer bestimmten Zeit ab?

Experience Manager Guides beendet eine Benutzersitzung nach einer definierten Zeit der Inaktivität (Leerlauf-Timeout). Diese Funktion zum automatischen Abmelden ist in der Adobe Experience Manager konfiguriert. Wenn die Sitzung abgelaufen ist, wird ein Popup-Warnhinweis angezeigt, um Benutzende über die abgelaufene Sitzung zu informieren. Dieser Warnhinweis verhindert, dass Benutzende weitere Änderungen am Inhalt vornehmen.

**Wie funktioniert das Sitzungs-Timeout?**

Experience Manager Guides sendet alle 30 Sekunden eine Hintergrundanfrage `token.json`, um die Sitzung zu validieren. Wenn die Sitzung noch aktiv ist, wird ein gültiges Token zurückgegeben. Wenn die Sitzung aufgrund von Inaktivität abgelaufen ist, wird ein leeres Token zurückgegeben und die Sitzung wird als inaktiv betrachtet.

**Was passiert, wenn die Sitzung abläuft?**

Wenn eine inaktive Sitzung erkannt wird:

- Es wird ein Popup-Warnhinweis angezeigt, der Sie darüber informiert, dass Sie abgemeldet wurden.

  ![](images/sign-out-prompt.png)

- Der Warnhinweis deaktiviert alle Interaktionen mit der Anwendung.

- Durch Klicken auf **OK** wird der Browser aktualisiert und Sie werden zur Anmeldeseite weitergeleitet.
- Nach der Anmeldung werden Sie zur zuletzt geöffneten Seite von Experience Manager Guides weitergeleitet.

**Nächste Schritte**

Der Warnhinweis zum Sitzungsablauf verhindert Datenverlust, indem er die Möglichkeit bietet, während einer inaktiven Sitzung Änderungen am Programm vorzunehmen. Um versehentlichen Verlust von Inhalten zu vermeiden, wird empfohlen, Ihre Arbeit regelmäßig im Editor zu speichern, insbesondere bevor Sie Ihr System für einen längeren Zeitraum verlassen.





