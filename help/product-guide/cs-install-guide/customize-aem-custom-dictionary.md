---
title: Anpassen des Standardwörterbuchs von AEM
description: Erfahren Sie, wie Sie das Standardwörterbuch von AEM anpassen
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---

# Anpassen des Standardwörterbuchs von AEM {#id209SD8000WU}

Der Web-Editor kann so konfiguriert werden, dass er die Rechtschreibprüfung von AEM oder die Rechtschreibprüfung des Browsers verwendet. Wenn Sie die Rechtschreibprüfung von AEM verwenden, können Sie die Liste der benutzerdefinierten Wörter definieren. Diese benutzerdefinierten Wörter werden dann dem AEM-Wörterbuch hinzugefügt, und diese Wörter werden im Web-Editor nicht als \(falsch\) gekennzeichnet.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierte Wortliste zu erstellen, die im AEM-Wörterbuch hinzugefügt werden:

1. Erstellen Sie die Datei user\_dictionary.txt mit einer Liste von Wörtern, die Sie in Ihrem benutzerdefinierten Wörterbuch definieren möchten.

   >[!NOTE]
   >
   > Jedes benutzerdefinierte Wort muss in einer neuen Zeile definiert werden.

1. Speichern Sie die Datei am folgenden Speicherort im Git-Repository Ihrer Cloud Manager:

   /apps/fmdita/config

1. Speichern Sie die Datei.

   Übertragen Sie die Änderungen und führen Sie die Cloud Manager \(CI/CD\)-Pipeline aus, um Konfigurationsänderungen bereitzustellen.


Autorinnen und Autoren müssen ihre Web-Editor-Sitzung neu starten, damit die Liste der benutzerdefinierten Wörter im AEM-Wörterbuch aktualisiert wird.

**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
