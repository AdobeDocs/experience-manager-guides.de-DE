---
title: Konfigurieren der Inhaltssicherheitsrichtlinie für die SCORM-Vorschau
description: Erfahren Sie, wie Sie die Content Security Policy für die SCORM-Vorschau mithilfe einer Umgebungsvariablen in Cloud Manager konfigurieren
feature: Authoring
role: User
source-git-commit: 730fe6021aa20aa2b57801807da0f471f84a7718
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 3%

---


# Konfigurieren der Content Security Policy (CSP) für die SCORM-Vorschau

Die Experience Manager Guides SCORM-Vorschau wird über eine dedizierte Umgebungsvariable verwaltet, die die Content Security Policy (CSP) steuert, die auf das Vorschauerlebnis angewendet wird. Nachdem die Einstellung aktiviert wurde, können Admins sie erweitern, indem sie zusätzliche vertrauenswürdige Quellen hinzufügen. Zu diesen Quellen können Skripte, Stile, Schriftarten, Bilder, Medien, Frames und mehr gehören, die für SCORM-Pakete erforderlich sind, um Vorschaubilder in Experience Manager Guides korrekt zu laden und zu rendern.

In diesem Artikel wird erläutert, wie Sie die Umgebungsvariable in Cloud Manager hinzufügen und konfigurieren, was die einzelnen Felder im JSON-Wert tun, und wie Sie den Wert später aktualisieren, wenn sich Ihre Anforderungen ändern.

## Konfigurationsfelder

Die Variable akzeptiert `GUIDES_SCORM_PREVIEW_CONFIG` JSON-Objekt als Wert. Jeder Wert steuert einen bestimmten Aspekt des CSP, der während der SCORM-Vorschau angewendet wird:

| Felder | Typ | Beschreibung |
|---|---|---|
| `CSP_ENABLED` | Boolescher Wert | Schaltet die CSP-Durchsetzung für die SCORM-Vorschau ein (`true`) oder aus (`false`). |
| `ALLOW_UNSAFE_EVAL` | Boolesch | Ermöglicht die Verwendung von `eval()` und ähnlichen unsicheren JavaScript-Auswertungsmethoden, wenn sie auf `true` gesetzt sind. |
| `ADDITIONAL_SCRIPT_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die JavaScript bedienen dürfen. |
| `ADDITIONAL_STYLE_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die Stylesheets bereitstellen dürfen. |
| `ADDITIONAL_FONT_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die Schriftarten bereitstellen dürfen. |
| `ADDITIONAL_FRAME_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die in `<iframe>` Elemente geladen werden dürfen. |
| `ADDITIONAL_IMG_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die Bilder bereitstellen dürfen. |
| `ADDITIONAL_MEDIA_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die Audio-/Videoinhalte bereitstellen dürfen. |
| `ADDITIONAL_WORKER_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die Web-Sekundären dienen dürfen. |
| `ADDITIONAL_CONNECT_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, mit denen sich die Vorschau verbinden darf (z. B. XHR-/Fetch-Aufrufe). |
| `ADDITIONAL_MANIFEST_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die Web-App-Manifeste bereitstellen dürfen. |
| `ADDITIONAL_OBJECT_SRC` | Array | Zusätzliche vertrauenswürdige Quellen, die über `<object>`, `<embed>` oder `<applet>` geladen werden dürfen. |


## Standardwerte für Konfigurationsfelder

```json
{
  "CSP_ENABLED": true,
  "ALLOW_UNSAFE_EVAL": false,
  "ADDITIONAL_STYLE_SRC": ["https://fonts.googleapis.com"],
  "ADDITIONAL_FONT_SRC": ["https://fonts.gstatic.com"],
  "ADDITIONAL_FRAME_SRC": ["https://www.youtube-nocookie.com", "https://www.youtube.com"],
  "ADDITIONAL_SCRIPT_SRC": [],
  "ADDITIONAL_WORKER_SRC": [],
  "ADDITIONAL_IMG_SRC": [],
  "ADDITIONAL_MEDIA_SRC": [],
  "ADDITIONAL_CONNECT_SRC": [],
  "ADDITIONAL_MANIFEST_SRC": [],
  "ADDITIONAL_OBJECT_SRC": []
}
```

Je nach Bedarf müssen Sie nicht jeden Wert ausfüllen. Belassen Sie einen beliebigen Quelltyp als leeres Array, wenn Sie keine zusätzlichen Ursprünge dafür zulassen müssen.

>[!NOTE]
>
> Wenn Sie die CSP-Durchsetzung für die SCORM-Vorschau deaktivieren möchten, legen Sie `"CSP_ENABLED": false` im JSON-Wert fest.

## Fügen Sie die Variable in Cloud Manager hinzu

1. Melden Sie sich bei Cloud Manager an und wählen Sie die Umgebung aus, in der Sie die Konfiguration anwenden möchten.
2. Navigieren Sie zur Registerkarte **Konfiguration** der Umgebung.
3. Wählen **Hinzufügen/Aktualisieren**, um eine Umgebungsvariable hinzuzufügen.

   ![Hinzufügen einer neuen Variablen zur Cloud Manager-](assets/add-new-variable.png){width="650"}

4. Geben Sie den Namen der Variablen (`GUIDES_SCORM_PREVIEW_CONFIG`) in das Feld **Name** ein.

   ![Hinzufügen des Namens der Variablen im Namensfeld](assets/variable-name.png){width="650"}

5. Geben Sie Ihre vollständige JSON-Konfiguration, einschließlich der von Ihnen benötigten Quell-Zulassungslisten, im Feld **Wert** ein.
6. Wählen Sie **Service angewendet** aus, um festzulegen, ob die Variable für **Autor**, **Veröffentlichen** oder beide gelten soll. Wählen Sie für das Experience Manager Guides-Authoring **author** aus.
7. Wählen Sie **Variable** im Feld **Typ** aus.
8. Wählen Sie **Hinzufügen** aus.
9. Wählen Sie **Speichern** aus.

   ![Speichern der Variablen zum Anwenden auf die Umgebung](assets/save.png){width="650"}

Nach dem Speichern wendet Cloud Manager die Konfiguration auf die ausgewählte Umgebung an. Die Übertragung dauert in der Regel 10-12 Minuten. Warten Sie also etwas, bis die Aktualisierung abgeschlossen ist. Nach Abschluss des Vorgangs ist die neue Konfiguration für die SCORM-Vorschau in dieser Umgebung aktiv.

## Aktualisieren der Variablenwerte

Wenn sich Ihre Anforderungen ändern, können Sie die Variable `GUIDES_SCORM_PREVIEW_CONFIG` jederzeit auf derselben Registerkarte „Konfiguration“ in Cloud Manager erneut aufrufen. Suchen Sie die vorhandene Variable und wählen Sie ihre Option **Hinzufügen/Aktualisieren** aus, um sie zur Bearbeitung zu öffnen, und überarbeiten Sie dann den Wert nach Bedarf.