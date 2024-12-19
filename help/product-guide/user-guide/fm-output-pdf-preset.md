---
title: PDF
description: Generieren und Konfigurieren der PDF-Ausgabe für FrameMaker-Dokumente in AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
feature: Publishing FrameMaker Documents
role: User
source-git-commit: 462647f953895f1976af5383124129c3ee869fe9
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# PDF {#id205BB0T20RH}

Folgende Optionen stehen für die PDF-Ausgabe zur Verfügung:

>[!NOTE]
>
> Klicken Sie zum Öffnen der Ausgabevorgaben für das PDF auf eine FrameMaker \(`.fm` oder `.book`\)-Datei, klicken Sie dann auf „Ausgabevorgaben“, und klicken Sie dann auf die Option &quot;PDF-Ausgabe“.

| PDF-Optionen | Beschreibung |
|-----------|-----------|
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um die PDF-Ausgabe zu generieren, wählen Sie die Option PDF aus. |
| Einstellungsname | Geben Sie einen beschreibenden Namen für die PDF-Ausgabeeinstellungen an, die Sie erstellen. Sie können beispielsweise &quot;*Kundenausgabe“* „Endbenutzerausgabe *angeben*. |
| **Auftragseinstellungen** |
| Optionen | Wählen Sie die PDF-Vorgabe aus, die Sie zum Generieren der PDF-Ausgabe verwenden möchten. |
| Generieren eines getaggten PDF | Wählen Sie diese Option aus, um mit Tags versehene PDF zu generieren, die Informationen über Inhalt und Struktur des Dokuments enthalten. Diese Informationen werden von den Bildschirmlesehilfen verwendet. |
| Generieren von PDF für jede Datei im Buch | Wenn Sie eine Ausgabe für eine Buchdatei erzeugen, wählen Sie diese Option, um für jede Datei im Buch eine separate PDF zu erzeugen. |
| PDF nur zur Überprüfung generieren | Wählen Sie diese Option, um PDF mit aktivierter Kommentarfunktion zu generieren. |
| Spezifisches Ziel für alle Elemente und Absätze erstellen | Wählen Sie diese Option aus, um benannte Ziele auf der Grundlage von Elementen und Absätzen zu erstellen. |
| **Anzeigeeinstellungen** |
| Dokument auf Seite öffnen | Geben Sie die Seitennummer an, die beim Öffnen der PDF angezeigt werden soll. |
| Anfänglicher Zoom-Faktor | Wählen Sie den Zoom-Faktor für das Dokument aus. |
| Eintragungszeichen | Um ein Dokument mit Schnittmarken und Registrierungsmarken zu drucken, wählen Sie eine Option aus der Dropdown-Liste Registrierungsmarken aus. |
| Seitenbreite und Seitenhöhe | Geben Sie die Breite und Höhe der Seite an. |
| Seitenbereich | Wählen Sie aus, ob Sie alle Seiten des Buches oder mehrere Seiten veröffentlichen möchten. Wenn Sie „Bereich“ auswählen, müssen Sie den Seitenbereich „Von“ und „Bis“ angeben. |
| CYMK in RGB konvertieren | Wählen Sie diese Option, um die CYMK-Farben in der generierten PDF in RGB zu konvertieren. |
| PDF-Lesezeichen erzeugen | Erstellen Sie eine barrierefreie PDF mit Lesezeichen. |
| Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die PDF-Ausgabe gespeichert wird. |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten. |

**Übergeordnetes Thema:**[ Ausgabe von FrameMaker-Dokumenten generieren](fm-output-generatation.md)
