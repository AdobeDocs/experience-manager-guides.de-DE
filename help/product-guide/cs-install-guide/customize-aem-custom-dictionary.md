---
title: Anpassen des Standardwörterbuchs von AEM
description: Erfahren Sie, wie Sie das Standardwörterbuch von AEM anpassen
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/omWGECpXvtuNBUH8dcOnggOHmG8z1PevjBmZ-ZcYWjY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
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
