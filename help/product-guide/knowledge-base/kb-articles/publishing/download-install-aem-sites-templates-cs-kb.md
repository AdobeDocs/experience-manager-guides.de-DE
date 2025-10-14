---
title: Herunterladen und Installieren von AEM Sites-Vorlagen für Cloud-Services
description: Erfahren Sie, wie Sie AEM Sites-Vorlagen für Cloud-Services herunterladen und installieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: 1cec8975e8aad56184793a023d066aa467d8cec5
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 1%

---

# Herunterladen und Installieren von AEM Sites-Vorlagen (Cloud-Services)

Dieses Handbuch enthält Schritt-für-Schritt-Anweisungen zum Einrichten und Konfigurieren der neuesten AEM Guides-Vorlage für das Generieren von AEM Sites-Seiten in einer Cloud-Umgebung. Führen Sie diese Schritte aus, um die erforderlichen Pakete zu installieren, Voreinstellungen zu erstellen und zu konfigurieren und AEM Sites zu generieren.

## Voraussetzungen

Bevor Sie mit der Einrichtung fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- **Adobe Experience Manager (AEM) Cloud**: Eine laufende Instanz von **AEM as a Cloud Service** mit **AEM Guides 2502 oder höheren Versionen**.

- **Erforderliche Berechtigungen**: Sie müssen über die folgenden Berechtigungen verfügen:

   - Zugriff auf **Cloud Manager**, um Pakete bereitzustellen.
   - Zugriff auf **Git-Repository** in Verbindung mit Ihrer Umgebung.
   - Berechtigungen zum Erstellen und Ändern von Vorgaben in AEM Guides.

- **Pakete herunterladen**: Laden Sie die folgenden Pakete vom Software Distribution-Portal herunter:

   - Komponentenpaket: guides-components.all-1.x.0.zip
   - Sites-Vorlage: aemg-docs-1.x.0.zip

## Paketinstallation über die Cloud-Bereitstellung

Installieren Sie das **Komponentenpaket (guides-components.all-1.x.x.zip)** und führen Sie die folgenden Schritte aus

1. **Git-Repository klonen:**
   1. Navigieren Sie **linken Bedienfeld** Cloud Manager zu „Repositorys“.
   2. Wählen Sie **Auf Repository-Informationen zugreifen** und kopieren Sie den Git-Klon-Befehl.

      ![Auf Repository-Informationen zugreifen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350" align="left"}

   3. Klonen Sie das Repository auf Ihrem lokalen System mit dem angegebenen Benutzernamen und Kennwort (generieren Sie ggf. ein Kennwort).
2. **Paket zum Maven-Bundle hinzufügen:**
   1. Erstellen Sie in Ihrem lokal geklonten Repository ein neues Maven-Bundle oder fügen Sie es einem vorhandenen hinzu.
   2. Stellen Sie sicher, dass die Struktur /jcr_root/apps/fmdita/install im Maven-Projekt vorhanden ist.

      ![Struktur im Maven-Projekt](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650" align="left"}


   3. Platzieren Sie die heruntergeladene Datei „guides-components.all-1.x.x.zip“ im Installationsordner.

3. **Filter.xml aktualisieren:**

   1. Öffnen Sie die Datei „filters.xml“ im Ordner „META-INF“ des übergeordneten Inhaltsverzeichnisses.
   2. Fügen Sie den folgenden Filter hinzu: filter root=&quot;/apps/fmdita“ mode=„merge“/


      ![Filter hinzufügen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650" align="left"}


4. **Konfigurieren Sie pom.xml:** Aktualisieren Sie die Datei „pom.xml“ entsprechend Ihren Umgebungsanforderungen.
5. **Änderungen pushen und Pipeline ausführen:**
   1. Übertragen Sie die Änderungen in das Git-Haupt-Repository.
   2. Navigieren Sie zu **Pipelines** in Cloud Manager und führen Sie die Pipeline für die gewünschte Umgebung aus.
6. **Installation überprüfen:** Sobald die Bereitstellung abgeschlossen ist, wird das Komponentenpaket in der AEM Cloud-Umgebung installiert.

## Erstellen einer Site mit installierten Vorlagen

1. **Site-Vorlage importieren:**
   1. Navigieren Sie zur AEM Sites-Seite (servername/sites.html/content).
   2. Wählen Sie **Vorlage** Erstellen > **Site** aus.
   3. Importieren Sie die Sites-Vorlage aemg-docs-1.x.x.zip mit der Option **Importieren**.
2. **Vorlage auswählen:** Wählen Sie **AEMG Docs 1.x.x** aus und klicken Sie dann auf **Weiter**.
3. **Site-Details eingeben:** Geben Sie den **Site-Titel** und **Site-Name** ein.

   ![Erstellen einer Website](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350" align="left"}

4. Wählen Sie **Erstellen** aus.

## Erstellen einer AEM-Site-Voreinstellung

1. **Neue Vorgabe erstellen:**
   1. Öffnen Sie eine DITA-Zuordnung in AEM Guides und navigieren Sie zum Bedienfeld **Ausgabe** .
   2. Wählen Sie **Voreinstellung erstellen** aus.
   3. Wählen Sie den Typ als **AEM Sites**.
   4. Geben Sie einen Namen für die Voreinstellung ein.
   5. Deaktivieren Sie die Einstellung **Veraltete Komponentenzuordnung verwenden**.

      ![Neue AEM-Site-Voreinstellung erstellen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-output-preset.png){width="350" align="left"}

   6. Wählen Sie **Hinzufügen** aus, um die Voreinstellung zu erstellen.
2. **AEM-Site-Voreinstellung konfigurieren** Es gibt zwei Optionen, um die vordefinierte Site zu konfigurieren:

   **Option 1: Verwenden Sie das Dropdown-Menü der Site**

   1. Wählen Sie **Site** als die oben erstellte aus (z. B. AEMG Docs Site).
   2. Stellen Sie sicher **dass die Vorlagen „Veröffentlichungspfad** und **Themenseite** automatisch auf Folgendes festgelegt sind:
      - Veröffentlichungspfad: /content/AEMG-Docs-Site/en/docs/product
      - Themenseitenvorlage: Themenseite

      ![Verwenden Sie das Dropdown-Menü der Site, um die AEM-Site zu konfigurieren](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

   **Option 2: Verwenden des Site-Pfads**

   1. Legen Sie **Site-Pfad** manuell als &quot;/content/AEMG-Docs-Site/en/docs/product“ fest.
   2. Stellen Sie sicher, **die Vorlage** Themenseite) automatisch auf Themenseite eingestellt ist.

      ![Verwenden Sie den Site-Pfad, um die AEM-Site zu konfigurieren](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

3. **Voreinstellung speichern:** Speichern Sie die an der Voreinstellung vorgenommenen Änderungen.

## AEM Sites generieren

1. **Website generieren:**
   1. Generieren Sie bei konfigurierter Vorgabe die AEM-Site für die entsprechende DITA-Zuordnung.
   2. Die generierte Site ist unter dem Pfad verfügbar: /content/AEMG-Docs-Site/en/docs/product.
2. **Standardgenerierungspfad ändern (optional):** Wenn Sie den Standardpfad für die Site-Generierung ändern möchten, führen Sie die folgenden Schritte aus:
   1. Navigieren Sie zu **AEM Sites**.
   2. Erstellen Sie eine neue Produktseite unter der vorkonfigurierten Site-Struktur.
   3. Navigieren Sie zu **AEMG-** > **Englisch** > **Docs**.

      ![Seite erstellen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650" align="left"}

   4. Wählen Sie die Kachel **Startseite** und dann **Weiter** aus.

      ![Home-Kachel auswählen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650" align="left"}

   5. Geben Sie **(Titel** und **Name** für die Seite ein.
   6. Wählen Sie **Erstellen** aus.

>[!NOTE]
>
> Stellen Sie sicher, dass alle Konfigurationen in einer Nicht-Produktionsumgebung getestet werden, bevor Sie sie in der Produktion bereitstellen. <br><br> Informationen finden Sie in der offiziellen [Dokumentation &#x200B;](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/implementing/deploying/overview) Bereitstellung für AEM as a Cloud Service&quot;.
