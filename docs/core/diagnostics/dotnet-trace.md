---
title: Das Tool „dotnet-trace“ – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: 64c931db5a18659707e832aaca910cfbbd6823c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714434"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>dotnet-trace-Hilfsprogramm für Leistungsanalysen

**Dieser Artikel gilt für:** ✓ .NET Core 3.0 SDK und neuere Versionen

## <a name="install-dotnet-trace"></a>Installieren von dotnet-trace

Installieren Sie das [NuGet-Paket](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` mit dem Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Übersicht

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Beschreibung

Das `dotnet-trace`-Tool:

* Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.
* Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.
* Es basiert auf der plattformübergreifenden `EventPipe`-Technologie der .NET Core-Runtime.
* Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.

## <a name="options"></a>Optionen

- **`--version`**  

  Zeigt die Version des Hilfsprogramms dotnet-counters an.

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="commands"></a>Befehle

| Befehl                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace ps](#dotnet-trace-ps) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>Optionen

- **`-p|--process-id <PID>`**

  Der Prozess, von dem die Ablaufverfolgung gesammelt werden soll.

- **`--buffersize <size>`**

  Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest. Standard: 256 MB.

- **`-o|--output <trace-file-path>`**

  Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten. Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.

- **`--providers <list-of-comma-separated-providers>`**

  Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen. Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter. Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.

  Diese Liste der Anbieter hat das folgende Format:

  - `Provider[,Provider]`
  - `Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.

- **`--format {NetTrace|Speedscope}`**

  Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest. Der Standardwert ist `NetTrace`.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>Argumente

- **`<input-filename>`**

  Die zu konvertierende Eingabe-Ablaufverfolgungsdatei. Standard: *trace.nettrace*.

### <a name="options"></a>Optionen

- **`--format <NetTrace|Speedscope>`**

  Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.

- **`-o|--output <output-filename>`**

  Ausgabedateiname. Die Erweiterung des Zielformats wird hinzugefügt.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

Listet anfügbare dotnet-Prozesse auf.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Sammeln einer Ablaufverfolgung mit dotnet-trace

So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:

- Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.

  - Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.
  - Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.
  - [dotnet-trace ps](#dotnet-trace-ps)

- Führen Sie den folgenden Befehl aus:

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an. `dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Anzeigen der von dotnet-trace erfassten Ablaufverfolgung

Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.

Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird. Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert. Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen. `Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.

> [!NOTE]
> Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format. Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert. Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit

`dotnet-trace` kann:

* `EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden. Beispielsweise in der Produktion.
* Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.

Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand. Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.

Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.

## <a name="net-providers"></a>.NET-Anbieter

Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter. .NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.

| Anbietername                            | Information |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Runtimeanbieter](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[CLR-Runtime-Schlüsselwörter](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Rundownanbieter](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[CLR-Rundown-Schlüsselwörter](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Aktiviert den Beispielprofiler. |
