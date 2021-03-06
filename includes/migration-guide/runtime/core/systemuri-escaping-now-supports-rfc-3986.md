---
ms.openlocfilehash: 1654d58651bf14b0e7c21de2afa827634b7db858
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235660"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>RFC 3986 kann jetzt verwendet werden, um System.Uri mit Escapezeichen zu versehen

|   |   |
|---|---|
|Details|URI-Escapezeichen in .NET Framework 4.5 wurden geändert, um [RFC 3986](https://tools.ietf.org/html/rfc3986) zu unterstützen. Die speziellen Änderungen umfassen Folgendes:<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> versieht reservierte Zeichen basierend auf RFC 3986 mit Escapezeichen.</li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> versieht reservierte Zeichen nicht mit Escapezeichen.</li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> löst keine Ausnahme aus, wenn eine ungültige Escapesequenz gefunden wird.</li><li>Bei nicht reservierten Zeichen mit Escapezeichen werden letztere entfernt.</li></ul>|
|Vorschlag|<ul><li>Aktualisieren Sie die Anwendungen, um nicht auf <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> angewiesen zu sein, wenn Sie bei einer ungültigen Escapesequenz eine Ausnahme auslösen möchten. Derartige Sequenzen müssen jetzt direkt erkannt werden.</li><li>Erwarten Sie zudem, dass URI- und Datenzeichenfolgen mit und ohne Escapezeichen zwischen .NET Framework 4.0 und .NET Framework 4.5 möglicherweise abweichen und für .NET-Versionen nicht direkt verglichen werden sollten. Stattdessen sollten sie in einer einzelnen .NET-Version analysiert und normalisiert werden, bevor Vergleiche durchgeführt werden.</li></ul>|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
