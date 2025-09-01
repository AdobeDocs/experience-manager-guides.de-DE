---
title: Anpassen vorhandener AEM-Site-Vorlagen für AEM Guides
description: Erfahren Sie, wie Sie vorhandene AEM-Site-Vorlagen für AEM Guides anpassen
feature: Installation
role: Admin
level: Experienced
source-git-commit: 1cec8975e8aad56184793a023d066aa467d8cec5
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 1%

---

# Anpassen vorhandener AEM-Site-Vorlagen für AEM Guides

Dieses Handbuch enthält schrittweise Anweisungen zum Anpassen vorhandener AEM-Site-Vorlagen für die Verwendung mit AEM Guides, um AEM Sites aus DITA-Zuordnungen und -Themen zu generieren.

Wenn Sie die vordefinierte Vorlage für AEM Guides (AEMG Docs) verwenden, sind die Konfigurationen und Komponenten bereits vorhanden und können unverändert zur Veröffentlichung Ihrer AEM Guides-Inhalte verwendet werden. Wenn Sie jedoch Ihre vorhandenen AEM Sites-Vorlagen mit benutzerdefiniertem Branding verwenden möchten, um AEM Guides-Inhalte zu veröffentlichen, führen Sie die folgenden Schritte aus, um Ihre Sites-Vorlagen an den AEM Guides-Rendering-Anforderungen auszurichten.


## Voraussetzungen

- Sie verfügen über die entsprechenden Berechtigungen und Zugriffsrechte für AEM-Vorlagen.
- Bearbeitbare AEM-Vorlagen und die AEM-Site-Struktur sind Ihnen bekannt.
- Sie haben eine vorhandene Site-Hierarchie, die mit bearbeitbaren Vorlagen erstellt wurde.
- Sie haben mindestens zwei Vorlagen aus Ihrem vorhandenen Projekt:

   - **Dokumentations-Container** Seitenvorlage: Wird zum Rendern der DITA-Zuordnung als Dokumentationsstamm verwendet.
   - **Themenseitenvorlage:** zum Rendern einzelner DITA-Themenseiten.

## Überlegungen zur Benennung von Vorlagen

Vorlagennamen variieren je nach Projekt-Setup. Beispielsweise in der OOTB-Konfiguration für AEM-Dokumente:

- Dokumentations-Container-Seite: /conf/AEMG-Docs-Site/settings/wcm/templates/kb-content

- Themenseite: /conf/AEMG-Docs-Site/settings/wcm/templates/topic-content

**Anpassung:** Der Anpassungsprozess umfasst zwei wichtige Schritte:

1. Vorlageneinrichtung: Identifizieren und konfigurieren Sie die beiden Vorlagen (Container und Thema).
2. Render Guides-Komponenten: Betten Sie erforderliche AEM Guides-Komponenten ein, um Funktionen wie Inhaltsverzeichnis, Navigation und Metadatenanzeige zu aktivieren.

## Vorlageneinrichtung

Wählen Sie zwei bearbeitbare Vorlagen aus Ihrer AEM-Site aus und konfigurieren Sie sie.

### Dokumentations-Container-Seitenvorlage

Die Vorlage Dokumentations-Container-Seite wird verwendet, um die Produktdokumentations-Container-Seite zu erstellen, die den Inhalt einer DITA-Zuordnung rendert.

- Es dient als Einstiegspunkt oder Homepage für eine bestimmte Dokumentation (z. B. ein Produkthandbuch oder ein Handbuch).
- Fügen Sie die Eigenschaft id=„category-page“ zum jcr:content des ursprünglichen Knotens der Vorlage hinzu. Dadurch wird sichergestellt, dass alle aus dieser Vorlage erstellten Seiten von AEM Guides automatisch als Dokumentations-Container behandelt werden.

  ![Hinzufügen von id=„category-page“](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-id-category-page.png){width="650" align="left"}

- Fügen Sie eine Text -Komponente mit der obligatorischen Eigenschaft hinzu: text=&quot;$category.html$&quot;.

  ![Hinzufügen der Textkomponente](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component.png){width="650" align="left"}

- enthält in der Regel Navigationselemente wie Links zu Abschnitten oder Themen in der Dokumentation.
- Sie kann angepasst werden, um Branding, Kopf- und Fußzeilen sowie andere Design-Elemente einzuschließen.

**Anwendungsbeispiel:**
Wenn Sie eine DITA-Karte für ein Produkthandbuch haben, generiert die Dokumentations-Container-Seitenvorlage die Homepage für dieses Handbuch, mit einer Übersicht und Links zu einzelnen Themen.

### Themenseitenvorlage

- Die **Themenseitenvorlage** wird zum Erstellen von Seiten für einzelne **DITA-Themen** verwendet.
- Jedes Thema in einer DITA-Zuordnung wird mithilfe dieser Vorlage als separate Seite gerendert.
- Enthält eine **Textkomponente** mit der obligatorischen Eigenschaft: text=&quot;$topic.content$&quot;.

  ![Hinzufügen der Textkomponente mit der obligatorischen Eigenschaft](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-text-component-mandatory-property.png){width="650" align="left"}

- Dieser Platzhalter wird während der Site-Erstellung durch den tatsächlichen Inhalt des DITA-Themas ersetzt.
   - Die Textkomponente wird normalerweise innerhalb einer **Container-Komponente“ platziert** um ein ordnungsgemäßes Layout und Formatieren sicherzustellen.
   - Kann angepasst werden, um konsistente Kopfzeilen, Fußzeilen und Navigationselemente über alle Themenseiten hinweg einzuschließen.

**Anwendungsbeispiel:**
Wenn Sie ein DITA-Thema über „Installationsanweisungen“ haben, generiert die Themenseitenvorlage eine Seite mit dem Inhalt dieses Themas.

**Container-Komponente:**

![Container-Komponente hinzufügen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-component.png){width="650" align="left"}

>[!NOTE]
>
> Stellen Sie sicher, dass Komponenten, :resourceType Sling unter wcm/foundation/components verwenden, in die entsprechenden Kern-/wcm/components migriert werden.

Fügen Sie dieselbe Komponente (Container- und Textkomponente) in die Struktur derselben Vorlage ein:

![Container- und Textkomponente hinzufügen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-container-and-text-component.png){width="650" align="left"}

## Wiedergeben von Handbüchern in Komponenten in benutzerdefinierten Vorlagen

Um AEM Guides-Kernkomponentenfunktionen wie Inhaltsverzeichnis, Seitenumleitung, Navigation und Metadatenanzeige zu aktivieren, müssen Sie bestimmte AEM Guides-Komponenten in Ihre benutzerdefinierten Vorlagen aufnehmen. Diese Komponenten müssen den entsprechenden bearbeitbaren Vorlagen (Dokumentations-Container oder Themenseite) explizit hinzugefügt werden, um sicherzustellen, dass die beabsichtigte Funktionalität während der Site-Erstellung und -Laufzeit verfügbar ist.

In der folgenden Tabelle finden Sie die Liste der Komponenten und ihre Verwendung:

| Funktion | Komponentenname | Beschreibung | Empfohlene Vorlage |
|---|---|---|---|
| Inhaltsverzeichnis | guideSideNavigation | Rendert das vollständige Inhaltsverzeichnis aus der DITA-Zuordnung | Dokumentations-Container |
| Seitenumleitung | childDirect | Leitet zur ersten Themenseite in der Karte weiter | Dokumentations-Container |
| Mini-Inhaltsverzeichnis | Minitoc | Zeigt das Inhaltsverzeichnis für das aktuelle Thema an | Themenseite |
| Zuletzt aktualisiert | pageProperty | Zeigt das Datum der letzten Änderung an | Themenseite |
| Pager | Pager | Ermöglicht die Navigation zwischen den vorherigen und nächsten Themenseiten | Themenseite |
| Sprachnavigation | languageNavigation | Ermöglicht den Wechsel zwischen verschiedenen Sprachversionen | Beide Vorlagen |


## Anwendungsfälle für Komponenten

- **Umleitungs-Komponente (untergeordnete Umleitung):** Fügen Sie diese zur Dokumentations-Container-Seitenvorlage hinzu, damit die aus der DITA-Zuordnung generierte Produkt-Startseite automatisch zur ersten Themenseite umgeleitet wird. Wenn Ihre Dokumentations-Container-Seite als eigenständige Homepage mit benutzerdefinierten Komponenten und Layout fungieren soll, ist diese Komponente nicht erforderlich.

- **Inhaltsverzeichnis (guideSideNavigation):** Fügen Sie dies zur Themenseitenvorlage hinzu, um ein navigierbares Inhaltsverzeichnis neben dem Themeninhalt zu rendern. Das Inhaltsverzeichnis wird aus der DITA-Zuordnung abgeleitet und hilft Benutzenden, durch gleichrangige Themen zu navigieren.


## Aktivieren von Handbüchern und Client-Bibliotheken

Standardmäßig werden die im AEM Guides-Komponentenpaket bereitgestellten Client-Bibliotheken (clientlibs) nicht auf benutzerdefinierte Vorlagen angewendet. So aktivieren Sie sie:

1. **Bearbeiten Sie die Vorlage:**

   1. Öffnen Sie die **Produktseite** im **Editor-Modus**.
   2. Wählen Sie **Vorlage bearbeiten** aus. Dadurch wird eine URL wie conf/settings/wcm/templates/structure.html geöffnet.

      ![Vorlage bearbeiten](/help/product-guide/knowledge-base/kb-articles/assets/publishing/edit-template.png){width="650" align="left"}

2. **Seitenrichtlinie aktualisieren:**

   1. Navigieren Sie zur Schaltfläche **Seiteninformationen** und wählen Sie **Seitenrichtlinie** aus.
   2. Fügen Sie die folgenden Client-Bibliotheken hinzu:
      - **Client-Bibliotheken**
      - **JavaScript-Seitenkopf der Client-Bibliotheken**

3. **Änderungen speichern** Speichern Sie die Vorlage, nachdem Sie die erforderlichen Client-Bibliotheken hinzugefügt haben.

   ![Client-Bibliotheken hinzufügen](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-client-libraries.png){width="650" align="left"}


>[!NOTE]
>
> Stellen Sie sicher, dass die Vorlagen in einer Nicht-Produktionsumgebung getestet werden, bevor Sie sie in der Produktion bereitstellen.<br><br>Weitere Informationen finden Sie in der offiziellen [AEM Guides](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/overview)- und [AEM Sites](https://experienceleague.adobe.com/de/docs/experience-manager-core-components/using/get-started/authoring)-Dokumentation.
