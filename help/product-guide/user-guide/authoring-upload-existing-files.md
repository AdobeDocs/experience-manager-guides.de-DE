---
title: Hochladen von Dateien
description: Erfahren Sie, wie Sie Ihre Dateien in das AEM-Repository hochladen und Fehler beheben können. Kennenlernen der Assets-Konsolen-Benutzeroberfläche, des AEM-Desktop-Programms und der Massenaufnahme von Assets und Verwenden von FrameMaker für den Massen-Upload
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
source-git-commit: 0259c0c0b7270d860198f17e6ea5f5829df038d5
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 2%

---

# Hochladen von Dateien {#id176FF000JUI}

Wahrscheinlich hätten Sie ein Repository mit vorhandenen DITA-Inhalten, die Sie mit Adobe Experience Manager Guides verwenden möchten. Für solche vorhandenen Inhalte können Sie einen der folgenden Ansätze verwenden, um Ihren Inhalt stapelweise in das Adobe Experience Manager-Repository hochzuladen.

>[!IMPORTANT]
>
> Unter [Hinzufügen digitaler Assets zu Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=de) finden Sie detaillierte Informationen zu den unterstützten Methoden zum Hochladen von Inhalten in Adobe Experience Manager.

## Benutzeroberfläche der Assets-Konsole

Um [digitale Assets mithilfe der Benutzeroberfläche der Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=de#filename-handling?lang=de#upload-assets)Konsole zu Adobe Experience Manager as a Cloud Service Assets hinzuzufügen, wählen Sie das gewünschte Asset auf Ihrem Desktop aus und ziehen Sie es über die Adobe Experience Manager-Benutzeroberfläche \(Webbrowser\) in den Zielordner. Stellen Sie beim Hochladen von Assets sicher, dass die Dateinamen keine nicht unterstützten oder unzulässigen Zeichen enthalten.

Weitere Informationen finden Sie im Abschnitt [Behandlung von Dateinamen und unzulässige Zeichen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=de#filename-handling) in der Dokumentation zu Adobe Experience Manager.

## Adobe Experience Manager-Desktop-Programm

Verwenden Sie das Adobe Experience Manager-Desktop-Programm, wenn Sie ein Kreativprofi sind und die Assets auf Ihrem lokalen Desktop verwalten möchten. Sie können diese Assets mit Ihren Desktop-Programmen öffnen und bearbeiten. Sie können auch Versionen verwalten und Ihre Dateien für andere Benutzer freigeben. Weitere Informationen finden Sie unter [Adobe Experience Manager Desktop App](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=de).

## Asset-Massenaufnahme

Bei umfangreichen Migrationen und gelegentlichen Massenaufnahmen von Assets können Sie Ihre Inhalte mit dem Asset-Bulk-Ingest hochladen. Mit diesem Tool können Sie Masseninhalte aus unterstützten Datenspeichern wie Azure oder S3 hochladen. Weitere Informationen finden Sie unter [Asset-Massenaufnahme](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=de#asset-bulk-ingestor).

## Verwenden von FrameMaker für den Massen-Upload

Adobe FrameMaker verfügt über einen leistungsstarken Adobe Experience Manager-Connector, mit dem Sie vorhandene DITA- und andere FrameMaker-Dokumente \(`.book` und `.fm`\) einfach in Adobe Experience Manager hochladen können. Sie können verschiedene Datei-Upload-Funktionen verwenden, z. B. das Hochladen einer einzelnen Datei, das Hochladen eines vollständigen Ordners mit oder ohne Abhängigkeiten \(z. B. Inhaltsreferenzen, Querverweise und Grafiken\).

Weitere Informationen zur Verwendung der Funktion für den Massen-Upload in FrameMaker finden Sie im Abschnitt *Erstellen eines CRX-Ordners und Hochladen von*) im FrameMaker-Benutzerhandbuch.

## Fehlerbehandlung beim Hochladen von Inhalten {#id201MI0I04Y4}

Wenn es zu einem Fehler beim Hochladen einer oder mehrerer Dateien kommt, wird am Ende des Upload-Prozesses eine Eingabeaufforderung mit einer Liste der Dateien angezeigt, die nicht hochgeladen werden konnten, wie im folgenden Ausschnitt dargestellt.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Weitere Informationen zur Funktionsweise verschiedener Szenarien für den Datei-Upload finden Sie unter [Verwalten von Dateien und Ordnern](authoring-file-management.md#).

Wenn Sie ein Tool wie das Adobe Experience Manager-Desktop-Programm oder das Asset-Bulk-Ingest verwenden, wird die Aktion, die für eine doppelte Datei ausgeführt werden soll, durch eine Einstellung im Adobe Experience Manager-Server gesteuert. Wenden Sie sich an Ihren Systemadministrator, um mehr über diese Konfiguration zu erfahren.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Inhalte verwalten](authoring.md)
