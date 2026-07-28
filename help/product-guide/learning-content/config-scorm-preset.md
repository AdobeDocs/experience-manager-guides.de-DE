---
title: Konfiguration der SCORM-Voreinstellung
description: Erfahren Sie mehr über die verschiedenen SCORM-Vorgabenkonfigurationen im Abschnitt Produktschulung und -lernen
feature: Authoring
role: User
exl-id: b3000708-6120-4725-bea1-0b8e58048948
TQID: https://experienceleague.adobe.com/9WSwgksrX0fahrniOalbizWFXCqcW0QlGAHn707vm-k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: dbb138a7804d102d1b9aa9cfbc3564e827ef199e
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 0%

---

# Konfigurieren der SCORM-Ausgabevorgabe

Nachdem die Voreinstellung erstellt wurde, konfigurieren Sie die SCORM-Voreinstellungen. Die voreingestellten Konfigurationsoptionen sind auf den Registerkarten Allgemein, Inhalt, Teilnehmererlebnis und Veröffentlichen organisiert.

- **Allgemein** Wird verwendet, um grundlegende Ausgabeeinstellungen wie die unterstützte Version, den Ausgabepfad, den SCORM-Dateinamen (zip), die Ausgabevorlage und den Nachgenerierungs-Workflow für eine neue Dropdown-Liste des Nachgenerierungs-Workflows anzugeben, die alle konfigurierten Workflows enthält.

  ![](assets/scorm-general-tab-v3.png){width="650"}


- **Inhalt:** Verwenden Sie diese Option, um die verfügbare bedingte Filterung (mithilfe von DITAVAL oder einer Bedingungsvorgabe) und den Variablensatz anzugeben.

  ![](assets/scorm-content-tab.png){width="650"}

- **Teilnehmererlebnis:** Auf der Registerkarte **Teilnehmererlebnis** können Sie konfigurieren, wie Teilnehmer mit der SCORM-Ausgabe interagieren und durch diese navigieren. Die Einstellungen sind unter **Allgemein**, **Navigation** und **Quiz** organisiert, sodass Sie die Barrierefreiheit von Inhalten, den Navigationsfluss und das Quizverhalten für ein maßgeschneidertes Lernerlebnis steuern können.

  ![](assets/learner-experience.png){width="650"}

  - **Allgemein** Konfigurieren Sie Optionen auf Ausgabeebene, z. B. das Aktivieren von PDF-Downloads für Teilnehmer.

    - **Erlauben Sie Lernenden das Herunterladen von Kurs-PDF**: Wenn diese Option aktiviert ist, wird der SCORM-Ausgabe ein PDF-Symbol hinzugefügt. Durch Klicken auf dieses Symbol können Teilnehmer eine PDF-Version des Kursinhalts direkt aus der veröffentlichten Ausgabe herunterladen.

      **Voraussetzungen:** Bevor Sie diese Option aktivieren, stellen Sie Folgendes sicher:

      - Die **Ausgabevorlage** muss mit dem Symbol **PDF einbetten** am gewünschten Speicherort konfiguriert werden und dieselbe Vorlage sollte unter der Option **Ausgabevorlage** auf der Registerkarte **Allgemein** beim Konfigurieren einer SCORM-Vorgabe ausgewählt werden.

        ![](assets/embed-pdf.png){width="650"}

      - Die zugehörige **native PDF-**) muss mindestens einmal generiert worden sein. Das Auswählen einer nicht generierten PDF-Vorgabe führt zu einem Fehler, der den Benutzer auffordert, die Vorgabe zu veröffentlichen.

    Sobald die SCORM-Ausgabe mit den oben genannten Einstellungen generiert wurde, enthält die resultierende Ausgabe ein PDF-Symbol, wie unten dargestellt, sodass die Lernenden den Kurs &quot;PDF&quot; herunterladen können.

    ![](assets/pdf-icon.png){width="650"}

  - **Navigation:** Definieren Sie, wie Teilnehmer sich durch den Kurs bewegen, einschließlich des sequenziellen Fortschritts, obligatorischer Abschlussbedingungen und Regeln zum Entsperren der Schaltfläche **Weiter**.

    - **Die Teilnehmer müssen die Inhalte in einer bestimmten Reihenfolge durchlaufen**: Stellt sicher, dass die Teilnehmer den Kurs in einer festen Reihenfolge durchlaufen und nicht springen oder zwischen den Kurskomponenten springen können.
    - **Nächste Schaltfläche deaktivieren, wenn der Teilnehmer das Quiz nicht besteht**: Blockiert den Teilnehmer, zum nächsten Abschnitt/zur nächsten Seite zu wechseln, bis er das Quiz besteht.
    - **Teilnehmer müssen jede Frage ausprobieren, um fortzufahren**: Erfordert, dass Teilnehmer alle Fragen ausprobieren, bevor sie das Quiz senden können, um unvollständige Übermittlungen zu verhindern.
    - **Fortschritt bis zum Abschluss sperren**: Verhindert die Navigation durch den Kurs, bis alle konfigurierten Unterbedingungen darunter erfüllt sind, indem die Schaltfläche **Weiter** im Kurs deaktiviert wird.
      - **Alle interaktiven Elemente geöffnet**: Erfordert, dass der Teilnehmer jedes interaktive Element auf der Seite öffnet.
      - **Alle Medien angesehen**: Erfordert, dass der Teilnehmer alle Video-/Audiomedien auf der Seite ansieht.
      - **Alle Wissensüberprüfungen versucht**: Erfordert, dass der Teilnehmer jede Wissensüberprüfungsfrage auf der Seite ausprobiert.
      - **Mindestbesuchszeit pro Seite**: Erfordert, dass der Teilnehmer mindestens für die angegebene Dauer auf der Seite bleibt, bevor die Schaltfläche Weiter aktiviert wird. Nach der Aktivierung müssen Sie die erforderliche Zeit wie unten beschrieben eingeben.
        - **Erforderliche Zeit (Sekunden)**: Die Mindestanzahl von Sekunden (z. B. `30`), die ein Teilnehmer auf der Seite bleiben muss, damit diese Bedingung erfüllt wird.

  - **Quiz:** Quizverhalten, wie das Zuordnen der Fragenreihenfolge und der Antwortoptionen, um die Vorhersehbarkeit von Versuchen zu verringern.

    - **Fragereihenfolge für jeden Versuch zufälligen**: Zeigt Quizfragen für jeden Versuch in einer anderen Reihenfolge an, wodurch die Vorhersehbarkeit verringert wird.
    - **Auswahl der Antworten für jeden Versuch zufälligen**: Mischt die Antwortoptionen für jede Frage bei jedem Versuch, wodurch die Wahrscheinlichkeit des Ratens verringert wird.

- **In LMS veröffentlichen:** Verwenden Sie diese Einstellung, um Ihre Inhalte direkt in Adobe Learning Manager (ALM) zu veröffentlichen. Wählen Sie im Dropdown-Menü **Veröffentlichungsserver** die Option **Adobe Learning Manager** und wählen Sie dann das erforderliche **Veröffentlichungsprofil**, das zuvor in den Workspace-Einstellungen konfiguriert wurde. Das ausgewählte Profil wird verwendet, um die Verbindung herzustellen und den generierten Inhalt in ALM hochzuladen.

  >[!NOTE]
  >
  > Bevor Sie Inhalte in AEM veröffentlichen, müssen Sie ein Adobe Learning Manager-Veröffentlichungsprofil konfigurieren. Weitere Informationen finden Sie unter [Profile veröffentlichen](../lc-config-guide/lc-folder-profile.md).

  ![](assets/scorm-publish-lms.png){width="650"}

Nachdem alle Änderungen konfiguriert wurden, speichern Sie die Änderungen für die SCORM-Vorgabe mit **Speichern** in der rechten Ecke der Symbolleiste der Seite „SCORM-Vorgabe“.
