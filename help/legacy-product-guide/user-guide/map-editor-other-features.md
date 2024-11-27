---
title: Weitere Funktionen im Map-Editor
description: Entdecken Sie einige gängige Funktionen im Basic- und Advanced Map Editor. Erfahren Sie, wie Sie wichtige Verweise im Map-Editor auflösen.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Weitere Funktionen im Map-Editor {#id1942D0T0HUI}

Einige allgemeine Funktionen im Basic- und Advanced Map Editor sind:

## Schlüsselverweise auflösen {#id176GD01H05Z}

Ein DITA-Inhaltsschlüsselverweis oder `conkeyref` ist ein Mechanismus zum Einfügen eines Inhaltsteils von einem Thema in ein anderes. Dieser Mechanismus verwendet den Schlüssel zum Auffinden des wiederzuverwendenden Inhalts anstelle des Mechanismus für die direkte Inhaltsreferenz. Weitere Informationen zu direkten und indirekten Verweisen in DITA finden Sie unter *DITA-Adressierung* in der OASIS DITA-Sprachspezifikation.

Wenn das DITA-Thema mit Schlüsselverweisen verknüpft ist, müssen diese vor der Vorschau, Bearbeitung oder Überprüfung eines Themas aufgelöst werden.

Die Schlüsselreferenzen werden auf der Grundlage der in der folgenden Prioritätsreihenfolge festgelegten Stammzuordnung aufgelöst:

1. Benutzereinstellungen
1. Bedienfeld &quot;Landkartenansicht&quot;
1. Ordnerprofil

Die in den Benutzereinstellungen ausgewählte Stammzuordnung hat die höchste Priorität, um Schlüsselverweise aufzulösen, gefolgt vom Bedienfeld Kartenansicht und der Stammzuordnung des Ordnerprofils. Wenn also in den Benutzereinstellungen keine Zuordnung festgelegt ist, wird die im Bedienfeld Kartenansicht geöffnete Karte verwendet. Wenn keine Zuordnung im Bereich &quot;Map View&quot;geöffnet ist, wird die in den Ordnerprofilen festgelegte Zuordnung verwendet, um die Schlüsselverweise aufzulösen.

Die Schlüsselreferenzen können in einer DITA-Map-Datei oder einer separaten DITA-Datei gespeichert werden. In AEM Guides können Sie Schlüsselreferenzen entweder auf Projekt- oder Sitzungsebene angeben. Wenn bereits eine Stammzuordnung für die Benutzersitzung definiert ist, wird sie zum Auflösen der Schlüssel verwendet. Andernfalls wird die standardmäßige Stammzuordnung für diesen Ordner verwendet. Wenn keine standardmäßige Stammzuordnung konfiguriert ist, werden die fehlenden Schlüsselverweise für den Benutzer hervorgehoben.

Es gibt mehrere Möglichkeiten, wichtige Verweise in einem DITA-Thema zu beheben, indem die DITA-Zuordnung definiert wird, die an den folgenden Stellen verwendet werden soll:

**Projekteigenschaften** - Sie können eine Stammzuordnung zum Auflösen von Schlüsselverweisen beim Erstellen eines Projekts im Abschnitt &quot;Projekteigenschaften&quot;definieren.

Diese Stammzuordnung gilt für alle Assets \(Ordner und Unterordner\), die mit diesem Projekt verknüpft sind. Für Inhalte, die in mehreren Projekten referenziert werden, wird eine alphabetische Liste von Projekten verwaltet und die Standardstammkarte, die dem ersten Projekt zugeordnet ist, wird verwendet. Sie können auch die DITA-Zuordnung auswählen, die in der Liste zum Auflösen von Schlüsselverweisen verwendet werden soll.

**Themenvorschau** - Klicken Sie im Themenvorschaumodus in der Symbolleiste auf das Symbol Schlüsselauflösung und wählen Sie die DITA-Datei aus, die für Schlüsselverweise verwendet werden soll.

**Ansicht zur Themenbearbeitung** - Klicken Sie beim Bearbeiten eines DITA-Themas auf das Symbol Schlüsselauflösung und wählen Sie die DITA-Datei aus, die zum Auflösen der Schlüsselverweise verwendet werden soll.

**Übergeordnetes Thema:**[ Arbeiten mit dem Map-Editor](map-editor.md)
