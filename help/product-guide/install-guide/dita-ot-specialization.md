---
title: Verwenden einer benutzerdefinierten DITA-OT- und DITA-Spezialisierung
description: Erfahren Sie, wie Sie benutzerdefinierte DITA-OT- und DITA-Spezialisierung verwenden.
exl-id: ddc1393b-b269-40e5-9627-96dad82b42e9
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 0%

---

# Verwenden einer benutzerdefinierten DITA-OT- und DITA-Spezialisierung {#id181GAJ0005Z}

Das DITA Open Toolkit \(DITA-OT\) ist ein Satz von Java-basierten Open-Source-Tools, die die Verarbeitung von DITA-Maps und Themeninhalten ermöglichen. Mit AEM Guides können Sie benutzerdefinierte DITA-OT-Plug-ins einfach importieren und verwenden. Nach dem Import kann AEM Guides so konfiguriert werden, dass das benutzerdefinierte DITA-OT-Plug-in verwendet wird, um Ausgaben in jedem beliebigen Format zu generieren. Wählen Sie zum Zeitpunkt der Generierung der Ausgabe einfach die DITA-OT-Option aus und AEM Guides verwendet das benutzerdefinierte DITA-OT-Plug-in, um die erforderliche Ausgabe zu generieren.

Wenn Sie Ant-Parameter beim Veröffentlichen einer Ausgabe verarbeiten möchten, können Sie dies mit AEM Guides einfach tun. Sie können angeben, welche Ant-Parameter Sie verwenden möchten und dieselben dann vom Veröffentlichungsprozess verarbeitet werden.

>[!NOTE]
>
> AEM Guides wird mit DITA-OT Version 3.3.2 ausgeliefert. AEM Guides unterstützt jedoch die DITA-OT-Version 1.7 und höher. Die vollständige Liste der DITA-OT-Versionen finden Sie unter [DITA-OT-Versionen](http://www.dita-ot.org/download).

>[!TIP]
>
> Informationen zu Best Practices zur Verwendung benutzerdefinierter DITA-OT-Plug-ins finden Sie in den Abschnitten *DITA-OT-Profilkonfiguration* und *Verwenden benutzerdefinierter DITA-OT* im Best Practices-Handbuch .

## Verwenden benutzerdefinierter DITA-OT-Plug-ins {#id181NH1020L7}

Es gibt zwei Möglichkeiten, das benutzerdefinierte DITA-OT-Plug-in für die Veröffentlichung zu verwenden. Die erste Methode besteht darin, das benutzerdefinierte DITA-OT-Plug-in in das AEM-Repository hochzuladen. Die andere Methode besteht darin, das benutzerdefinierte DITA-OT-Plug-in auf Ihrem Server zu speichern, ein Profil zu erstellen und den Speicherort des benutzerdefinierten DITA-OT-Plug-ins in Ihrem Profil anzugeben.

Standardmäßig ist AEM Guides mit einem vorkonfigurierten Profil ausgestattet, das die Konfigurationen für die Standardvorlagen enthält, die zum Bearbeiten und Veröffentlichen von Inhalten verwendet werden sollen. Sie können benutzerdefinierte Profile mit benutzerdefinierten Vorlagen erstellen, die beim Bearbeiten von Dokumenten und benutzerdefinierten DITA-OT-Plug-ins zum Veröffentlichen von Inhalten verwendet werden.

Das DITA-OT-Standardpaket, das mit AEM Guides verfügbar ist, enthält den Apache FOP XSL-FO-Prozessor, der das Rendering von MathML-Gleichungen nicht unterstützt. Wenn Sie MathML-Gleichungen in Ihrem Inhalt verwenden, stellen Sie sicher, dass Sie ein MathML-Rendering-Engine-Plug-in für Apache FOP integriert haben oder einen anderen XSL-FO-Prozessor verwenden.

>[!IMPORTANT]
>
> Wenn Sie AEM Guides von Version 2.2 auf 2.5.1 oder 2.6 aktualisiert haben, werden alle über den Konfigurationsmanager vorgenommenen Änderungen automatisch ausgewählt und im Standardprofil gespeichert.

Führen Sie die folgenden Schritte aus, um das benutzerdefinierte DITA-OT-Plug-in in das AEM-Repository hochzuladen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Laden Sie die Datei `DITA-OT.ZIP` herunter.

   Der Speicherort der `DITA-OT.ZIP`-Datei ist `/libs/fmdita/dita_resources/DITA-OT.zip`.

   ![](assets/dita-ot-zip-in-crx.png)

1. Extrahieren Sie den Inhalt der ZIP-Datei auf Ihrem Server.

1. Verwenden Sie einen DITA-OT-Plug-in-Integrationsmechanismus, um die neue Version von DITA-OT in Ihr benutzerdefiniertes DITA-OT-Plug-in zu integrieren.

   >[!NOTE]
   >
   > Das Klassenpfadtrennzeichen in der Plug-in-ZIP-Datei ist vom Betriebssystem abhängig. Wenn Ihr Server unter Windows gehostet wird, unterscheidet sich das Klassenpfadtrennzeichen von dem unter Linux verwendeten. Weitere Informationen zur manuellen Integration von Plug-ins finden Sie im Thema *Manuelles Installieren von Plug-ins* in der DITA-OT-Dokumentation.

1. Erstellen Sie die ZIP-Datei erneut und behalten Sie dabei denselben Namen \(`DITA-OT.ZIP`\) und die Ordnerstruktur bei.

1. Laden Sie die aktualisierte ZIP-Datei wieder in das AEM-Repository hoch.

   Stellen Sie vor dem Hochladen der ZIP-Datei die folgenden Prüfungen sicher:

   - Führen Sie den Integrator \(zur Installation des benutzerdefinierten Plug-ins\) auf einem Mac/Linux-Betriebssystem aus, um Probleme mit Dateiseparatoren zu vermeiden. Da Windows und Linux OS unterschiedliche Dateiseparatoren haben, ist das in Mac/Linux OS integrierte Plug-in sowohl mit dem Windows- als auch dem Linux-Setup kompatibel.
   - Stellen Sie sicher, dass die Datei `DITA-OT.ZIP` einen Ordner mit dem Namen &quot;DITA-OT&quot;enthält, der alle relevanten Plug-ins und Dateien enthält.
   - Überprüfen Sie, ob die von Ihnen erstellte `DITA-OT.ZIP`-Datei mimeType: &quot;nt:file&quot; \(dies entspricht dem primären Typ der ZIP-Datei beim Hochladen in AEM\). Verwenden Sie ein WebDAV-Tool oder eine Codebereitstellung, um diese ZIP-Datei in den gewünschten Pfad in AEM hochzuladen. \(Verwenden Sie AEM Package Manager nicht, um diese ZIP-Datei bereitzustellen, da diese ZIP kein AEM Inhaltspaket, sondern nur eine Archivdatei ist.\)
   >[!NOTE]
   >
   > Es wird empfohlen, das standardmäßige DITA-OT-Paket nicht zu überschreiben. Sie sollten Ihr benutzerdefiniertes DITA-OT-Paket, das Ihr Plug-in enthält, an einem anderen Speicherort unter dem Ordner &quot;`apps`&quot;hochladen.

1. Öffnen Sie das standardmäßige DITA-Profil zur Bearbeitung und speichern Sie es \(ohne Aktualisierungen vorzunehmen\), damit die Änderungen wirksam werden.


Führen Sie die folgenden Schritte aus, um ein neues Profil zu erstellen und es für die Verwendung des auf Ihrem Server gespeicherten benutzerdefinierten DITA-OT-Plug-ins zu konfigurieren:

1. Speichern Sie das benutzerdefinierte DITA-OT-Plug-in auf Ihrem Server.

   >[!NOTE]
   >
   > Die Ordnerstruktur zum Speichern des benutzerdefinierten DITA-OT-Plug-ins sollte folgendermaßen lauten: `\*<parent-folder\>*\DITA-OT`.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die Kachel **DITA-Profile** .

   >[!NOTE]
   >
   > Die Informationen zum Standardprofil werden auf der Seite Profile angezeigt. Wenn Sie AEM Guides von Version 2.2 auf 2.5.1 oder 2.6 aktualisiert haben, werden alle über den Konfigurationsmanager vorgenommenen Änderungen automatisch ausgewählt und im Standardprofil gespeichert.

1. Sie können das Standardprofil bearbeiten, ein neues Profil erstellen oder Einstellungen aus dem Standardprofil duplizieren, um ein neues Profil zu erstellen.

   >[!NOTE]
   >
   > Sie können das Standardprofil aktualisieren, es jedoch nicht löschen. Alle neuen Profile, die Sie erstellen, können jedoch bearbeitet und gelöscht werden.

1. Konfigurieren Sie die folgenden Eigenschaften für die Verwendung des benutzerdefinierten DITA-OT-Plug-ins:

   | Eigenschaftsname | Beschreibung |
   |-------------|-----------|
   | **Profileigenschaften** |
   | Profilname | Geben Sie einen eindeutigen Namen für dieses Profil an. |
   | Ausgabe wiederverwenden | *\(Optional\)* Wenn Ihr Profil auf einem vorhandenen Profil basiert, wählen Sie diese Option aus. Wenn Sie diese Option auswählen, wird sichergestellt, dass AEM Guides den Inhalt des DITA-OT-Pakets nicht erneut extrahiert und das vorhandene DITA-OT-Paket wiederverwendet. |
   | Profilextraktionspfad | *\(Optional\)* Geben Sie den Pfad an, unter dem DITA-OT auf der Festplatte aufbewahrt wird. Standardmäßig bündelt AEM Guides ein DITA-OT-Paket in seinem Repository und wird unter diesem Pfad auf dem Datenträger extrahiert.<br>**Hinweis** Sie können diesen Pfad mit einer beliebigen vorhandenen Systemvariable oder -eigenschaft definieren. Weitere Informationen finden Sie in der Beschreibung der Eigenschaft [DITA-OT-Umgebungsvariablen](#id181NH0YN0AX) . |
   | Zugewiesener Pfad | \(*Optional*\) Geben Sie den Pfad im Inhalts-Repository an, für den dieses Profil gilt. Sie können mehrere Orte angeben. |
   | **DITA-OT-Eigenschaften** |
   | DITA-OT-Timeout | \(*Optional*\) Geben Sie die Zeit \(in Sekunden\) an, für die AEM Guides auf eine Antwort vom DITA-OT-Plug-in wartet. Wenn keine Antwort in der angegebenen Zeit empfangen wurde, beendet AEM Guides die Veröffentlichungsaufgabe und die Aufgabe wird als fehlgeschlagen gekennzeichnet. Außerdem werden die Fehlerprotokolle in der Protokolldatei zur Generierung der Ausgabe verfügbar gemacht. <br>Standardwert: 300 Sekunden \(5 Minuten\) |
   | DITA-OT-PDF-Argumente | Geben Sie die Befehlszeilenargumente an, die vom benutzerdefinierten DITA-OT-Plug-in zum Generieren der PDF-Ausgabe verarbeitet werden. Geben Sie für alle benutzerdefinierten DITA-OT-Profile das folgende Befehlszeilenargument an:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | DITA-OT AEM Arguments | \(*Optional*\) Geben Sie die benutzerdefinierten Befehlszeilenargumente an, die vom benutzerdefinierten DITA-OT-Plug-in zum Generieren der AEM Site-Ausgabe verarbeitet werden. |
   | DITA-OT-Bibliothekspfade | \(*Optional*\) Geben Sie die zusätzlichen Bibliothekspfade des DITA-OT-Plug-ins an. |
   | DITA-OT Build XML | \(*Optional*\) Geben Sie den Pfad des benutzerdefinierten Ant-Build-Skripts an, das mit dem angepassten DITA-OT-Plug-in verknüpft ist. Dieser Pfad ist relativ zum DITA-OT-Ordner auf Ihrem Dateisystem. |
   | DITA-OT Ant Script-Ordner | \(Optional\) Geben Sie den Pfad des Skriptordners DITA-OT Ant an. Dieser Pfad ist relativ zum DITA-OT-Ordner auf Ihrem Dateisystem. |
   | DITA-OT-Umgebungsvariablen | *\(Optional\)* Geben Sie Umgebungsvariablen an, die an den DITA-OT-Prozess weitergegeben werden sollen. Standardmäßig fügt AEM Guides vier Variablen hinzu: `ANT_OPTS`, `ANT_HOME`, `PATH` und `CLASSPATH`. <br> Sie können alle vorhandenen Systemumgebungsvariablen oder Eigenschaften zum Erstellen neuer Umgebungsvariablen wiederverwenden. Wenn Sie beispielsweise die Systemvariable `JAVA_HOME` in Ihrem System definiert haben und eine neue Umgebungsvariable mit dem Namen `JAVA_BIN` definieren möchten, die mit `JAVA_HOME` erstellt wird. Anschließend können Sie die Definition von `JAVA_BIN` wie folgt hinzufügen:<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Hinweis** Sie können auch Java-Systemeigenschaften verwenden, um Umgebungsvariablen zu erstellen. Wenn AEM Startskript beispielsweise die Java-Systemeigenschaft `java.io.tmpdir` für einen temporären Ordner definiert, können Sie mit dieser Eigenschaft eine neue Variable wie folgt definieren: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Wichtig** Um eine vorhandene Systemvariable oder -eigenschaft wiederzuverwenden, muss sie in `${}` eingeschlossen sein. |
   | DITA-OT-Ausgabe überschreiben | *\(Optional\)* Wenn diese Option ausgewählt ist, können Sie das DITA-OT-Paket angeben, das auf Ihrem lokalen System verfügbar ist, um die Ausgabe mithilfe von DITA-OT zu generieren. Diese Konfiguration wird bei Aktivierung des ConfigManager festgelegt. <br> Wenn Sie den Pfad eines DITA-OT-Pakets angeben möchten, das auf AEM Server gespeichert ist, deaktivieren Sie diese Option. |
   | AEM DITA-OT-ZIP-Pfad/lokaler DITA-OT-Ordnerpfad | Geben Sie je nach Ihrer Auswahl in &quot;DITA-OT-Ausgabe überschreiben&quot;den vollständigen Pfad an, unter dem die benutzerdefinierte DITA-OT.zip-Datei gespeichert ist. Dies kann der Pfad in Ihrem AEM-Repository oder lokalen System sein. |
   | DITA-OT-Plug-in-Pfad | Pfad des benutzerdefinierten Plug-ins. Dieses Plug-in wird automatisch in das Haupt-DITA-OT-Paket integriert. |
   | Kataloge integrieren | \(*Optional*\) Pfad der benutzerdefinierten DTD- und XSD-catalog.xml-Dateien im AEM-Repository. Dies sollte nur bereitgestellt werden, wenn die Kataloge im DITA-OT-Paket fehlen. Diese Kataloge werden automatisch als Plug-in in das DITA-OT integriert. |
   | System-ID-Katalog hinzufügen | \(*Optional*\) Wählen Sie diese Option nur aus, wenn im Katalog fehlende Öffentliche ID-Einträge vorhanden sind oder die DITA-Dateien nur die System-IDs verwenden, die relativ zum Serverpfad sind, von dem aus sie hochgeladen werden. |
   | Temporärer DITA-OT-Pfad | *\(Optional\)* Geben Sie einen temporären Speicherort an, an den DITA-Dateien zur Verarbeitung kopiert werden. Bevor DITA-OT Dateien verarbeitet, werden sie an diesen temporären Speicherort kopiert. Standardmäßig lautet der temporäre Speicherort: <br> **Hinweis** Sie können diesen Pfad mit einer beliebigen vorhandenen Systemvariable oder -eigenschaft definieren. Weitere Informationen finden Sie in der Beschreibung der Eigenschaft [DITA-OT-Umgebungsvariablen](#id181NH0YN0AX) . |

   >[!NOTE]
   >
   >  Das AEM Guides-Installationsprogramm erstellt zwei Umgebungsvariablen, mit denen Sie den Pfad der benutzerdefinierten DITA-OT-Plug-in-Dateien angeben können. Diese Umgebungsvariablen sind: DITAOT\_DIR, das den Pfad des DITA-OT-Ordners im Dateisystem enthält, und DITAMAP\_DIR, der den Pfad enthält, in den der DITA-Map-Inhalt im Dateisystem extrahiert wird.

1. Klicken Sie auf **Fertig** , um das Profil zu speichern.


>[!NOTE]
>
> Sie können das benutzerdefinierte DITA-Profil als Paket exportieren und auf die anderen AEM Guides-Instanzen hochladen, um Zeit zu sparen. Weitere Informationen finden Sie unter [Anhang](appendix.md).

## Integrieren der DITA-Spezialisierung {#id211MB0E00XA}

Bei der DITA-Spezialisierung werden neue DITA-Strukturen erstellt, indem neue Elemente hinzugefügt oder vorhandene Elemente entfernt werden. Um ein neues DITA-Element zu erstellen, können Sie ein vorhandenes DITA-Element als Grundlage nehmen und es gemäß Ihren Authoring-Anforderungen ändern. Im Wesentlichen ermöglicht Ihnen die DITA-Spezialisierung die Erstellung benutzerdefinierter Informationsmodelle, die Ihren Geschäftsanforderungen entsprechen und gleichzeitig die Vorteile der vorhandenen DITA-Architektur erhalten.

Sie können die Profilfunktion verwenden, um benutzerdefinierte DITA-Spezialisierungseinstellungen zu speichern. Diese Einstellungen können dann zum Zeitpunkt der Bearbeitung und Veröffentlichung von benutzerdefinierten DITA-Inhalten verwendet werden. Mit AEM Guides können Sie die öffentliche ID und die System-ID in Ihren benutzerdefinierten DTDs/XSDs verwenden.

>[!NOTE]
>
> AEM Guides Web Editor unterstützt keine XSDs.

Führen Sie die folgenden Schritte aus, um ein neues Profil zu erstellen und es für die Verwendung spezialisierter DTDs und XSDs AEM Guides zu konfigurieren:

1. Erstellen Sie auf Ihrem lokalen Computer einen Spezialisierungsordner, der die spezialisierten DTDs und XSDs enthält.

1. Geben Sie die DTD-Details in der Datei `catalog.xml` an, die auch im Spezialisierungsordner enthalten sein muss.

   >[!NOTE]
   >
   > Bei DITA 1.3 lautet der Standardspeicherort für die DTD `catalog.xml`-Datei im AEM-Repository: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Geben Sie die XSD-Details in der Datei `catalog.xml` an, die auch im Spezialisierungsordner enthalten sein muss.

   >[!NOTE]
   >
   > Im Fall von DITA 1.3 lautet der Standardspeicherort für die XSD-Datei catalog.xml im AEM-Repository: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Laden Sie den Ordner an den folgenden Speicherort hoch:

   `/apps/fmdita/dita_resources`

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die Kachel **DITA-Profile** .

   >[!NOTE]
   >
   > Die Informationen zum Standardprofil werden auf der Seite Profile angezeigt. Wenn Sie AEM Guides von Version 2.2 auf 2.5.1 oder 2.6 aktualisiert haben, werden alle über den Konfigurationsmanager vorgenommenen Änderungen automatisch ausgewählt und im Standardprofil gespeichert.

1. Sie können das Standardprofil bearbeiten, ein neues Profil erstellen oder Einstellungen aus dem Standardprofil duplizieren, um ein neues Profil zu erstellen.

   >[!NOTE]
   >
   > Das Standardprofil kann nicht gelöscht werden. Alle neuen Profile, die Sie erstellen, können jedoch bearbeitet und gelöscht werden.

1. Geben Sie in den Einstellungen **Schema** \> **Katalog** den Pfad der benutzerdefinierten DTD- und XSD-Dateien `catalog.xml` in Ihrem AEM-Repository an.

1. Wählen Sie die Option **System-ID-Katalog hinzufügen** aus.

   >[!NOTE]
   >
   > Wählen Sie diese Option nur aus, wenn im Katalog fehlende Öffentliche ID-Einträge vorhanden sind oder die DITA-Dateien nur die System-IDs verwenden, die relativ zum lokalen Dateipfad sind, von dem aus sie hochgeladen werden.

   Weitere Informationen zu anderen Eigenschaften auf der Seite &quot;Profile&quot;finden Sie in der Tabelle &quot;Eigenschaften&quot;im Abschnitt [Schritt 6](#id17A9F0D075Z) des Abschnitts [Verwenden benutzerdefinierter DITA-OT-Plug-ins](#id181NH1020L7) .

1. Klicken Sie auf **Fertig** , um das Profil zu speichern.


>[!NOTE]
>
> Sie können das benutzerdefinierte DITA-Profil als Paket exportieren und auf die anderen AEM Guides-Instanzen hochladen, um Zeit zu sparen. Weitere Informationen finden Sie unter [Anhang.md](appendix.md).
