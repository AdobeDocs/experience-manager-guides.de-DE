---
title: Installation und Einrichtung
description: Installieren und Verwenden des AEM Guides-Erweiterungspakets
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 1%

---

# Installieren und Verwenden des AEM Guides-Erweiterungspakets

Mit Erweiterungen können Sie Ihre AEM Guides-App an Ihre Anforderungen anpassen. Dieses Erweiterungs-Framework wird ab AEM Guides v4.3 (On-Premise) und 2310 (Cloud) unterstützt.

## Voraussetzungen

Dieses Paket erfordert [git bash](https://github.com/git-guides/install-git) und npm

## Installation

Die einfachste Methode zum Bootstrapping der AEM Guides-Framework-Installation ist durch CLI

```bash
npx @adobe/create-guides-extension
```

## Hinzufügen von Anpassungscode

1. Fügen Sie Code-Dateien für jede Komponente hinzu, die Sie im Verzeichnis `src/` erweitern möchten. Einige Beispieldateien wurden bereits hinzugefügt.
2. Jetzt in der Datei `index.ts` im Verzeichnis `src/` :
   - Importieren Sie die `.ts` -Dateien mit den Anpassungen, die Sie in Ihrem Build hinzufügen möchten.
   - Importe zu `window.extension` hinzufügen
   - Registrieren Sie die `id` der angepassten Komponente und den entsprechenden Import bei `tcx extensions`
   - Siehe Beispiel `/src/index.ts`

## Erstellen des benutzerdefinierten Codes

- Führen Sie `npm run build` im Stammverzeichnis aus. Sie erhalten 3 Dateien im Verzeichnis `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Build-Ausgabe](./../imgs/build_output.png)

## Hinzufügen der Anpassung zu AEM

- Gehe zu `CRXDE` `crx/de/index.jsp#/`
- Erstellen Sie unter dem Ordner `apps` einen neuen Knoten des Typs `cq:ClientLibraryFolder` .

![Ordnerstruktur](./../imgs/crxde_folder_structure.png)

- Wählen Sie im Knoten `properties` die Option `Multi` und fügen Sie die folgende Eigenschaft hinzu:
Name: `categories`
Typ: `String []`
Wert: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Ordnereigenschaften](./../imgs/crxde_folder_properties.png)

- Um die erstellte JS hinzuzufügen, erstellen Sie eine neue Datei, z. B. `tcx1.js` im oben erstellten Knoten. Fügen Sie hier den Code aus `dist/guides-extension.umd.cjs` oder `dist/guides-extension.js` hinzu. Erstellen Sie nun eine neue Datei `js.txt`, hier fügen wir den Namen unserer JS-Datei hinzu, der in diesem Fall lautet:

```t
#base=.
tcx1.js
```

- Um den erstellten CSS hinzuzufügen, erstellen Sie eine neue Datei, z. B. `tcx1.css` im oben erstellten Knoten. Fügen Sie hier den Code von `dist/build.css` hinzu. Erstellen Sie nun eine neue Datei `css.txt`, hier fügen wir den Namen unserer CSS-Datei hinzu, der in diesem Fall lautet:

```t
#base=.
tcx1.css
```

- Führen Sie einen `shift + refresh` aus, um die App mit den Anpassungen zu laden!

## Fehlerbehebung

Überprüfen Sie, ob alle oben genannten Schritte korrekt ausgeführt wurden.
Nachdem Sie Ihren Code zu tcx.js hinzugefügt haben, stellen Sie sicher, dass Sie eine harte Aktualisierung durchführen (Umschalt+Aktualisieren).
Öffnen Sie nun AEM, klicken Sie mit der rechten Maustaste und klicken Sie auf `Inspect`
Gehen Sie zu Quellen und suchen Sie nach Ihrer `[node_name].js` -Datei (z. B. extensions.js). Führen Sie ein Steuerelement / Befehl + D aus, um nach Ihrer Datei zu suchen. Wenn die `.js` -Datei mit dem JS-Code vorhanden ist, den Sie aus `dist/guides-extension.umd.cjs` oder `dist/guides-extension.js` eingefügt haben, ist das Setup abgeschlossen.
