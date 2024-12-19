---
title: Herunterladen und Installieren von AEM Sites-Vorlagen
description: Erfahren Sie, wie Sie AEM Sites-Vorlagen herunterladen und installieren
feature: Installation
role: Admin
level: Experienced
exl-id: ca446ee4-a377-4e08-8008-21db3a2fe669
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 0%

---

# Herunterladen und Installieren von AEM Sites-Vorlagen

Führen Sie die folgenden Schritte aus, um AEM Sites-Vorlagen für On-Premise-Software von Experience Manager Guides herunterzuladen und zu installieren:


## Package-Installation

1. Die folgenden Pakete herunterladen

   - Komponenten: [guides-components-all.zip](https://github.com/adobe/aemg-sites-components/releases/tag/v1.0.0)

   - Sites für On-Premise-Software: [Docs](https://github.com/adobe/aemg-docs/releases/tag/v1.0.0)

1. Melden Sie sich bei Ihrer AEM-Instanz an und navigieren Sie zum CRX Package Manager. Die Standard-URL für den Zugriff auf den Package Manager lautet:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

   Package Manager verwaltet die Pakete auf Ihrer lokalen AEM-Installation. Weitere Informationen zum Arbeiten mit dem Package Manager finden Sie unter [ mit Paketen ](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/package-manager.html) der AEM-Dokumentation.

1. Um das Paket hochzuladen, klicken Sie auf **Paket hochladen**.

1. Navigieren Sie im Dialogfeld **Paket hochladen** zu der Datei, die Sie in Schritt 1 heruntergeladen haben, und klicken Sie auf **OK**.

   Das Paket wird in Ihre AEM-Instanz hochgeladen.

1. Klicken Sie auf „Installieren“, um **Paket** installieren.

1. Klicken Sie **Dialogfeld „Paket installieren** auf **Installieren**, um die Pakete zu installieren.


## Konfigurieren der mit den AEM Sites-Vorgaben zu verwendenden Vorlagen

Sobald die Pakete installiert sind, wird eine Site mit dem Namen **AEMG** in der Sites-Benutzeroberfläche erstellt. Diese Beispiel-Site zeigt, wie Sie die Site-Struktur zum Generieren von AEM Sites-Ausgaben einrichten können. Das ist nur ein Beispiel. Sie können benutzerdefinierte Sites gemäß Ihren Anforderungen erstellen.

![Beispielseiten für AEMG Sites](assets/aemg-sites-sample-pages.png)


**AEMG** enthält die folgenden Komponenten.
- Im Ordner **AEMG) ist ein Ordner für die Sprache** vorhanden. Sie können ähnliche Sprachkopien gemäß Ihren Anforderungen erstellen. Eine mehrsprachige Website umfasst beispielsweise Sprachkopien in Englisch (en), Deutsch (de) und Französisch (fr).  Erfahren Sie mehr darüber, wie Sie mit dem [Sprachkopie-Assistenten“ eine Sprachkopie ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/introduction/tc-wizard).
- Innerhalb des englischen Sprachordners (en) bietet Experience Manager Guides viele vordefinierte Beispielseiten wie **Suche**, **Anmelden**, **Dokumente** und **Support**.

- **Docs** ist die Startseite der Beispieldokumentation. Es dient als zentraler Ort für alle produktbezogenen Dokumentationen
und zeigt jedes Produkt, für das Dokumentation verfügbar ist, als einzelne Kacheln an.

- Neben der Dokumentations-Startseite gibt es Beispielseiten für **Suche**, **Anmelden** und **Support**. Sie können diese Beispiele gemäß Ihren Anforderungen anpassen.
- Sie können über Startseiten für einzelne Produkte verfügen, z. B. Product1. Eine Beispielseite **Product1** befindet sich unter **Docs**, der Startseite der Dokumentation.

- Experience Manager Guides bietet außerdem die folgenden vordefinierten Vorlagen:

   - **Inhaltsseite**-Vorlage: Verwenden Sie diese Vorlage, um die Standardseiten zu erstellen, die den größten Teil des Inhalts der Produkt-Site enthalten. Sie können Text, Bilder, Videos und andere Inhaltselemente enthalten. Diese Vorlage enthält nur die Kopf- und die Fußzeile. Passen Sie sie an und verwenden Sie sie, um eine beliebige Seite gemäß Ihren Anforderungen zu erstellen. Sie können beispielsweise die Support-Seite oder die Anmeldeseite für Ihr Produkt erstellen.
   - **Startseite** Vorlage: Die Haupt-Landingpage einer Website, die eine Übersicht, wichtige Abschnitte wie die wichtigsten Elemente und Funktionen sowie Navigations-Links enthält. Beispielsweise stellt die Hauptseite eines ABC-Produkts eine Verbindung zu den anderen Inhalts- oder Funktionsseiten her.
   - **Themenseite** Vorlage: Die Seiten, die zum Organisieren und Darstellen von themenbasierten Inhalten verwendet werden. Beispielsweise enthält ein Benutzerhandbuch verschiedene Themenseiten, von denen jede ein spezifisches Thema im Zusammenhang mit Funktionen und Fehlerbehebung enthält.

  ![Sites-Vorlage](assets/sites-ui-templates.png)

Verwenden Sie diese Beispiele und Vorlagen, um Ihre AEM Sites-Ausgaben zu generieren:
- Eine Produkt-Startseite entspricht einer Zuordnungs-Startseite und wird mithilfe der Startseitenvorlage erstellt. Wählen Sie diesen Pfad in der AEM Sites-Voreinstellung aus, um den Inhalt der Zuordnung darunter zu veröffentlichen. Die Produkt-Startseite kann andere Startseiten enthalten.
- Sie haben beispielsweise ein Produkt wie Experience Manager Guides und benötigen drei Handbücher für Benutzer, Administratoren und Entwickler.  Erstellen Sie für jedes Handbuch mithilfe der Startseitenvorlage eine Startseite und wählen Sie dann die entsprechende Startseite in der AEM Sites-Ausgabevorgabe aus.

Erfahren Sie mehr darüber, wie Sie [AEM Sites-Vorgaben im Web-Editor erstellen und konfigurieren](../user-guide/generate-output-aem-site-web-editor.md).

## Erstellen einer Startseite mithilfe der Vorlage

Führen Sie die folgenden Schritte aus, um die Startseite für Ihr Produkt zu erstellen:
1. Wählen Sie nach der Installation des Pakets **Sites** in der globalen Navigation aus.
1. Wählen Sie die in der Sites-Benutzeroberfläche installierte Vorlage „AEM-Dokumente“ aus.
1. Klicken Sie in der Sites **Benutzeroberfläche auf die Schaltfläche** Erstellen“ oben rechts.
1. Wählen Sie **Seite** aus dem **Erstellen** aus.
1. Wählen Sie **Startseite** und klicken Sie dann auf **Weiter**.
1. Geben Sie den Site-Titel und den Site-Namen ein und klicken **oben** auf „Erstellen“. Eine AEM-Site-Vorlage wird mithilfe der Site **Vorlage &quot;**&quot; erstellt. Sie können beispielsweise eine Startseite für Ihre `Product ABC` erstellen.


>[!NOTE]
>
>Nachdem Sie die Startseite erstellt haben, können Sie diesen Pfad als **Publish-Pfad** zum Generieren der Ausgabe Ihrer AEM Sites-Vorgaben verwenden. Zum Beispiel: `aemg-docs-en/docs/product-abc`.

## Bearbeiten von Themenvorlagen für AEM Sites

Sie können auch die Themenvorlagen für Ihre AEM Sites anpassen. Sie können den Inhalt bearbeiten oder die Eigenschaften der verschiedenen AEM-Komponenten in Ihrem Thema konfigurieren. Beispielsweise können Sie je nach Ihren Anforderungen Komponenten hinzufügen oder entfernen.\
Führen Sie die folgenden Schritte aus, um die Themenvorlagen zu bearbeiten:
1. Wählen Sie die Vorlage aus, die Sie bearbeiten möchten.
1. Wählen Sie **oben** Symbol „Bearbeiten“ aus.

Der AEM-Vorlageneditor wird geöffnet. Sie können Ihre Themenvorlage bearbeiten. Weitere Informationen zum [ von Seitenvorlagen ](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/authoring/siteandpage/templates#editing-a-template-structure-template-author).


## Anpassen bestehender AEM Sites-Vorlagen

Neben den vordefinierten Vorlagen können Sie auch Ihre vorhandenen Vorlagen mit den AEM Sites-Vorgaben verwenden. Führen Sie die folgenden Schritte aus, um bestehende AEM Sites-Vorlagen anzupassen:

### Vorlageneinrichtung

Sie benötigen die folgenden beiden Vorlagentypen:

- Kategorie- oder Landingpage-Vorlage: Diese Vorlage wird für die Landingpage der Produktdokumentation verwendet und entspricht einer DITA-Zuordnung.  Die AEM-Site-Seite für eine DITA-Zuordnung wird mithilfe dieser Vorlage generiert. Sie können diese Vorlage auf jeder Ebene verwenden.
- Hinzufügen einer Textkomponente zu einer vorhandenen Vorlage. Die Textkomponente sollte die obligatorische Eigenschaft `text="$category.html$"` aufweisen.
- Sie können beispielsweise We-Retail-Vorlagen auswählen und die Querprofilseiten-Vorlage als Landingpage-Vorlage für die DITA-Karte verwenden. Nehmen Sie dazu die Änderungen vor, wie im folgenden Screenshot gezeigt:
  ![Abschnittsseitenvorlage](assets/customize-existing-aem-templates-section.png)
   - Detailseite oder Themenseitenvorlage: Verwenden Sie diese Vorlage für den Inhalt von Themen einer Karte. Alle Sites-Seiten mit DITA/XML-Inhalten werden mithilfe von Themenseitenvorlagen erstellt. Um diese Vorlagen zu erstellen, sind zwei Voraussetzungen erforderlich:
      - Fügen Sie der Vorlage eine Textkomponente hinzu, die in einer Container-Komponente mit einer obligatorischen Eigenschaft enthalten ist. `text="$topic.content$"`.
        ![Container-Seitenvorlage](assets/customize-existing-aem-templates-container.png)
      - Spiegeln Sie denselben Container und dieselbe Textkomponente in der Struktur derselben Vorlage, wie im folgenden Screenshot gezeigt:
        ![Struktur der Container-Vorlage](assets/customize-existing-aem-templates-structure.png)

### Tag-Kategorieseite als Dokumentations-Container

Wenn für die Dokumentationsseiten mithilfe der vorherigen Vorlage eine Website-Hierarchie erstellt wird, wählen Sie eine der Kategorieseiten aus, die in dieser Website-Hierarchie erstellt wurden. Tagging der Kategorieseite als Dokumentations-Container durch Angabe einer ID.
Weisen Sie dazu seine -Eigenschaft `id` einen `category-page` Wert zu. Siehe folgenden Screenshot:

![Tag-Kategorieseite](assets/customize-existing-aem-templates-tagging.png)
