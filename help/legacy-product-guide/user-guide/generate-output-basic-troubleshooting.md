---
title: Grundlegende Fehlerbehebung
description: Beheben Sie Probleme mit der grundlegenden Fehlerbehebung in AEM Guides. Erfahren Sie, wie Sie die Protokolldatei in einem Texteditor anzeigen, kopieren und überprüfen und JSP-Kompilierungsfehler beheben können.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Grundlegende Fehlerbehebung {#id1821I0Y0G0A}

Beim Arbeiten mit AEM Guides können beim Veröffentlichen oder Öffnen eines Dokuments Fehler auftreten. Solche Fehler können in der DITA-Zuordnung, dem Thema oder im AEM Guides-Prozess selbst auftreten. In diesem Abschnitt finden Sie Informationen zum Zugreifen auf und Analysieren von Informationen in der Protokolldatei zur Ausgabegenerierung. Wenn Ihr DITA-Thema zu groß ist, wird möglicherweise der JSP-Kompilierungsfehler angezeigt. In diesem Abschnitt finden Sie auch Informationen zum Beheben des JSP-Kompilierungsfehlers.

## Protokolldatei anzeigen und überprüfen {#id1822G0P0CHS}

Führen Sie die folgenden Schritte aus, um die Protokolldatei zur Ausgabegenerierung anzuzeigen und zu überprüfen:

1. Nachdem Sie den Generierungsprozess der Ausgabe gestartet haben, klicken Sie in der DITA-Map-Konsole auf **Ausgaben** .

   Die Spalte **Allgemein** der **generierten Ausgaben** enthält die Symbole, die einen visuellen Hinweis auf den Erfolg oder das Fehlschlagen der Ausgabegenerierung geben.

   ![](images/output-general-settings.png){width="300" align="left"}

   Im obigen Screenshot zeigen die ersten und dritten Symbole eine fehlgeschlagene Ausgabegenerierung an. Das zweite Symbol zeigt eine erfolgreiche Ausgabegenerierung, jedoch mit Nachrichten. Die letzte ist eine erfolgreiche Ausgabegenerierung ohne Nachricht.

1. Klicken Sie nach Abschluss des Auftrags auf den Link in der Spalte **Generiert am** .

   Die Protokolldatei wird in einer neuen Registerkarte geöffnet.

   ![](images/log-file.png){width="800" align="left"}

1. Wenden Sie die folgenden Filter an, um den Text in der Protokolldatei hervorzuheben:
   - Fatal: Zeigt die schwerwiegenden Fehler in der Protokolldatei mit rosa Farbe an.
   - Fehler: Zeigt die Fehler in der Protokolldatei mit orangefarbener Farbe an.
   - Warnung: Markiert die Warnhinweise in der Protokolldatei mit violetter Farbe.
   - Info: Markiert die Informationsmeldungen in der Protokolldatei mit blauer Farbe.
   - Ausnahme: Die Ausnahmen in der Protokolldatei werden gelb hervorgehoben.
1. Verwenden Sie die Navigationstasten nach oben und unten, um zum markierten Text in der Protokolldatei zu springen.

   Alternativ können Sie durch die Protokolldatei blättern und die Meldungen überprüfen.


## Kopieren und Überprüfen der Protokolldatei in einem Texteditor

Führen Sie die folgenden Schritte aus, um die Protokolldatei zur Ausgabegenerierung in einem Texteditor zu kopieren und zu überprüfen:

1. Nachdem Sie den Generierungsprozess der Ausgabe gestartet haben, klicken Sie in der DITA-Map-Konsole auf **Ausgaben** .

1. Klicken Sie nach Abschluss des Auftrags auf den Link in der Spalte **Generiert am** .

   Die Protokolldatei wird in einer neuen Registerkarte geöffnet.

1. Klicken Sie auf die Schaltfläche **Protokoll kopieren** . Die Protokolldatei wird in die Zwischenablage kopiert.
1. Öffnen Sie einen Texteditor und fügen Sie die Protokolldatei in den Editor ein.

1. Scrollen Sie durch die Protokolldatei und suchen Sie nach Meldungen.

   Mithilfe der folgenden Informationen können Sie feststellen, ob ein Fehler in der DITA-Datei oder im AEM Guides-Prozess vorliegt:

   - *Fehler bezüglich DITA-Map-Datei*: Wenn ein Fehler in der DITA-Map-Datei oder einer anderen in der DITA-Zuordnung enthaltenen Datei gefunden wird, enthält die Protokolldatei die Zeichenfolge &quot;BUILD FEHLGESCHLAGEN&quot;. Sie können die in der Protokolldatei angegebenen Informationen überprüfen, um die fehlerhafte Datei zu finden und das Problem zu beheben.

   Im folgenden Beispielprotokolldateiausschnitt sehen Sie die Meldung `BUILD FAILED` zusammen mit dem Grund für den Fehler.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *AEM Guides-bezogener Fehler*: Der andere Fehlertyp, den Sie in der Protokolldatei identifizieren können, hängt mit dem AEM Guides-Prozess selbst zusammen. In diesem Fall wird die DITA-Map-Datei erfolgreich analysiert, aber der Output-Generierungsprozess schlägt aufgrund eines internen Fehlers in AEM Guides fehl. Für solche Fehler müssen Sie sich beim technischen Support-Team um Hilfe bemühen.

   Im folgenden Beispielprotokolldateiausschnitt sehen Sie die Meldung `BUILD SUCCESSFUL` gefolgt von einem anderen technischen Fehler.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## JSP-Kompilierungsfehler beheben

Wenn Ihr DITA-Thema zu groß ist, wird möglicherweise der JSP-Kompilierungsfehler \(`org.apache.sling.api.request.TooManyCallsException`\) in Ihrem Browser angezeigt. Dieser Fehler wird möglicherweise angezeigt, wenn Sie ein Thema zum Bearbeiten, Überprüfen oder Veröffentlichen öffnen.

Führen Sie die folgenden Schritte aus, um dieses Problem zu beheben:

1. Wählen Sie in der globalen Navigation die Option Tools und dann Vorgänge > Web-Konsole aus.

   Die Seite &quot;Konfiguration der Adobe Experience Manager-Web-Konsole&quot;wird angezeigt.

1. Suchen Sie nach der Komponente *Apache Sling Main Servlet* und klicken Sie darauf.

   Die konfigurierbaren Optionen für das Apache Sling Main Servlet werden angezeigt.

1. Erhöhen Sie den Wert für den Parameter *Anzahl Aufrufe pro Anfrage* gemäß Ihren Anforderungen.


**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
