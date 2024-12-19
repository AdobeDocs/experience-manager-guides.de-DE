---
title: Einführung in das Erweiterungs-Repository
description: Verzeichnisstruktur des AEM Guides-Erweiterungspakets
role: User, Admin
exl-id: 99a00b3e-a5c9-41d8-a73d-8690d587277e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Verzeichnisstruktur des AEM Guides-Erweiterungspakets

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
├── dist
│   ├── guides-extension.js
│   ├── guides-extension.umd.cjs
│   ├── build.css
├── node_modules
├── package.json
├── package-lock.json 
└── .gitignore
└── buildCSS.mjs // for creating tailwind classes
└── vite.config.js // config for specifying TS and javascript build options
└── taliwind.config.js // config for tailwind we can add custom config for a design system here
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```

## /src

```text
├── src
│   ├── **/*{js,ts}
│   ├── index.ts
```

Das Quellverzeichnis enthält die TypeScript- oder JavaScript-Dateien für Ihre Erweiterung. Die Datei index.ts ist der Einstiegspunkt für Ihre Erweiterung. Sie können hier alle Komponenten importieren und als einzelnes Objekt exportieren. Dieses -Objekt wird von der Erweiterung zum Rendern der Komponenten verwendet.

### /dist

Dies ist der endgültige Build-Ordner. Diese enthält die endgültige JS- und CSS-Datei, die in die AEM kopiert werden muss.

```test
├── dist
│   ├── gudies-extension.js // you can either choose es module (this one) or .cjs(other one) file
│   ├── gudies-extension.umd.cjs
│   ├── build.css // this is your tailwind css output
```

## /jsons

Dieses Verzeichnis enthält die JSONs für die verschiedenen Ansichten. Sie können diese JSONs verwenden, um die Ziele zu identifizieren und die Ansicht anzupassen.

```text
├── jsons // jsons for the aem app
│   ├── context_menus // jsons for the context menus
│   ├── review_app // jsons for the review app
│   ├── xmleditor // jsons for xmleditor
```
