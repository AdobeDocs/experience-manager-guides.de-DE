---
title: Anpassen des Web-Editors
description: Erfahren Sie, wie Sie die Anzeige eingefügter Tabellen im Editor anpassen
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
TQID: 'https://experienceleague.adobe.com/0g3LyLfKxZEbtl968wJK6r1xPHRjagayeBF4xSvJF6c'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
