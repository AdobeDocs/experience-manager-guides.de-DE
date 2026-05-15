---
title: Konfiguration des Dispatchers
description: Erfahren Sie, wie Sie Dispatcher konfigurieren
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/RTgKeZZYjXP5ebOpTys9RL6-Q9IcPbkLZJ13ueRZwVI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 9%

---

# Konfiguration des Dispatchers {#id213BCM0M05U}

Wenn Sie beabsichtigen, eine Dispatcher in der AEM-Autoreninstanz zusammen mit AEM Guides zu verwenden, müssen Sie die folgenden zusätzlichen Konfigurationen vornehmen, um die Einrichtung abzuschließen:

>[!NOTE]
>
> Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich. Weitere Informationen zur Verwendung von Dispatcher finden Sie unter [Übersicht über Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=de).

## AllowEncodedSlashes in URLs aktivieren

URLs mit kodierten Schrägstrichen sind im AEM-Dispatcher-Setup nicht standardmäßig aktiviert. Bei der Arbeit in AEM Guides müssen Sie dies jedoch aktivieren. Dazu müssen Sie den Parameter „AllowEncodedSlashes“ in der Apache-Konfiguration auf „On“ setzen, wie im folgenden Ausschnitt gezeigt:

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

## Konfigurieren der Datei „mime.types“ für DITA

Bei Verwendung einer Dispatcher mit AEM Guides müssen Sie sicherstellen, dass die DITA-Zuordnung und die Themendateien als HTML gerendert werden, damit Autorinnen und Autoren den Inhalt wie erwartet anzeigen können \(anstelle von Rohtextformat\).

Führen Sie die folgenden Schritte aus, um die Datei „mime.types“ zu aktualisieren:

1. Stellen Sie mithilfe von SSH eine Verbindung zum Dispatcher-Server her und navigieren Sie zur Datei httpd.conf .

1. Überprüfen Sie den Pfad der Datei „mime.types“.

1. Öffnen Sie die Datei mime.types und suchen Sie nach „text/html“. Die Standardzuordnung für „text/html“ ist:

   `text/html html htm`

1. Aktualisieren Sie die Zuordnung, indem Sie ditamap- und dita-Erweiterungen wie folgt hinzufügen:

   `text/html html htm ditamap dita`

1. Speichern und schließen Sie die Datei.


Durch dieses Konfigurationsupdate wird sichergestellt, dass die von Dispatcher gerenderten DITA-Zuordnungs- und Themendateien als HTML in der Assets-Benutzeroberfläche angezeigt werden.

## Anforderungs-URL für Benutzervoreinstellungen zulassen

Wenn Sie eine Dispatcher mit AEM Guides verwenden und Ihre Autoreninstanz über einen Dispatcher verfügt, nehmen Sie die beiden folgenden Änderungen vor:

- Setzen Sie die URL der POST-Anfrage auf die Whitelist. Nachfolgend finden Sie eine Beispielregel &quot;`/filters`&quot; - Fügen Sie diese Regel zur Dispatcher-Konfigurationsdatei hinzu:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Stellen Sie sicher, dass das URL-Muster &quot; /libs/cq/security/userinfo.json&quot; nicht im Autoren-Dispatcher zwischengespeichert wird. Fügen Sie daher eine Regel \(wie unten\) in „author\_dispatcher.any“ hinzu.

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)
