---
title: Weitere Funktionen in den Zuordnungs-Editoren
description: Entdecken Sie einige allgemeine Funktionen im Standard- und im erweiterten Zuordnungs-Editor. Erfahren Sie, wie Sie wichtige Verweise im Zuordnungs-Editor auflösen.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: d6e00884-e17c-499e-9568-0807a75051ad
TQID: https://experienceleague.adobe.com/tAzYI5Pxc6SkzgksjL3mFAQHY01YtejwTrU6vHW5vMc
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 467
ht-degree: 0%

---

# Weitere Funktionen in den Zuordnungs-Editoren {#id1942D0T0HUI}

Zu den gebräuchlichen Funktionen im Standard- und im erweiterten Zuordnungs-Editor gehören:

## Auflösen von Schlüsselverweisen {#id176GD01H05Z}

Ein DITA-Inhaltsschlüssel-Verweis (oder `conkeyref`) ist ein Mechanismus zum Einfügen eines Teils des Inhalts von einem Thema in ein anderes. Dieser Mechanismus verwendet den Schlüssel zum Auffinden des wiederzuverwendenden Inhalts und nicht den direkten Inhaltsverweismechanismus. Weitere Informationen zum direkten und indirekten Verweisen in DITA finden Sie unter *DITA-Adressierung* in der DITA-Sprachspezifikation von OASIS.

Wenn mit dem DITA-Thema Schlüsselverweise verknüpft sind, müssen diese aufgelöst werden, bevor ein Thema in der Vorschau angezeigt, bearbeitet oder überprüft werden kann.

Die Schlüsselverweise werden auf der Grundlage der Stammzuordnung aufgelöst, die in der folgenden Prioritätsreihenfolge festgelegt ist:

1. Benutzereinstellungen
1. Kartenansichtsbereich
1. Ordnerprofil

Die in den Benutzereinstellungen ausgewählte Stammzuordnung hat die höchste Priorität, um wichtige Verweise aufzulösen, gefolgt vom Bereich für die Zuordnungsansicht und der Stammzuordnung des Ordnerprofils. Wenn in den Benutzereinstellungen also keine Zuordnung festgelegt ist, wird die im Bereich „Kartenansicht“ geöffnete Zuordnung verwendet. Wenn im Bereich der Zuordnungsansicht keine Zuordnung geöffnet ist, wird der Zuordnungssatz im Ordner Profile verwendet, um die Schlüsselverweise aufzulösen.

Die Schlüsselverweise können in einer DITA-Map-Datei oder einer separaten DITA-Datei gespeichert werden. In AEM Guides können Sie wichtige Verweise entweder auf Projekt- oder Sitzungsebene angeben. Wenn für die Benutzersitzung bereits eine Stammzuordnung definiert ist, wird diese zur Auflösung der Schlüssel verwendet. Andernfalls wird die Standard-Stammzuordnung für diesen Ordner verwendet. Wenn keine standardmäßige Stammzuordnung konfiguriert ist, werden die fehlenden Schlüsselverweise für den Benutzer hervorgehoben.

Es gibt mehrere Möglichkeiten, wichtige Verweise in einem DITA-Thema aufzulösen, indem Sie die DITA-Zuordnung definieren, die an den folgenden Stellen verwendet werden soll:

**Projekteigenschaften** - Sie können im Abschnitt Projekteigenschaften eine Stammzuordnung definieren, in der die wichtigsten Verweise beim Erstellen eines Projekts aufgelöst werden.

Diese Stammzuordnung gilt für alle mit diesem Projekt verknüpften Assets \(Ordner und Unterordner\). Für Inhalte, auf die in mehreren Projekten verwiesen wird, wird eine alphabetische Liste der Projekte beibehalten und die standardmäßige Stammzuordnung, die mit dem ersten Projekt verknüpft ist, wird verwendet. Sie können auch die DITA-Map auswählen, die für die Auflösung von Schlüsselverweisen in der Liste verwendet werden soll.

**Themenvorschau** - Klicken Sie im Themenvorschau-Modus in der Symbolleiste auf das Symbol für die Tastenauflösung und wählen Sie die DITA-Datei aus, die für wichtige Verweise verwendet werden soll.

**Themenbearbeitungsansicht** - Klicken Sie beim Bearbeiten eines DITA-Themas auf das Symbol für die Schlüsselauflösung und wählen Sie die DITA-Datei aus, die für die Auflösung der Schlüsselverweise verwendet werden soll.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Arbeiten mit dem Zuordnungs-Editor](map-editor.md)
