---
title: Installation und Einrichtung
description: Installieren und Verwenden des AEM Guides-Erweiterungspakets
role: User, Admin
exl-id: 0304c8d0-35a8-4712-a9af-36557e3b247f
TQID: https://experienceleague.adobe.com/ngU5TVcI7yva051ZscfGCfBb6vEbtG4cvjoOgplqmoA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 362
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
Öffnen Sie nun AEM, klicken Sie mit der rechten Maustaste darauf `Inspect`
Gehen Sie zu Quellen und suchen Sie nach Ihrer `[node_name].js` (z. B.: extensions.js). Führen Sie einen Befehl / Befehl + D aus, um nach Ihrer Datei zu suchen. Wenn die `.js`-Datei mit dem JS-Code vorhanden ist, den Sie aus `dist/guides-extension.umd.cjs` oder `dist/guides-extension.js` eingefügt haben, ist die Einrichtung abgeschlossen
