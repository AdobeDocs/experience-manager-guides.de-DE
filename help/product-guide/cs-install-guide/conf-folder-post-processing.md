---
title: Dateinamen konfigurieren
description: Erfahren Sie, wie Sie die Nachbearbeitung für einen auf Adobe Experience Manager Assets hochgeladenen Ordner deaktivieren
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Deaktivieren der Nachbearbeitung für einen Ordner

Standardmäßig werden alle hochgeladenen Assets mit dem Workflow DAM-Update-Asset verarbeitet. Experience Manager Guides führt im Rahmen dieses Workflows eine zusätzliche Verarbeitung, die so genannte Nachbearbeitung, aus. Dies hilft auch beim Generieren der UUIDs

Beim Hochladen Ihrer Dateien und Ordner auf den *Adobe Experience Manager Assets*-Server können Sie auch die Nachbearbeitung und das Generieren von UUIDs deaktivieren.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um die Nachbearbeitung für einen bestimmten Pfad zu deaktivieren oder die Nachbearbeitung für einen Ordner zu ignorieren:

>[!NOTE]
>
> Sie können auch reguläre Ausdrücke (Regex) verwenden, um Regeln zu definieren, die für mehrere Ordner oder eine gesamte Ordnerhierarchie gelten. Weitere Informationen finden Sie im Abschnitt [Verwenden von Regex zum Aktivieren oder Deaktivieren der ](#use-regex-to-enable-or-disable-post-processing)&quot;.

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS-`/` (mehrwertige Eigenschaft, Zeichenfolgen mit einem Pfad, bei dem <br> am Ende weggelassen werden oder Regex) **Standardwert**: `/content/dam/projects/translation_output` |

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS-`/` (mehrwertige Eigenschaft, Zeichenfolgen mit einem Pfad, bei dem <br> am Ende weggelassen werden oder Regex) **Standardwert**: `/content/dam` |

## Regeln zum Aktivieren oder Deaktivieren der Nachbearbeitung

Standardmäßig erfolgt die Nachbearbeitung für jeden Ordnerpfad unter dem Experience Manager DAM-Ordner. Konfigurationen werden für jeden Ordner gemäß den folgenden Regeln angewendet:

* Wenn das übergeordnete Element für die Nachbearbeitung ignoriert wird, aber der untergeordnete Ordner aktiviert ist, werden das untergeordnete Element und alle seine Nachfolger als aktiviert betrachtet.
* Wenn das übergeordnete Element für die Nachbearbeitung aktiviert ist, das untergeordnete Element jedoch ignoriert wird, werden das untergeordnete Element und alle seine Nachfolger als ignoriert betrachtet.
* Wenn derselbe Ordnerpfad sowohl in der `ignored.post.processing.paths`- als auch in der `enabled.post.processing.paths`-Konfiguration vorhanden ist, wird er für die Nachbearbeitung als ignoriert erachtet.

## Verwenden von Regex zum Aktivieren oder Deaktivieren der Nachbearbeitung

Anstatt einzelne Ordnerpfade anzugeben, können Sie reguläre Ausdrücke (Regex) verwenden, um Regeln zu definieren, die für mehrere Ordner oder ganze Ordnerhierarchien gelten.

Regex-Muster werden während der Nachbearbeitung anhand des vollständigen Asset-Pfads ausgewertet.

Wenn reguläre Ausdrücke (Regex) verwendet werden, um ignorierte und aktivierte Nachbearbeitungspfade zu konfigurieren, bewertet AEM Guides beide Konfigurationen anhand des Asset-Pfads. Wenn ein Pfad sowohl mit einer Ignorieren-Regel als auch mit einer Aktivieren-Regel übereinstimmt, haben Ignorieren-Regeln immer Vorrang.

Die folgenden Beispiele veranschaulichen, wie Regeln auf Regex-Basis ignoriert und aktiviert werden.

## Regex-Auswertungsszenarien für die Nachbearbeitung

### Übergeordnete Hierarchie ignorieren, bestimmten Ordner aktivieren

**Regex ignorieren**

`regex:/content/dam/lang-test/.*`

**Regex aktivieren**

`regex:/content/dam/lang-test/.*/parent1`

Im obigen Beispiel wird die Nachbearbeitung für `/content/dam/lang-test/en/parent1` deaktiviert.

Obwohl der Pfad mit dem aktivierten Regex übereinstimmt, wird er bereits mit dem ignorierten Regex abgeglichen. Regeln ignorieren hat Vorrang, daher ist die Nachbearbeitung nicht aktiviert.

### Bestimmten Ordner ignorieren, breitere Hierarchie aktivieren

**Regex ignorieren**

`regex:/content/dam/lang-test/.*/parent1`

**Regex aktivieren**

`regex:/content/dam/lang-test/.*`

Im obigen Beispiel wird die Nachbearbeitung für `/content/dam/lang-test/en/parent1` deaktiviert und für `/content/dam/lang-test/en/parent2` aktiviert.

Der `parent1` wird explizit ignoriert und bleibt deaktiviert. Andere Ordner, die nur mit dem aktivierten Regex übereinstimmen, werden verarbeitet.

### Übergeordneten Ordner ignorieren, einen untergeordneten Ordner aktivieren

**Regex ignorieren**

`regex:/content/dam/lang-test/.*/parent1`

**Regex aktivieren**

`regex:/content/dam/lang-test/.*/parent1/child1`

Im obigen Beispiel wird die Nachbearbeitung für `/content/dam/lang-test/en/parent1` und `/content/dam/lang-test/en/parent1/child2` deaktiviert und für `/content/dam/lang-test/en/parent1/child1` aktiviert.

Der durch Regex explizit aktivierte untergeordnete Ordner wird verarbeitet. Andere untergeordnete Ordner bleiben deaktiviert, da ihr übergeordneter Pfad mit dem ignorierten Regex übereinstimmt.

### Bestimmten untergeordneten Ordner ignorieren, übergeordnete Hierarchie aktivieren

**Regex ignorieren**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Regex aktivieren**

`regex:/content/dam/lang-test/.*/parent1`

Im obigen Beispiel wird die Nachbearbeitung für `/content/dam/lang-test/en/parent1/child1` deaktiviert und für `/content/dam/lang-test/en/parent1` und `/content/dam/lang-test/en/parent1/child2` aktiviert.

Nur der explizit ignorierte untergeordnete Ordner wird übersprungen. Der übergeordnete Ordner und andere untergeordnete Ordner werden verarbeitet, da sie mit dem aktivierten Regex übereinstimmen und nicht mit dem ignorierten Regex übereinstimmen.

