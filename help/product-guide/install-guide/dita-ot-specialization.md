---
title: Verwenden benutzerdefinierter DITA-OT und DITA-Spezialisierung
description: Erfahren Sie, wie Sie benutzerdefinierte DITA-OT- und DITA-Spezialisierungen verwenden
exl-id: ddc1393b-b269-40e5-9627-96dad82b42e9
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: b04f20af6e1f85746e13dad464513bf60b039378
workflow-type: tm+mt
source-wordcount: '2122'
ht-degree: 0%

---

# Verwenden benutzerdefinierter DITA-OT und DITA-Spezialisierung {#id181GAJ0005Z}

Das DITA Open Toolkit \(DITA-OT\) ist ein Satz von Java-basierten Open-Source-Tools zur Verarbeitung von DITA-Zuordnungen und Themeninhalten. AEM Guides ermöglicht den einfachen Import und die Verwendung benutzerdefinierter DITA-OT-Plug-ins. Nach dem Import kann AEM Guides so konfiguriert werden, dass das benutzerdefinierte DITA-OT-Plug-in verwendet wird, um Ausgaben in jedem Format zu generieren. Wählen Sie zum Zeitpunkt der Generierung der Ausgabe einfach die Option DITA-OT aus und AEM Guides verwendet das benutzerdefinierte DITA-OT-Plug-in, um die gewünschte Ausgabe zu generieren.

Wenn Sie Ant-Parameter beim Veröffentlichen einer Ausgabe verarbeiten möchten, bietet Ihnen AEM Guides eine einfache Möglichkeit, dies zu tun. Sie können angeben, welche Ant-Parameter Sie verwenden möchten und dieselben vom Veröffentlichungsprozess verarbeitet werden.

>[!NOTE]
>
> AEM Guides wird mit DITA-OT Version 3.3.2 ausgeliefert. AEM Guides unterstützt jedoch DITA-OT Version 1.7 und höher. Eine vollständige Liste der DITA-OT-Versionen finden Sie unter [DITA-OT-Versionen](http://www.dita-ot.org/download).

>[!TIP]
>
> Informationen zu Best Practices bei der Verwendung *benutzerdefinierten DITA-OT-Plug* ins finden Sie in den Abschnitten *Konfiguration von DITA-OT* und Verwenden benutzerdefinierter DITA-OT-Profile“ im Handbuch zu Best Practices.

## Verwenden benutzerdefinierter DITA-OT-Plug-ins {#id181NH1020L7}

Es gibt zwei Möglichkeiten, ein benutzerdefiniertes DITA-OT-Plug-in für die Veröffentlichung zu verwenden. Die erste Methode besteht darin, das benutzerdefinierte DITA-OT-Plug-in in das AEM-Repository hochzuladen. Die andere Methode besteht darin, das benutzerdefinierte DITA-OT-Plug-in auf Ihrem Server zu speichern, ein Profil zu erstellen und den Speicherort des benutzerdefinierten DITA-OT-Plug-ins in Ihrem Profil anzugeben.

Standardmäßig verfügt AEM Guides über ein vorkonfiguriertes Profil , das die Konfigurationen für die Standardvorlagen enthält, die zum Bearbeiten und Veröffentlichen von Inhalten verwendet werden können. Sie können benutzerdefinierte Profile mit benutzerdefinierten Vorlagen erstellen, die beim Bearbeiten von Dokumenten und benutzerdefinierten DITA-OT-Plug-ins zum Veröffentlichen von Inhalten verwendet werden.

Das standardmäßige DITA-OT-Paket, das mit AEM Guides verfügbar ist, enthält den Apache FOP XSL-FO-Prozessor, der das Rendern von MathML-Gleichungen nicht unterstützt. Wenn Sie MathML-Gleichungen in Ihrem Inhalt verwenden, stellen Sie sicher, dass Sie ein MathML Rendering Engine-Plug-in für Apache FOP integriert haben oder einen anderen XSL-FO-Prozessor verwenden.

>[!IMPORTANT]
>
> Wenn Sie AEM Guides von Version 2.2 auf 2.5.1 oder 2.6 aktualisiert haben, werden alle über den Konfigurations-Manager vorgenommenen Änderungen automatisch ausgewählt und im Standardprofil gespeichert.

Führen Sie die folgenden Schritte aus, um das benutzerdefinierte DITA-OT-Plug-in in das AEM-Repository hochzuladen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Laden Sie die `DITA-OT.ZIP` Datei herunter.

   Der Speicherort der `DITA-OT.ZIP` ist `/libs/fmdita/dita_resources/DITA-OT.zip`.

   ![](assets/dita-ot-zip-in-crx.png)

1. Extrahieren Sie den Inhalt der ZIP-Datei auf Ihrem Server.

1. Verwenden Sie einen DITA-OT-Plug-in-Integrationsmechanismus, um die neue Version von DITA-OT in Ihr benutzerdefiniertes DITA-OT-Plug-in zu integrieren.

   >[!NOTE]
   >
   > Das Klassenpfadtrennzeichen in der Plug-in-ZIP-Datei hängt vom Betriebssystem ab, d. h. wenn der Server unter Windows gehostet wird, unterscheidet sich das Klassenpfadtrennzeichen von dem unter Linux verwendeten. Weitere Informationen zum manuellen Integrieren von Plug-ins finden Sie im Thema *Manuelles Installieren von Plug-ins* in der DITA-OT-Dokumentation.

1. Erstellen Sie erneut die ZIP-Datei, wobei Sie den gleichen Namen \(`DITA-OT.ZIP`\) und die Ordnerstruktur beibehalten.

1. Laden Sie die aktualisierte ZIP-Datei wieder in das AEM-Repository hoch.

   Stellen Sie die folgenden Prüfungen sicher, bevor Sie die ZIP-Datei hochladen:

   - Führen Sie den Integrator \(zum Installieren des benutzerdefinierten Plug-ins\) auf einem Mac/Linux-Betriebssystem aus, um Probleme mit Dateiseparatoren zu vermeiden. Da Windows- und Linux-Betriebssysteme unterschiedliche Dateiseparatoren haben, ist das in Mac/Linux-Betriebssystemen integrierte Plug-in mit Windows- und Linux-Setup kompatibel.
   - Stellen Sie sicher, dass die `DITA-OT.ZIP`-Datei einen Ordner mit dem Namen „DITA-OT“ enthält, der alle relevanten Plug-ins und Dateien enthält.
   - Überprüfen Sie, ob `DITA-OT.ZIP` erstellte Datei vom Typ „mimeType: „nt:file“ \(entspricht dem primären Typ der ZIP-Datei beim Hochladen in AEM\) ist. Verwenden Sie ein WebDAV-Tool oder eine Code-Bereitstellung, um diese ZIP-Datei in den gewünschten Pfad in AEM hochzuladen. \(Verwenden Sie den Package Manager von AEM nicht, um diese ZIP-Datei bereitzustellen, da diese ZIP-Datei kein AEM-Inhaltspaket, sondern nur eine Archivdatei ist.\)

   >[!NOTE]
   >
   > Es wird empfohlen, das standardmäßige DITA-OT-Paket nicht zu überschreiben. Sie sollten Ihr benutzerdefiniertes DITA-OT-Paket, das Ihr Plug-in enthält, an einen anderen Speicherort unter dem `apps` hochladen.

1. Öffnen Sie das standardmäßige DITA-Profil zur Bearbeitung und speichern Sie es \(ohne Aktualisierungen vorzunehmen\), damit die Änderungen wirksam werden.


Führen Sie die folgenden Schritte aus, um ein neues Profil zu erstellen und es so zu konfigurieren, dass es das benutzerdefinierte DITA-OT-Plug-in verwendet, das auf Ihrem Server gespeichert ist:

1. Speichern Sie das benutzerdefinierte DITA-OT-Plug-in auf Ihrem Server.

   >[!NOTE]
   >
   > Die Ordnerstruktur zum Speichern des benutzerdefinierten DITA-OT-Plug-ins sollte wie folgt sein: `\*<parent-folder\>*\DITA-OT`.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die **DITA-Profile**-Kachel.

   >[!NOTE]
   >
   > Die Standardprofilinformationen werden auf der Seite Profile angezeigt. Wenn Sie AEM Guides von Version 2.2 auf 2.5.1 oder 2.6 aktualisiert haben, werden alle über den Konfigurations-Manager vorgenommenen Änderungen automatisch ausgewählt und im Standardprofil gespeichert.

1. Sie können das Standardprofil bearbeiten, ein neues Profil erstellen oder Einstellungen aus dem Standardprofil duplizieren, um ein neues Profil zu erstellen.

   >[!NOTE]
   >
   > Sie können das Standardprofil aktualisieren, es jedoch nicht löschen. Alle neuen Profile, die Sie erstellen, können jedoch bearbeitet und gelöscht werden.

1. Konfigurieren Sie die folgenden Eigenschaften, um das benutzerdefinierte DITA-OT-Plug-in zu verwenden:

   | Eigenschaftsname | Beschreibung |
   |-------------|-----------|
   | **Profileigenschaften** |
   | Profilname | Geben Sie einen eindeutigen Namen für dieses Profil an. |
   | Ausgabe wiederverwenden | *\(Optional\)* Wenn Ihr Profil auf einem vorhandenen Profil basiert, wählen Sie diese Option. Durch Auswahl dieser Option wird sichergestellt, dass AEM Guides den Inhalt des DITA-OT-Pakets nicht erneut extrahiert und das vorhandene DITA-OT-Paket wiederverwendet. |
   | Pfad der Profilextraktion | *\(Optional\)* Geben Sie den Pfad an, unter dem DITA-OT auf der Festplatte gespeichert wird. Standardmäßig bündelt AEM Guides ein DITA-OT-Paket in seinem Repository und wird unter diesem Pfad auf der Festplatte extrahiert.<br>**Hinweis** Sie können diesen Pfad mit einer beliebigen vorhandenen Systemvariablen oder -eigenschaft definieren. Weitere Informationen finden Sie unter Beschreibung [ Eigenschaft ](#id181NH0YN0AX)DITA-OT-Umgebungsvariablen“. |
   | Zugewiesener Pfad | \(*Optional*\) Geben Sie den Pfad in Ihrem Content-Repository an, für den dieses Profil gilt. Sie können mehrere Speicherorte angeben. |
   | **DITA-OT-Eigenschaften** |
   | DITA-OT-Timeout | \(*Optional*\) Geben Sie die Zeit \(in Sekunden\) an, für die AEM Guides auf eine Antwort des DITA-OT-Plug-ins wartet. Wenn in der angegebenen Zeit keine Antwort eingeht, beendet AEM Guides die Veröffentlichungsaufgabe und die Aufgabe wird als fehlgeschlagen markiert. Außerdem werden die Fehlerprotokolle in der Protokolldatei für die Ausgabegenerierung zur Verfügung gestellt. <br>Standardwert: 300 Sekunden \(5 Minuten\) |
   | DITA-OT-PDF-Argumente | Geben Sie die Befehlszeilenargumente an, die vom benutzerdefinierten DITA-OT-Plug-in zum Generieren der PDF-Ausgabe verarbeitet werden. Geben Sie für alle benutzerdefinierten DITA-OT-Profile das folgende Befehlszeilenargument an:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | DITA-OT-AEM-Argumente | \(*Optional*\) Geben Sie die benutzerdefinierten Befehlszeilenargumente an, die vom benutzerdefinierten DITA-OT-Plug-in zum Generieren der AEM-Site-Ausgabe verarbeitet werden. |
   | DITA-OT-Bibliothekspfade | \(*Optional*\) Geben Sie die zusätzlichen Bibliothekspfade des DITA-OT-Plug-ins an. |
   | DITA-TO-Build-XML | \(*Optional*\) Geben Sie den Pfad des benutzerdefinierten Ant-Build-Skripts an, das mit dem benutzerdefinierten DITA-OT-Plug-in bereitgestellt wird. Dieser Pfad ist relativ zum DITA-OT-Verzeichnis auf Ihrem Dateisystem. |
   | DITA-OT-Ant-Skriptordner | \(Optional\) Geben Sie den Pfad des Skriptordners „DITA-OT Ant“ an. Dieser Pfad ist relativ zum DITA-OT-Verzeichnis auf Ihrem Dateisystem. |
   | DITA-OT-Umgebungsvariablen | *\(Optional\)* Geben Sie Umgebungsvariablen an, die an den DITA-OT-Prozess übergeben werden sollen. Standardmäßig fügt AEM Guides vier Variablen hinzu: `ANT_OPTS`, `ANT_HOME`, `PATH` und `CLASSPATH`. <br> Sie können jede der vorhandenen Systemumgebungsvariablen oder -eigenschaften zum Erstellen neuer Umgebungsvariablen wiederverwenden. Beispiel: Sie haben `JAVA_HOME` Systemvariable in Ihrem System definiert und möchten eine neue Umgebungsvariable mit dem Namen `JAVA_BIN` definieren, die mithilfe von `JAVA_HOME` erstellt wird. Anschließend können Sie die Definition von `JAVA_BIN` wie folgt hinzufügen<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Hinweis** Sie können auch Java-Systemeigenschaften zum Erstellen von Umgebungsvariablen verwenden. Wenn beispielsweise das AEM-Startskript eine Java-Systemeigenschaft definiert, die einem temporären Verzeichnis `java.io.tmpdir` ist, können Sie diese Eigenschaft verwenden, um eine neue Variable zu definieren als: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Wichtig** Um eine vorhandene Systemvariable oder -eigenschaft wiederzuverwenden, muss sie in `${}` eingeschlossen sein. |
   | DITA-OT-Ausgabe überschreiben | *\(Optional\)* Wenn diese Option aktiviert ist, können Sie das auf Ihrem lokalen System verfügbare DITA-OT-Paket angeben, um mithilfe von DITA-OT eine Ausgabe zu generieren. Diese Konfiguration wird bei Aktivierung des ConfigManagers festgelegt. <br> Wenn Sie den Pfad eines DITA-OT-Pakets angeben möchten, das auf dem AEM-Server gespeichert ist, deaktivieren Sie diese Option. |
   | AEM-DITA-OT-ZIP-Pfad/lokaler DITA-OT-Ordnerpfad | Geben Sie abhängig von Ihrer Auswahl in der Ausgabe DITA-OT überschreiben den vollständigen Pfad an, unter dem die benutzerdefinierte Datei DITA-OT.zip gespeichert ist. Dies kann der Pfad in Ihrem AEM-Repository oder lokalen System sein. |
   | DITA-OT-Plug-in-Pfad | Pfad des benutzerdefinierten Plug-ins. Dieses Plug-in wird automatisch in das Haupt-DITA-OT-Paket integriert. |
   | Kataloge integrieren | \(*Optional*\) Pfad der benutzerdefinierten DTD- und XSD-catalog.xml-Dateien im AEM-Repository. Dies sollte nur bereitgestellt werden, wenn die Kataloge im DITA-OT-Paket fehlen. Diese Kataloge werden automatisch als Plug-In in das Haupt-DITA-OT integriert. |
   | System-ID-Katalog hinzufügen | \(*Optional*\) Wählen Sie diese Option nur, wenn im Katalog öffentliche ID-Einträge fehlen oder wenn die DITA-Dateien nur die System-IDs verwenden, die relativ zum Server-Pfad sind, von dem aus sie hochgeladen werden. |
   | Temporärer DITA-OUT-Pfad | *\(Optional\)* Geben Sie einen temporären Speicherort an, an den DITA-Dateien zur Verarbeitung kopiert werden. Bevor DITA-OT Dateien verarbeitet, werden sie an diesen temporären Speicherort kopiert. Standardmäßig lautet der temporäre Speicherort: <br> **Hinweis** Sie können diesen Pfad mit einer beliebigen vorhandenen Systemvariablen oder -eigenschaft definieren. Weitere Informationen finden Sie unter Beschreibung [ Eigenschaft ](#id181NH0YN0AX)DITA-OT-Umgebungsvariablen“. |

   >[!NOTE]
   >
   >  Das AEM Guides-Installationsprogramm erstellt zwei Umgebungsvariablen, mit denen Sie den Pfad der benutzerdefinierten DITA-OT-Plug-in-Dateien angeben können. Bei diesen Umgebungsvariablen handelt es sich um DITAOT\_DIR, das den Pfad des DITA-OT-Verzeichnisses auf dem Dateisystem enthält, und DITAMAP\_DIR, das den Pfad enthält, aus dem der DITA-Map-Inhalt auf dem Dateisystem extrahiert wird.

1. Klicken Sie **Fertig**, um das Profil zu speichern.


>[!NOTE]
>
> Sie können das benutzerdefinierte DITA-Profil als Paket exportieren und auf die anderen AEM Guides-Instanzen hochladen, um Zeit zu sparen. Weitere Informationen finden Sie unter [Anhang](appendix.md).

## Integrieren von DITA Specialization {#id211MB0E00XA}

Bei der DITA-Spezialisierung werden neue DITA-Strukturen erstellt, indem neue Elemente hinzugefügt oder vorhandene Elemente entfernt werden. Um ein neues DITA-Element zu erstellen, können Sie ein vorhandenes DITA-Element als Basis verwenden und es gemäß Ihren Authoring-Anforderungen ändern. Im Wesentlichen ermöglicht Ihnen die DITA-Spezialisierung die Erstellung benutzerdefinierter Informationsmodelle, die Ihren Geschäftsanforderungen entsprechen und gleichzeitig die Vorteile der bestehenden DITA-Architektur nutzen.

Sie können die Profilfunktion verwenden, um benutzerdefinierte DITA-Spezialisierungseinstellungen zu speichern. Diese Einstellungen können dann zum Zeitpunkt der Erstellung und Veröffentlichung von benutzerdefinierten DITA-Inhalten verwendet werden. Mit AEM Guides können Sie eine öffentliche ID und eine System-ID in Ihren benutzerdefinierten DTDs/XSDs verwenden.

>[!NOTE]
>
> AEM Guides Web Editor unterstützt keine XSDs.

Führen Sie die folgenden Schritte aus, um ein neues Profil zu erstellen und es für die Verwendung spezieller DTDs und XSDs in AEM Guides zu konfigurieren:

1. Erstellen Sie auf Ihrem lokalen Computer einen Spezialisierungsordner, der die spezialisierten DTDs und XSDs enthält.

1. Geben Sie die DTD-Details in der `catalog.xml`-Datei an, die auch im Spezialisierungsordner enthalten sein müssen.

   >[!NOTE]
   >
   > Bei DITA 1.3 lautet der Standardspeicherort für DTD-`catalog.xml` im AEM-Repository: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Geben Sie die XSD-Details in der `catalog.xml` an, die auch im Spezialisierungsordner enthalten sein müssen.

   >[!NOTE]
   >
   > Im Fall von DITA 1.3 lautet der Standardspeicherort für die Datei „XSD catalog.xml“ im AEM-Repository: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Laden Sie den Ordner an den folgenden Speicherort hoch:

   `/apps/fmdita/dita_resources`

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die **DITA-Profile**-Kachel.

   >[!NOTE]
   >
   > Die Standardprofilinformationen werden auf der Seite Profile angezeigt. Wenn Sie AEM Guides von Version 2.2 auf 2.5.1 oder 2.6 aktualisiert haben, werden alle über den Konfigurations-Manager vorgenommenen Änderungen automatisch ausgewählt und im Standardprofil gespeichert.



1. Sie können das Standardprofil bearbeiten, ein neues Profil erstellen oder Einstellungen aus dem Standardprofil duplizieren, um ein neues Profil zu erstellen.

   >[!NOTE]
   >
   > Das Standardprofil kann nicht gelöscht werden. Alle neuen Profile, die Sie erstellen, können jedoch bearbeitet und gelöscht werden.

1. Geben Sie in den **Schema** \> **Catalog**-Einstellungen den Pfad der benutzerdefinierten DTD- und XSD-`catalog.xml` in Ihrem AEM-Repository an.

   >[!NOTE]
   >
   > Wenn Sie das benutzerdefinierte Schema verwenden, müssen Sie den Pfad der benutzerdefinierten DTD- und XSD-catalog.xml-Dateien im AEM-Repository in der Option **Integrationskataloge** definieren.



1. Wählen Sie **Option „System-ID-Katalog**.

   >[!NOTE]
   >
   > Wählen Sie diese Option nur aus, wenn im Katalog öffentliche ID-Einträge fehlen oder wenn die DITA-Dateien nur die System-IDs verwenden, die relativ zum lokalen Dateipfad sind, von dem aus sie hochgeladen werden.

   Weitere Informationen zu anderen Eigenschaften auf der Seite Profile finden Sie in der Tabelle „Eigenschaften“ in [Schritt 6](#id17A9F0D075Z) des Abschnitts [Verwenden benutzerdefinierter DITA-OT-Plug-ins](#id181NH1020L7).

1. Klicken Sie **Fertig**, um das Profil zu speichern.


>[!NOTE]
>
> Sie können das benutzerdefinierte DITA-Profil als Paket exportieren und auf die anderen AEM Guides-Instanzen hochladen, um Zeit zu sparen. Weitere Informationen finden Sie unter [Appendix.md](appendix.md).
