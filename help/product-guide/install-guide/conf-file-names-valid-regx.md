---
title: Konfigurieren von RegX für gültige Dateinamenzeichen
description: Erfahren Sie, wie Sie RegX für gültige Dateinamenzeichen konfigurieren
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/STMaIE3mkqhAwXB7dz-3pmROSQjqPO5EVC9e2cC0nlE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 397
ht-degree: 0%

---

# Konfigurieren von RegX für gültige Dateinamenzeichen {#id214BD0550E8}

Ab AEM Guides Version 3.8 können Sie als Administrator eine Liste gültiger Sonderzeichen definieren, die in Dateinamen zulässig sind. In früheren Versionen durften Benutzende Dateinamen definieren, die Sonderzeichen wie `@`, `$`, `>` und mehr enthalten. Diese Sonderzeichen führten zu Problemen beim Öffnen von Themen über das DITA Map-Dashboard oder beim Klicken auf den Link des Themas im Inhaltsverzeichnis, was oft dazu führte, dass die Seite aufgrund von Sonderzeichen in der URL nicht geöffnet wurde.

Durch Verwendung der -Konfiguration, mit der Sie einen Regex für gültige Dateinamenzeichen definieren können, haben Sie die volle Kontrolle darüber, wie die Dateien intern im System benannt werden. Sie können eine Liste von Sonderzeichen definieren, die in den Dateinamen zulässig sind. Standardmäßig enthält die gültige Dateinamenkonfiguration &quot;`a-z A-Z 0-9 - _`&quot;. Beim Erstellen einer neuen Datei können Sie ein beliebiges Sonderzeichen im Titel der Datei haben, aber intern wird es im Dateinamen durch &quot;`-`&quot; ersetzt. Wenn Sie beispielsweise den Titel der Datei als „Einführung 1“ oder &quot;Introduction@1&quot; haben, würde der entsprechende Dateiname für beide Fälle „Einführung-1“ lauten.

Beachten Sie beim Definieren einer Liste gültiger Zeichen, dass diese Zeichen &quot;`*/:[\]|#%{}?&<>"/+`&quot; immer durch ein &quot;`-`&quot; ersetzt werden.

Wenn Sie die Liste der gültigen Sonderzeichen nicht konfigurieren, kann der Prozess der Dateierstellung zu unerwarteten Ergebnissen führen. Um solche Fehler zu vermeiden, wird dringend empfohlen, diese Konfigurationsänderung sofort nach dem Upgrade Ihres Builds auf Version 3.8 vorzunehmen.

So konfigurieren Sie einen RegX für gültige \(oder zulässige\) Zeichen in Dateinamen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und klicken Sie darauf.

1. Stellen Sie in der Eigenschaft **Regex für gültige Zeichen** sicher, dass die Eigenschaft auf \[-a-zA-Z0-9\_\] festgelegt ist. Sie können dieser Liste weitere Zeichen hinzufügen. Sie muss jedoch diese grundlegenden Zeichen enthalten und die Liste muss mit einem Bindestrich &quot;-&quot; beginnen.

   >[!NOTE]
   >
   > Diese Eigenschaft gilt nur für Dateinamen und nicht für Ordnernamen.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Ähnlich wie bei der Liste der gültigen Dateinamenzeichen können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM Site-Ausgabe angeben. Weitere Informationen finden Sie unter [Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe](conf-file-names-valid-regx-aem-site-output.md#).

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
