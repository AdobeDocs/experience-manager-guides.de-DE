---
title: Verstehen der Sitzungs-Timeouts in Experience Manager Guides
description: Erfahren Sie mehr über Sitzungs-Timeouts in Experience Manager Guides.
feature: Authoring, Publishing
role: User
exl-id: f09b1215-4753-4dfd-89ef-1629257e5efe
TQID: https://experienceleague.adobe.com/nrxkVxSUooy2-08PaUp1pjiH8w2kBBNGC9efarvepbQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
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
