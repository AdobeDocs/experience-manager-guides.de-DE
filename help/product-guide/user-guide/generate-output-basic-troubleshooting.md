---
title: Allgemeine Fehlerbehebung
description: Beheben Sie Probleme mit der grundlegenden Fehlerbehebung in AEM Guides. Erfahren Sie, wie Sie die Protokolldatei in einem Texteditor anzeigen, kopieren und überprüfen und JSP-Kompilierungsfehler beheben können.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 0%

---

# Allgemeine Fehlerbehebung {#id1821I0Y0G0A}

Beim Arbeiten mit Adobe Experience Manager Guides können Fehler auftreten, während Sie Ihr Dokument veröffentlichen oder öffnen. Solche Fehler können in der DITA-Zuordnung, im Thema oder im Experience Manager Guides-Prozess selbst auftreten. Dieser Abschnitt enthält Informationen zum Zugriff auf und zum Analysieren von Informationen in der Protokolldatei für die Ausgabegenerierung. Wenn Ihr DITA-Thema zu groß ist, wird möglicherweise der JSP-Kompilierungsfehler angezeigt. Dieser Abschnitt enthält auch Informationen zum Beheben des JSP-Kompilierungsfehlers.

## Protokolldatei anzeigen und überprüfen {#id1822G0P0CHS}

Führen Sie die folgenden Schritte aus, um die Protokolldatei für die Ausgabegenerierung anzuzeigen und zu überprüfen:

1. Nachdem Sie den Prozess zur Ausgabe-Generierung initiiert haben, wählen Sie **Ausgaben** in der DITA-Zuordnungskonsole aus.

   Die Spalte **Allgemein** der **Generierte Ausgaben** zeigt die Symbole, die einen visuellen Hinweis auf den Erfolg oder Misserfolg der Ausgabegenerierung geben.

   ![](images/output-general-settings.png){width="300" align="left"}

   Im obigen Screenshot zeigen die Symbole 1 und 3 eine fehlgeschlagene Ausgabegenerierung. Das zweite Symbol zeigt eine erfolgreiche Ausgabegenerierung an, jedoch mit Meldungen. Die letzte Variante ist eine erfolgreiche Ausgabegenerierung ohne Meldung.

1. Wählen Sie nach Abschluss des Vorgangs den Link in **Spalte** Erstellt am“ aus.

   Die Protokolldatei wird auf einer neuen Registerkarte geöffnet.

   ![](images/log-file.png){align="left"}

1. Verwenden Sie die folgenden Filter, um den Text in der Protokolldatei hervorzuheben:
   - Schwerwiegend: Markiert schwerwiegende Fehler in der Protokolldatei in rosa.
   - Fehler: Markiert die Fehler in der Protokolldatei in orangefarbener Farbe.
   - Warnung: Markiert die Warnungen in der Protokolldatei in violetter Farbe.
   - Info: Hebt die Informationsmeldungen in der Protokolldatei mit blauer Farbe hervor.
   - Ausnahme: markiert die Ausnahmen in der Protokolldatei mit gelber Farbe.
1. Verwenden Sie die Navigationsschaltflächen nach oben und unten, um zum hervorgehobenen Text in der Protokolldatei zu springen.

   Alternativ können Sie durch die Protokolldatei scrollen und die Meldungen überprüfen.


## Kopieren und überprüfen Sie die Protokolldatei in einem Texteditor

Führen Sie die folgenden Schritte aus, um die Protokolldatei für die Ausgabegenerierung in einen Texteditor zu kopieren und zu überprüfen:

1. Nachdem Sie den Prozess zur Ausgabe-Generierung initiiert haben, wählen Sie **Ausgaben** in der DITA-Zuordnungskonsole aus.

1. Wählen Sie nach Abschluss des Vorgangs den Link in **Spalte** Erstellt am“ aus.

   Die Protokolldatei wird auf einer neuen Registerkarte geöffnet.

1. Klicken Sie **Schaltfläche „Protokoll**&quot;. Die Protokolldatei wird in die Zwischenablage kopiert.
1. Öffnen Sie einen Texteditor und fügen Sie die Protokolldatei in den Editor ein.

1. Scrollen Sie durch die Protokolldatei und suchen Sie nach Meldungen.

   Anhand der folgenden Informationen können Sie feststellen, ob im DITA-Datei- oder Experience Manager Guides-Prozess ein Fehler vorliegt:

   - *DITA-Zuordnungsdatei-bezogener Fehler*: Falls in der DITA-Zuordnungsdatei oder einer anderen in der DITA-Zuordnung enthaltenen Datei ein Fehler gefunden wird, enthält die Protokolldatei die Zeichenfolge „BUILD FAILED“ (BUILD FEHLGESCHLAGEN). Sie können die in der Protokolldatei angegebenen Informationen überprüfen, um die fehlerhafte Datei zu finden und das Problem zu beheben.

   Im folgenden Beispiel-Protokolldatei-Snippet können Sie die `BUILD FAILED`-Meldung zusammen mit dem Grund für den Fehler anzeigen.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *Experience Manager Guides-bezogener Fehler*: Die andere Fehlerart, die Sie in der Protokolldatei identifizieren können, ist mit dem Experience Manager Guides-Prozess selbst verbunden. In diesem Fall wird die DITA-Zuordnungsdatei erfolgreich geparst, aber der Ausgabegenerierungsprozess schlägt aufgrund eines internen Fehlers in Experience Manager Guides fehl. Bei Fehlern dieser Art müssen Sie Hilfe vom technischen Support-Team anfordern.

   Im folgenden Beispiel-Protokolldatei-Snippet können Sie die `BUILD SUCCESSFUL` und anschließend weitere technische Fehler anzeigen.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## JSP-Kompilierungsfehler beheben

Wenn Ihr DITA-Thema zu groß ist, wird möglicherweise der JSP-Kompilierungsfehler \(`org.apache.sling.api.request.TooManyCallsException`\) in Ihrem Browser angezeigt. Dieser Fehler kann auftreten, wenn Sie ein Thema zum Bearbeiten, Überprüfen oder Veröffentlichen öffnen.

Führen Sie zur Behebung dieses Problems folgende Schritte durch:

1. Wählen Sie in der globalen Navigation die Option Tools und dann Vorgänge \> Web-Konsole aus.

   Die Seite Konfiguration der Adobe Experience Manager-Web-Konsole wird angezeigt.

1. Suchen Sie nach der Komponente *Apache Sling Main Servlet* und wählen Sie sie aus.

   Die konfigurierbaren Optionen für das Apache Sling Main Servlet werden angezeigt.

1. Erhöhen Sie den Wert für den Parameter *Anzahl der Aufrufe pro Anfrage* gemäß Ihren Anforderungen.


**Übergeordnetes Thema:**&#x200B;[ Ausgabegenerierung](generate-output.md)
