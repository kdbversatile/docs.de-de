---
title: Serialisieren und Deserialisieren von JSON C# mit-.net
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: acb83be9b20a155b6b6a9fb5ade38e099f54e71d
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163591"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>JSON-Serialisierung und-Deserialisierung (Marshalling und Unmarshalling) in .net-Overview

Der `System.Text.Json`-Namespace stellt Funktionen zum Serialisieren und Deserialisieren von JavaScript Object Notation (JSON) bereit.

Der Bibliotheks Entwurf hebt eine hohe Leistung und eine geringe Speicher Belegung für eine umfangreiche Featuregruppe hervor. Die integrierte UTF-8-Unterstützung optimiert den Prozess des Lesens und Schreibens von JSON-Text, der als UTF-8 codiert ist. Dies ist die häufigste Codierung für Daten im Web und Dateien auf dem Datenträger.

Die Bibliothek stellt außerdem Klassen zum Arbeiten mit einem Dokument Objektmodell (DOM) im Arbeitsspeicher bereit. Diese Funktion ermöglicht den zufälligen schreibgeschützten Zugriff auf die Elemente in einer JSON-Datei oder Zeichenfolge. 

## <a name="how-to-get-the-library"></a>Vorgehensweise beim erhalten der Bibliothek

* Die Bibliothek ist als Teil des gemeinsamen [.net Core 3,0](https://aka.ms/netcore3download) -Frameworks integriert.
* Installieren Sie für andere Ziel-Frameworks das [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) nuget-Paket. Das Paket unterstützt Folgendes:
  * .NET Standard 2,0 und höhere Versionen
  * .NET Framework 4.7.2 und spätere Versionen
  * .Net Core 2,0, 2,1 und 2,2

## <a name="additional-resources"></a>Weitere Ressourcen

* [Verwenden der Bibliothek](system-text-json-how-to.md)
* [Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Schreiben von Konvertern](system-text-json-converters-how-to.md)
* [System.Text.Json Quellcode](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [API-Referenz für System.Text.Json](xref:System.Text.Json)
* [System.Text.Json. API-Referenz für die Serialisierung](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
