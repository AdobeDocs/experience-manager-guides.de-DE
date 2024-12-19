---
title: Weitere Funktionen in den Zuordnungs-Editoren
description: Entdecken Sie einige allgemeine Funktionen im Standard- und im erweiterten Zuordnungs-Editor. Erfahren Sie, wie Sie wichtige Verweise im Zuordnungs-Editor auflösen.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '467'
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

**Übergeordnetes Thema:**[ Arbeiten mit dem Zuordnungs-Editor](map-editor.md)
