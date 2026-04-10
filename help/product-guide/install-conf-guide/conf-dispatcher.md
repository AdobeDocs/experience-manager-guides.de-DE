---
title: Konfiguration des Dispatchers
description: Erfahren Sie, wie Sie Dispatcher konfigurieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 7%

---

# Konfiguration des Dispatchers {#id213BCM0M05U}

Wenn Sie beabsichtigen, eine Dispatcher in der AEM-Autoreninstanz zusammen mit AEM Guides zu verwenden, müssen Sie die folgenden zusätzlichen Konfigurationen vornehmen, um die Einrichtung abzuschließen:

>[!NOTE]
>
> Dispatcher ist ein Tool von Adobe Experience Manager für das Zwischenspeichern und/oder den Lastenausgleich. Weitere Informationen zur Verwendung von Dispatcher finden Sie unter [Übersicht über Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=de).

## AllowEncodedSlashes in URLs aktivieren

URLs mit kodierten Schrägstrichen sind im AEM-Dispatcher-Setup nicht standardmäßig aktiviert. Bei der Arbeit in AEM Guides müssen Sie dies jedoch aktivieren. Dazu müssen Sie den `AllowEncodedSlashes` Parameter in der Apache-Konfiguration auf **Ein** setzen, wie im folgenden Ausschnitt gezeigt:

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

Führen Sie die folgenden Schritte aus, um die `mime.types`-Datei zu aktualisieren:

1. Stellen Sie mithilfe von SSH eine Verbindung mit dem Dispatcher-Server her und navigieren Sie zur `httpd.conf`.

1. Überprüfen Sie den Pfad der `mime.types`.

1. Öffnen Sie die `mime.types` und suchen Sie nach „text/html“. Die Standardzuordnung für „text/html“ ist:

   `text/html html htm`

1. Aktualisieren Sie die Zuordnung, indem Sie ditamap- und dita-Erweiterungen wie folgt hinzufügen:

   `text/html html htm ditamap dita`

1. Speichern und schließen Sie die Datei.


Durch dieses Konfigurationsupdate wird sichergestellt, dass die von Dispatcher gerenderten DITA-Zuordnungs- und Themendateien als HTML in der Assets-Benutzeroberfläche angezeigt werden.

## Anforderungs-URL für Benutzervoreinstellungen zulassen

Wenn Sie eine Dispatcher mit AEM Guides verwenden und Ihre Autoreninstanz über einen Dispatcher verfügt, nehmen Sie die beiden folgenden Änderungen vor:

- Setzen Sie die URL der POST-Anfrage auf die Whitelist. Nachfolgend finden Sie eine Beispielregel für `/filters`: Fügen Sie diese Regel zur Dispatcher-Konfigurationsdatei hinzu:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Stellen Sie sicher, dass das URL-Muster &quot;`/libs/cq/security/userinfo.json`&quot; nicht im Autoren-Dispatcher zwischengespeichert wird. Fügen Sie daher in `\(like below\)` eine `author\_dispatcher.any` hinzu.

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

