---
title: Konfigurieren von RegX für gültige Dateinamenzeichen
description: Erfahren Sie, wie Sie RegX für gültige Dateinamenzeichen konfigurieren
exl-id: 876dfc77-078f-4341-b99d-02a453d2e065
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '396'
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
> Ähnlich wie bei der Liste der gültigen Dateinamenzeichen können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM-Site-Ausgabe angeben. Weitere Informationen finden Sie unter [Konfigurieren gültiger Dateinamen für die AEM-Site-Ausgabe](conf-file-names-valid-regx-aem-site-output.md#).

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
