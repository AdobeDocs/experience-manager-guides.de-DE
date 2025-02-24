---
title: Anpassen des Web-Editors
description: Erfahren Sie, wie Sie die Anzeige eingefügter Tabellen im Editor anpassen
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: d03ac6ba3ec8e5c52c31a3239e2043bbae79622e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Konfigurieren der Anzeige eingefügter Tabellen

Über die sekundäre Symbolleiste im Editor können Sie eine einfache Tabelle an der aktuellen oder nächsten gültigen Position eines Themas einfügen. Sie können auch eine Tabelle aus Microsoft Word oder Excel kopieren und direkt in eine Themendatei einfügen.

Admins können konfigurieren, wie kopierte Tabellen angezeigt werden. Standardmäßig werden solche kopierten Tabellen als `simpletable` im Editor angezeigt. Sie können diese Einstellung jedoch ändern, um kopierte Tabellen wie `tgroup` anzuzeigen, indem Sie die XML-Editor-Konfigurationseinstellung aktualisieren.

>[!NOTE]
>
> Wenn Sie eine Tabelle mit zusammengeführten Zeilen oder Spalten kopieren, wird die Tabelle als normale `trgoup` eingefügt und nicht `simpletable` unabhängig von der in der XML-Editor-Konfiguration konfigurierten Tabelleneinstellung.

Um das Standardtabellenformat zu aktualisieren, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Adobe Experience Manager-Navigationsseite und wählen Sie **der linken** „Tools“ aus.
2. Wählen Sie im Bedienfeld Tools **Guides** aus der Liste der Tools aus.
3. Wählen Sie **Ordnerprofile** und wählen Sie dann das Profil aus, bei dem Sie die Tabelleneinstellung aktualisieren möchten.
4. Navigieren Sie zur Registerkarte **XML-Editor-**&quot;.
5. Wählen Sie **oben** Symbol „Bearbeiten“ aus.
6. Wählen Sie das **Herunterladen**-Symbol aus, um die `ui_config.json`-Datei auf Ihr lokales System herunterzuladen.
7. Aktualisieren Sie in der `ui_config.json` die `simpletable` wie unten dargestellt:

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


Speichern Sie die Datei nach der Aktualisierung und laden Sie sie hoch.

