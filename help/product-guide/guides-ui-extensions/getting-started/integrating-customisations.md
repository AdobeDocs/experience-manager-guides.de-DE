---
title: Installation und Einrichtung
description: Installieren und Verwenden des AEM Guides-Erweiterungspakets
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
source-git-commit: b4d6c1c8c2d413bb4137e58391554abf2fb68b8c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# Installieren und Verwenden des AEM Guides-Erweiterungspakets

Erweiterungen bieten Ihnen die Möglichkeit, Ihre AEM Guides-App besser an Ihre Anforderungen anzupassen. Dieses Erweiterungs-Framework wird ab AEM Guides v4.3 (On-Premise) und 2310 (Cloud) unterstützt.

## Voraussetzungen

Dieses Paket erfordert [git bash](https://github.com/git-guides/install-git) und npm

## Installation

Die einfachste Möglichkeit, das AEM Guides-Framework per Bootstrapping zu installieren, ist über die Befehlszeilenschnittstelle (CLI)

```bash
npx @adobe/create-guides-extension
```

## Hinzufügen von Anpassungscode

1. Fügen Sie Code-Dateien für jede Komponente, die Sie erweitern möchten, im `src/` hinzu. Einige Beispieldateien wurden bereits für Sie hinzugefügt.
2. Jetzt in der `index.ts`-Datei im `src/` :
   - Importieren Sie die `.ts` Dateien mit den Anpassungen, die Sie in Ihrem Build hinzufügen möchten.
   - Hinzufügen der Importe zu `window.extension`
   - Registrieren des `id` der angepassten Komponente und des entsprechenden Imports nach `tcx extensions`
   - Siehe Beispiel-`/src/index.ts`

## Erstellen von benutzerdefiniertem Code

- Führen Sie `npm run build` im Stammverzeichnis aus. Sie erhalten 3 Dateien im Verzeichnis, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Ausgabe erstellen](./../imgs/build_output.png)

## Hinzufügen der Anpassung zu AEM

- Zu `CRXDE` `crx/de/index.jsp#/`
- Erstellen Sie unter dem Ordner `apps` einen neuen Knoten des Typs `cq:ClientLibraryFolder`

![Ordnerstruktur](./../imgs/crxde_folder_structure.png)

- Wählen Sie im `properties` des Knotens `Multi` fügen Sie die folgende Eigenschaft hinzu
Name: `categories`
Typ: `String []`
Wert: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

>[!NOTE]
>
> Für die vorletzte Benutzeroberfläche wären die Werte: `apps.fmdita.penultimate.xml_editor.page_overrides` und `apps.fmdita.review_overrides`


![Ordnereigenschaften](./../imgs/crxde_folder_properties.png)

- Um das erstellte JS hinzuzufügen, erstellen Sie eine neue Datei, z. B. `tcx1.js` im oben erstellten Knoten. Fügen Sie hier den Code aus `dist/guides-extension.umd.cjs` oder `dist/guides-extension.js` hinzu. Erstellen Sie nun eine neue Datei `js.txt`, hier fügen wir den Namen unserer js-Datei hinzu, der in diesem Fall wie folgt lautet:

```t
#base=.
tcx1.js
```

- Um das erstellte CSS hinzuzufügen, erstellen Sie eine neue Datei, z. B. `tcx1.css` im oben erstellten Knoten. Fügen Sie hier den Code aus `dist/build.css` hinzu. Erstellen Sie nun eine neue Datei `css.txt`, hier fügen wir den Namen unserer CSS-Datei hinzu, der in diesem Fall wie folgt lautet:

```t
#base=.
tcx1.css
```

- Führen Sie einen `shift + refresh` aus, um die App mit den Anpassungen zu laden!

## Fehlerbehebung

Überprüfen Sie, ob alle oben genannten Schritte korrekt ausgeführt wurden.
Nachdem Sie Ihren Code zu tcx.js hinzugefügt haben, führen Sie eine harte Aktualisierung durch (Umschalt+Aktualisieren).
Öffnen Sie jetzt AEM, klicken Sie mit der rechten Maustaste und klicken Sie auf `Inspect`
Gehen Sie zu Quellen und suchen Sie nach Ihrer `[node_name].js` (z. B.: extensions.js). Führen Sie einen Befehl / Befehl + D aus, um nach Ihrer Datei zu suchen. Wenn die `.js`-Datei mit dem JS-Code vorhanden ist, den Sie aus `dist/guides-extension.umd.cjs` oder `dist/guides-extension.js` eingefügt haben, ist die Einrichtung abgeschlossen
