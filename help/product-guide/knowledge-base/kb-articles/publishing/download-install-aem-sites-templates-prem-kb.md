---
title: Herunterladen und Installieren von AEM Sites-Vorlagen für On-Premise-Services
description: Erfahren Sie, wie Sie AEM Sites-Vorlagen für On-Premise-Services herunterladen und installieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: 20ba7f4582f1d155e555c9ff3ac58e1e3c400765
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Herunterladen und Installieren von AEM Sites-Vorlagen (On-Premise-Services)

Dieses Handbuch enthält schrittweise Anweisungen zum Einrichten und Konfigurieren der neuesten AEM Guides-Vorlage für die Generierung von AEM Sites. Führen Sie diese Schritte aus, um die erforderlichen Pakete zu installieren, Voreinstellungen zu erstellen und zu konfigurieren und AEM Sites zu generieren.

## Voraussetzungen

Bevor Sie mit der Einrichtung fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- **Adobe Experience Manager (AEM):** Eine laufende Instanz von **AEM 6.5** mit **Service Pack** 21, 20 und 19 und **AEM Guides 4.6.0** oder höheren Versionen.

- **Erforderliche Berechtigungen**: Stellen Sie sicher, dass Sie über die folgenden Berechtigungen verfügen:

   - Zugriff auf **Software Distribution-Portal** zum Herunterladen der erforderlichen Pakete
   - Zugriff auf **CRX Package Manager**, um Pakete in AEM zu installieren.
   - Berechtigungen zum Erstellen und Ändern von Vorgaben in AEM Guides.

- **Pakete herunterladen**: Laden Sie die folgenden Pakete vom **Software Distribution-Portal** herunter:

   - Komponentenpaket: on-prem-guides-components.all-1.x.0.zip
   - Sites-Paket: aemg-docs.all-1.x.0.zip

## Paketinstallation mit CRX Package Manager

1. **Installieren des Komponentenpakets:**
   1. Navigieren Sie zu [**CRX Package Manager**](http://<your-aem-instance>/crx/packmgr).
   2. Laden Sie das Paket on-preme-guides-components.all-1.x.0.zip hoch und installieren Sie es.

2. **Installieren Sie das Sites-Paket:** Laden Sie das Paket aemg-docs.all-1.x.0.zip hoch und installieren Sie es mit dem CRX Package Manager.


## Erstellen und Konfigurieren von AEM-Site-Voreinstellungen

1. **Neue Vorgabe erstellen:**
   1. Öffnen Sie eine DITA-Zuordnung in AEM Guides und navigieren Sie zum Bedienfeld **Ausgabe** .
   2. Wählen Sie **Voreinstellung erstellen** aus.
   3. Wählen Sie den Typ als **AEM Sites**.
   4. Geben Sie einen Namen für die Voreinstellung ein.
   5. Deaktivieren Sie die Einstellung **Veraltete Komponentenzuordnung verwenden**.
   6. Wählen Sie **Hinzufügen** aus, um die Voreinstellung zu erstellen.

      ![Dialogfeld „Neue Ausgabevorgabe“](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}


2. **AEM-Site-Voreinstellung konfigurieren** Es gibt zwei Optionen, um die vordefinierte Site zu konfigurieren:

   **Option 1: Verwenden Sie das Dropdown-Menü der Site**

   1. Wählen Sie **Site** als **AEMG Docs** aus.
   2. Stellen Sie sicher **dass „Veröffentlichungspfad** und **Themenseitenvorlage** automatisch auf Folgendes festgelegt sind:
      - Veröffentlichungspfad: aemg-docs/en/docs/product1
      - Themenseitenvorlage: Themenseite.

      ![Site-Dropdown verwenden](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

   **Option 2: Verwenden des Site-Pfads**

   1. Legen Sie **Site-Pfad** manuell als &quot;/content/aemg-docs/en/docs/product1“ fest.
   2. Stellen Sie sicher **dass „Themenseitenvorlage** automatisch auf Themenseite eingestellt ist.

      ![Site-Pfad verwenden](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Voreinstellung speichern:** Speichern Sie die an der Voreinstellung vorgenommenen Änderungen.

## AEM Sites generieren

1. **Website generieren:**
   1. Wenn die Vorgabe konfiguriert ist, können Sie jetzt die AEM-Site für die entsprechende DITA-Zuordnung generieren.
   2. Die generierte Site ist unter dem Pfad verfügbar: /content/aemg-docs/en/docs/product1.
2. **Standardgenerierungspfad ändern (optional):** Wenn Sie den Standardpfad für die Site-Generierung ändern möchten, führen Sie die folgenden Schritte aus:

   1. Navigieren Sie zu **AEM Sites**.
   2. Erstellen Sie eine neue Produktseite unter der vorkonfigurierten Site-Struktur.
   3. Navigieren Sie zu **AEMG-** > **Englisch** > **Docs**.

      ![Seite in der AEM Site-Struktur erstellen ](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

   4. Wählen Sie die Kachel **Startseite** und dann **Weiter** aus.

      ![Startseitenkachel auswählen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

   5. Geben Sie **(Titel** und **Name** für die Seite ein.
   6. Wählen Sie **Erstellen** aus.

