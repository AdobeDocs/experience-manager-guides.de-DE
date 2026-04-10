---
title: Anpassen des Standardwörterbuchs von AEM
description: Erfahren Sie, wie Sie das Standardwörterbuch von AEM anpassen
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Anpassen des Standardwörterbuchs von AEM {#id209SD8000WU}

Der Web-Editor kann so konfiguriert werden, dass er die Rechtschreibprüfung von AEM oder die Rechtschreibprüfung des Browsers verwendet. Wenn Sie mit der Rechtschreibprüfung von AEM arbeiten, können Sie Ihre Liste benutzerdefinierter Wörter definieren. Diese benutzerdefinierten Wörter werden dann dem Wörterbuch der AEM hinzugefügt, und diese Wörter werden im Web-Editor nicht als \(falsch\) gekennzeichnet.

Führen Sie die folgenden Schritte aus, um Ihre Liste mit benutzerdefinierten Wörtern zu erstellen, die im Wörterbuch von AEM hinzugefügt werden:

1. Erstellen Sie die Datei user\_dictionary.txt mit einer Liste von Wörtern, die Sie in Ihrem benutzerdefinierten Wörterbuch definieren möchten.

   >[!NOTE]
   >
   > Jedes benutzerdefinierte Wort muss in einer neuen Zeile definiert werden.

1. Speichern Sie die Datei am folgenden Speicherort im Git-Repository Ihrer Cloud Manager:

   /apps/fmdita/config

1. Speichern Sie die Datei.

   Übertragen Sie die Änderungen und führen Sie die Cloud Manager \(CI/CD\)-Pipeline aus, um Konfigurationsänderungen bereitzustellen.


Autoren müssen ihre Web-Editor-Sitzung neu starten, damit die Liste der benutzerdefinierten Wörter im AEM-Wörterbuch aktualisiert wird.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
