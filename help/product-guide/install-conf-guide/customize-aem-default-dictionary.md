---
title: Anpassen des Standardwörterbuchs von AEM
description: Erfahren Sie, wie Sie das Standardwörterbuch von AEM anpassen
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 51099b42-706f-42b4-993e-7d9577b5a4f0
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Anpassen des Standardwörterbuchs von AEM {#id209SD8000WU}

Der Editor kann so konfiguriert werden, dass er die Rechtschreibprüfung von AEM oder die Rechtschreibprüfung des Browsers verwendet. Wenn Sie mit der Rechtschreibprüfung von AEM arbeiten, können Sie Ihre Liste benutzerdefinierter Wörter definieren. Diese benutzerdefinierten Wörter werden dann zum Wörterbuch der AEM hinzugefügt. Im Editor werden diese Wörter nicht als \(falsch\) gekennzeichnet.

Die folgenden Registerkarten enthalten Anweisungen zum Erstellen Ihrer Liste benutzerdefinierter Wörter, die je nach Experience Manager Guides-Einrichtung im Wörterbuch von AEM hinzugefügt werden: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Erstellen Sie die Datei user\_dictionary.txt mit einer Liste von Wörtern, die Sie in Ihrem benutzerdefinierten Wörterbuch definieren möchten.

   >[!NOTE]
   >
   > Jedes benutzerdefinierte Wort muss in einer neuen Zeile definiert werden.

1. Speichern Sie die Datei am folgenden Speicherort im Git-Repository Ihrer Cloud Manager:

   /apps/fmdita/config

1. Speichern Sie die Datei.

   Übertragen Sie die Änderungen und führen Sie die Cloud Manager \(CI/CD\)-Pipeline aus, um Konfigurationsänderungen bereitzustellen.


Autorinnen und Autoren müssen ihre Editor-Sitzung neu starten, damit die Liste der benutzerdefinierten Wörter im AEM-Wörterbuch aktualisiert wird.

>[!TAB On-Premise]

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zum folgenden Knoten:

   /apps/fmdita/config

1. Erstellen Sie eine neue Datei mit dem Namen user\_dictionary.txt.

1. Öffnen Sie die Datei und fügen Sie eine Liste von Wörtern hinzu, die Sie im benutzerdefinierten Wörterbuch definieren möchten.

   Der folgende Screenshot zeigt eine Liste mit benutzerdefinierten Wörtern, die der Datei user\_dictionary.txt hinzugefügt wurden:

   ![](assets/custom-words-list-dictionary.png){width="650"}

1. Speichern und schließen Sie die Datei.


Autorinnen und Autoren müssen ihre Editor-Sitzung neu starten, damit die Liste der benutzerdefinierten Wörter im AEM-Wörterbuch aktualisiert wird.

>[!ENDTABS]

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
