---
title: SCORM-Vorschaufilter konfigurieren
description: Erfahren Sie, wie Sie SCORM-Vorschaufilter konfigurieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: f5b7ae41fe63b31a3b45b38fc73976987a2a5ebe
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 3%

---

# Konfigurieren der SCORM-Vorschau

In diesem Artikel wird erläutert, wie Sie die Experience Manager Guides-SCORM-Vorschau konfigurieren, um zu verwalten, welche externen Domains Stylesheets, Bilder, Schriftarten, Medien und eingebettete Inhalte in der SCORM-Vorschauausgabe bereitstellen dürfen. In den folgenden Schritten wird erläutert, wie Sie je nach verwendetem Setup verschiedene Filter für die SCORM-Vorschau konfigurieren:

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../install-conf-guide/download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Eigenschaftsdetails an:

   | PID | Eigenschaftsschlüssel | Standardwert |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.style.src` | `https://fonts.googleapis.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.img.src` | – |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.font.src` | `https://fonts.gstatic.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.media.src` | – |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.frame.src` | `https://www.youtube-nocookie.com`, `https://www.youtube.com` |


1. Speichern Sie die Konfigurationsdatei und stellen Sie sie in Ihrer Cloud Service-Umgebung bereit.

Nach dem Speichern beginnt die SCORM-Vorschau mit der Anwendung der aktualisierten Domain-Zulassungsliste. Externe Ressourcen von Domains, die dieser Konfiguration nicht hinzugefügt wurden, sind in der Vorschau nicht verfügbar.

>[!NOTE]
>
> Dies gilt nur für die Vorschau-Umgebung. Das herunterladbare SCORM-Paket stellt weiterhin alle erstellten Inhalte wie vorgesehen bereit.


>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **Guides SCORM Preview Filter (com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter)** und wählen Sie es aus.

   ![](assets/scorm-preview-filters.png){width="600"}


1. Fügen Sie in der Bundle-Konfiguration nach Bedarf die zulässigen Domain-URLs für jeden Ressourcentyp hinzu:

   | Feld | Beschreibung |
   |---|---|
   | **Zusätzlicher style-src-Host** | Domains, aus denen externe CSS-Stylesheets geladen werden dürfen (standardmäßig `https://fonts.googleapis.com`). |
   | **Zusätzlicher image-src-Host** | Domains, aus denen externe Bilder geladen werden dürfen. |
   | **Zusätzlicher Host „font-src“** | Domains, aus denen externe Schriftarten-Dateien (OTF, WOFF usw.) geladen werden dürfen (standardmäßig `https://fonts.gstatic.com`). |
   | **Zusätzlicher media-src-Host** | Domains, aus denen externe Mediendateien geladen werden dürfen. |
   | **Zusätzlicher Frame-src-Host** | Domains, aus denen iframe-Inhalte eingebettet werden dürfen (standardmäßig `https://www.youtube.com`, um YouTube-Videoeinbettungen zuzulassen). |

1. Wählen Sie **Speichern** aus.

Nach dem Speichern beginnt die SCORM-Vorschau mit der Anwendung der aktualisierten Domain-Zulassungsliste. Externe Ressourcen von Domains, die dieser Konfiguration nicht hinzugefügt wurden, sind in der Vorschau nicht verfügbar.

>[!NOTE]
>
> Dies gilt nur für die Vorschau-Umgebung. Das herunterladbare SCORM-Paket stellt weiterhin alle erstellten Inhalte wie vorgesehen bereit.

>[!ENDTABS]