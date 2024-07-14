---
title: Konfiguration des Dispatchers
description: Erfahren Sie, wie Sie Dispatcher konfigurieren
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 6%

---

# Konfiguration des Dispatchers {#id213BCM0M05U}

Wenn Sie planen, eine Dispatcher in AEM -Autoreninstanz zusammen mit AEM Guides zu verwenden, müssen Sie die folgenden zusätzlichen Konfigurationen durchführen, um die Einrichtung abzuschließen:

>[!NOTE]
>
> Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich. Weitere Informationen zur Verwendung von Dispatcher finden Sie unter [Übersicht über Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=de).

## AllowEncodedSlashes in URLs aktivieren

URLs mit kodierten Schrägstrichen sind bei AEM Dispatcher-Setup nicht standardmäßig aktiviert. Bei der Arbeit mit AEM Guides müssen Sie dies jedoch aktivieren. Dazu müssen Sie den Parameter AllowEncodedSlashes in der Apache-Konfiguration auf Ein setzen, wie im folgenden Snippet gezeigt:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Datei &quot;mime.types&quot;für DITA konfigurieren

Bei der Verwendung einer Dispatcher mit AEM Guides müssen Sie sicherstellen, dass die DITA-Zuordnungs- und Themendateien als HTML gerendert werden, damit Autoren den Inhalt erwartungsgemäß anzeigen können (anstelle des Rohtextformats\).

Führen Sie die folgenden Schritte aus, um die Datei &quot;mime.types&quot;zu aktualisieren:

1. Stellen Sie mithilfe von SSH eine Verbindung zum Dispatcher-Server her und navigieren Sie zur Datei &quot;httpd.conf&quot;.

1. Überprüfen Sie den Pfad der Datei &quot;mime.types&quot;.

1. Öffnen Sie die Datei &quot;mime.types&quot;und suchen Sie nach &quot;text/html&quot;. Die Standardzuordnung für &quot;text/html&quot;lautet:

   `text/html html htm`

1. Aktualisieren Sie die Zuordnung, indem Sie Ditamap- und Dia-Erweiterungen wie folgt hinzufügen:

   `text/html html htm ditamap dita`

1. Speichern und schließen Sie die Datei.


Diese Konfigurationsaktualisierung stellt sicher, dass von Dispatcher gerenderte DITA-Zuordnungs- und Themendateien in der Assets-Benutzeroberfläche als HTML angezeigt werden.

## URL der Anfrage &quot;Benutzereinstellungen zulassen&quot;

Wenn Sie eine Dispatcher mit AEM Guides verwenden und Ihre Autoreninstanz über einen Dispatcher verfügt, nehmen Sie die folgenden beiden Änderungen vor:

- Setzen Sie die URL der POST-Anfrage auf die Whitelist. Nachfolgend finden Sie eine Beispielregel &quot;`/filters`&quot;: Fügen Sie diese Regel zur Dispatcher-Konfigurationsdatei hinzu:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Stellen Sie sicher, dass das URL-Muster &quot; /libs/cq/security/userinfo.json&quot;nicht im Autoren-Dispatcher zwischengespeichert ist. Fügen Sie daher eine Regel \(wie unten\) in author\_dispatcher.any hinzu.

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Übergeordnetes Thema:**[ Herunterladen und Installieren](download-install.md)
