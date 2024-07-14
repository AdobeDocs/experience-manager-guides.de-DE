---
title: Verwenden einer benutzerdefinierten DITA-OT- und DITA-Spezialisierung
description: Erfahren Sie, wie Sie benutzerdefinierte DITA-OT- und DITA-Spezialisierung verwenden.
exl-id: 4d3e0fc1-b684-44f9-ab0d-411033024019
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 0%

---

# Verwenden einer benutzerdefinierten DITA-OT- und DITA-Spezialisierung {#id181GAJ0005Z}

Das DITA Open Toolkit \(DITA-OT\) ist ein Satz von Java-basierten Open-Source-Tools, die die Verarbeitung von DITA-Maps und Themeninhalten ermöglichen. Mit AEM Guides können Sie benutzerdefinierte DITA-OT-Plug-ins einfach importieren und verwenden. Nach dem Import kann AEM Guides so konfiguriert werden, dass das benutzerdefinierte DITA-OT-Plug-in verwendet wird, um Ausgaben in jedem beliebigen Format zu generieren. Wählen Sie zum Zeitpunkt der Generierung der Ausgabe einfach die DITA-OT-Option aus und die AEM Guides verwendet das benutzerdefinierte DITA-OT-Plug-in, um die erforderliche Ausgabe zu generieren.

Wenn Sie Ant-Parameter beim Veröffentlichen einer Ausgabe verarbeiten möchten, können Sie dies mit AEM Guides einfach tun. Sie können angeben, welche Ant-Parameter Sie verwenden möchten und dieselben dann vom Veröffentlichungsprozess verarbeitet werden.

>[!NOTE]
>
> AEM Guides wird mit DITA-OT Version 3.3.2 ausgeliefert. AEM Guides unterstützt jedoch die DITA-OT-Version 1.7 und höher. Die vollständige Liste der DITA-OT-Versionen finden Sie unter [DITA-OT-Versionen](http://www.dita-ot.org/download).

>[!TIP]
>
> In den Abschnitten *DITA-OT-Profilkonfiguration* und *Verwenden benutzerdefinierter DITA-OT* des Best Practices-Handbuchs finden Sie Best Practices zur Verwendung benutzerdefinierter DITA-OT-Plug-ins.

## Verwenden benutzerdefinierter DITA-OT-Plug-ins {#id181NH1020L7}

Sie können das benutzerdefinierte DITA-OT-Plug-in für die Veröffentlichung verwenden, indem Sie das benutzerdefinierte DITA-OT-Plug-in in das AEM Repository hochladen. Standardmäßig ist AEM Guides mit einem vorkonfigurierten Profil ausgestattet, das die Konfigurationen für die Standardvorlagen enthält, die zum Bearbeiten und Veröffentlichen von Inhalten verwendet werden sollen. Sie können benutzerdefinierte Profile mit benutzerdefinierten Vorlagen erstellen, die beim Bearbeiten von Dokumenten und benutzerdefinierten DITA-OT-Plug-ins zum Veröffentlichen von Inhalten verwendet werden.

Das DITA-OT-Standardpaket, das mit AEM Guides verfügbar ist, enthält den Apache FOP XSL-FO-Prozessor, der das Rendering von MathML-Gleichungen nicht unterstützt. Wenn Sie MathML-Gleichungen in Ihrem Inhalt verwenden, stellen Sie sicher, dass Sie ein MathML-Rendering-Engine-Plug-in für Apache FOP integriert haben oder einen anderen XSL-FO-Prozessor verwenden.

Führen Sie die folgenden Schritte aus, um das benutzerdefinierte DITA-OT-Plug-in in das AEM-Repository hochzuladen:

1. Laden Sie die Datei DITA-OT.zip aus dem Link herunter, der in der Begrüßungs-E-Mail freigegeben ist.

1. Extrahieren Sie den Inhalt der ZIP-Datei auf Ihrem System.

1. Verwenden Sie einen DITA-OT-Plug-in-Integrationsmechanismus, um die neue Version von DITA-OT in Ihr benutzerdefiniertes DITA-OT-Plug-in zu integrieren.

1. Erstellen Sie die ZIP-Datei erneut und behalten Sie dabei denselben Namen \(`DITA-OT.ZIP`\) und die Ordnerstruktur bei.

1. Laden Sie die aktualisierte ZIP-Datei wieder in das AEM-Repository hoch.

   Stellen Sie vor dem Hochladen der ZIP-Datei die folgenden Prüfungen sicher:

   - Führen Sie den Integrator \(zur Installation des benutzerdefinierten Plug-ins\) auf einem Mac/Linux-Betriebssystem aus, um Probleme mit Dateiseparatoren zu vermeiden. Da Windows und Linux OS unterschiedliche Dateiseparatoren haben, ist das in Mac/Linux OS integrierte Plug-in sowohl mit dem Windows- als auch dem Linux-Setup kompatibel.
   - Stellen Sie sicher, dass die Datei `DITA-OT.ZIP` einen Ordner mit dem Namen &quot;DITA-OT&quot;enthält, der alle relevanten Plug-ins und Dateien enthält.
   - Überprüfen Sie, ob die von Ihnen erstellte `DITA-OT.ZIP`-Datei mimeType: &quot;nt:file&quot; \(dies entspricht dem primären Typ der ZIP-Datei beim Hochladen in AEM\). Verwenden Sie ein WebDAV-Tool oder eine Codebereitstellung, um diese ZIP-Datei in den gewünschten Pfad in AEM hochzuladen. \(Verwenden Sie AEM Package Manager nicht, um diese ZIP-Datei bereitzustellen, da diese ZIP kein AEM Inhaltspaket, sondern nur eine Archivdatei ist.\)

   >[!NOTE]
   >
   > Es wird empfohlen, das standardmäßige DITA-OT-Paket nicht zu überschreiben. Sie sollten Ihr benutzerdefiniertes DITA-OT-Paket hochladen, das Ihr Plug-in /var/dxml/dita\_resources/dita-ot-Ordner enthält. Sie können dies auch über die Cloud Manager-Pipeline tun. Weitere Informationen finden Sie unter [Bereitstellen in AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=de) in AEM Dokumentation.

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
   | Profilextraktionspfad | *\(Optional\)* Geben Sie den Pfad an, unter dem DITA-OT auf der Festplatte aufbewahrt wird. Standardmäßig bündelt AEM Guides ein DITA-OT-Paket in seinem Repository und wird unter diesem Pfad auf dem Datenträger extrahiert. <br> **HINWEIS** Sie können diesen Pfad mit einer beliebigen vorhandenen Systemvariable oder -eigenschaft definieren. Weitere Informationen finden Sie in der Beschreibung der Eigenschaft [DITA-OT-Umgebungsvariablen](#id181NH0YN0AX) . |
   | Zugewiesener Pfad | \(*Optional*\) Geben Sie den Pfad im Inhalts-Repository an, für den dieses Profil gilt. Sie können mehrere Orte angeben. |
   | **DITA-OT-Eigenschaften** |
   | DITA-OT-Timeout | \(*Optional*\) Geben Sie die Zeit \(in Sekunden\) an, für die die AEM Guides auf eine Antwort vom DITA-OT-Plug-in wartet. Wenn keine Antwort in der angegebenen Zeit empfangen wurde, beendet AEM Guides die Veröffentlichungsaufgabe und die Aufgabe wird als fehlgeschlagen gekennzeichnet. Außerdem werden die Fehlerprotokolle in der Protokolldatei zur Generierung der Ausgabe verfügbar gemacht. <br> Standardwert: 300 Sekunden \(5 Minuten\) |
   | DITA-OT-PDF-Argumente | Geben Sie die Befehlszeilenargumente an, die vom benutzerdefinierten DITA-OT-Plug-in zum Generieren der PDF-Ausgabe verarbeitet werden. Geben Sie für alle benutzerdefinierten DITA-OT-Profile das folgende Befehlszeilenargument an:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | DITA-OT AEM Arguments | \(*Optional*\) Geben Sie die benutzerdefinierten Befehlszeilenargumente an, die vom benutzerdefinierten DITA-OT-Plug-in zum Generieren der AEM Site-Ausgabe verarbeitet werden. |
   | DITA-OT-Bibliothekspfade | \(*Optional*\) Geben Sie die zusätzlichen Bibliothekspfade des DITA-OT-Plug-ins an. |
   | DITA-OT Build XML | \(*Optional*\) Geben Sie den Pfad des benutzerdefinierten Ant-Build-Skripts an, das mit dem angepassten DITA-OT-Plug-in verknüpft ist. Dieser Pfad ist relativ zum DITA-OT-Ordner auf Ihrem Dateisystem. |
   | DITA-OT Ant Script-Ordner | \(Optional\) Geben Sie den Pfad des Skriptordners DITA-OT Ant an. Dieser Pfad ist relativ zum DITA-OT-Ordner auf Ihrem Dateisystem. |
   | DITA-OT-Umgebungsvariablen | *\(Optional\)* Geben Sie Umgebungsvariablen an, die an den DITA-OT-Prozess weitergegeben werden sollen. Standardmäßig fügt die AEM Guides vier Variablen hinzu: `ANT_OPTS`, `ANT_HOME`, `PATH` und `CLASSPATH`. <br> Sie können alle vorhandenen Systemumgebungsvariablen oder Eigenschaften zum Erstellen neuer Umgebungsvariablen wiederverwenden. Wenn Sie beispielsweise die Systemvariable `JAVA_HOME` in Ihrem System definiert haben und eine neue Umgebungsvariable mit dem Namen `JAVA_BIN` definieren möchten, die mit `JAVA_HOME` erstellt wird. Anschließend können Sie die Definition von `JAVA_BIN` wie folgt hinzufügen:`JAVA_BIN= ${JAVA_HOME}/bin` <br> **Hinweis:** Sie können auch Java-Systemeigenschaften verwenden, um Umgebungsvariablen zu erstellen. Wenn AEM Startskript beispielsweise die Java-Systemeigenschaft `java.io.tmpdir` für einen temporären Ordner definiert, können Sie mit dieser Eigenschaft eine neue Variable wie folgt definieren: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Wichtig:** Um eine vorhandene Systemvariable oder -eigenschaft wiederzuverwenden, muss sie in `${}` eingeschlossen sein. |
   | DITA-OT-Ausgabe überschreiben | Wählen Sie aus, ob die DITA-OT-Ausgabe überschrieben werden soll. Lassen Sie diese Option aktiviert. |
   | DITA-OT-ZIP-Pfad AEM | Geben Sie den vollständigen Pfad an, in dem die benutzerdefinierte DITA-OT.zip-Datei in Ihrem AEM-Repository gespeichert ist. |
   | DITA-OT-Plug-in-Pfad | Pfad des benutzerdefinierten Plug-ins. Dieses Plug-in wird automatisch in das Haupt-DITA-OT-Paket integriert. |
   | Kataloge integrieren | \(*Optional*\) Pfad der benutzerdefinierten DTD- und XSD-catalog.xml-Dateien im AEM-Repository. Dies sollte nur bereitgestellt werden, wenn die Kataloge im DITA-OT-Paket fehlen. Diese Kataloge werden automatisch als Plug-in in das DITA-OT integriert. |
   | System-ID-Katalog hinzufügen | \(*Optional*\) Wählen Sie diese Option nur aus, wenn im Katalog fehlende Öffentliche ID-Einträge vorhanden sind oder die DITA-Dateien nur die System-IDs verwenden, die relativ zum Serverpfad sind, von dem aus sie hochgeladen werden. |
   | Temporärer DITA-OT-Pfad | Ein temporärer Speicherort, an den DITA-Dateien zur Verarbeitung kopiert werden. Bevor DITA-OT Dateien verarbeitet, werden sie an diesen temporären Speicherort kopiert. Standardmäßig lautet der temporäre Speicherort: <br> `<*AEM-Install*>/crx-quickstart/profiles/ditamaps` <br> **Wichtig:** Sie dürfen den Standardpfad nicht ändern. |

   >[!NOTE]
   >
   > Das AEM Guides-Installationsprogramm erstellt zwei Umgebungsvariablen, mit denen Sie den Pfad der benutzerdefinierten DITA-OT-Plug-in-Dateien angeben können. Diese Umgebungsvariablen sind: `DITAOT\_DIR`, der den Pfad des DITA-OT-Ordners im Dateisystem enthält, und `DITAMAP\_DIR`, der den Pfad enthält, in den der DITA-Map-Inhalt im Dateisystem extrahiert wird.

1. Klicken Sie auf **Fertig** , um das Profil zu speichern.


## Integrieren der DITA-Spezialisierung {#id211MB0E00XA}

Bei der DITA-Spezialisierung werden neue DITA-Strukturen erstellt, indem neue Elemente hinzugefügt oder vorhandene Elemente entfernt werden. Um ein neues DITA-Element zu erstellen, können Sie ein vorhandenes DITA-Element als Grundlage nehmen und es gemäß Ihren Authoring-Anforderungen ändern. Im Wesentlichen ermöglicht Ihnen die DITA-Spezialisierung die Erstellung benutzerdefinierter Informationsmodelle, die Ihren Geschäftsanforderungen entsprechen und gleichzeitig die Vorteile der vorhandenen DITA-Architektur erhalten.

Sie können die Profilfunktion verwenden, um benutzerdefinierte DITA-Spezialisierungseinstellungen zu speichern. Diese Einstellungen können dann zum Zeitpunkt der Bearbeitung und Veröffentlichung von benutzerdefinierten DITA-Inhalten verwendet werden. Mit AEM Guides können Sie die öffentliche ID und die System-ID in Ihren benutzerdefinierten DTDs/XSDs verwenden.

>[!NOTE]
>
> AEM Guides Web Editor unterstützt keine XSDs.

Führen Sie die folgenden Schritte aus, um ein neues Profil zu erstellen und es so zu konfigurieren, dass spezialisierte DTDs und XSDs in Ihrer AEM Guides verwendet werden:

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

   `/var/dxml/dita_resources`

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die Kachel **DITA-Profile** .

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
