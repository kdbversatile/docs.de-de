---
ms.openlocfilehash: 846a6bcd3c668e6ad505f745bcb830c3b9dce437
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859346"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>Die AesCryptoServiceProvider-Entschlüsselungsmethode stellt eine wiederverwendbare Transformation bereit

|   |   |
|---|---|
|Details|Für Apps mit der Zielplattform .NET Framework 4.6.2 und höher stellt die <xref:System.Security.Cryptography.AesCryptoServiceProvider>-Entschlüsselungsmethode eine wiederverwendbare Transformation bereit. Nach einem Aufruf von <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=name> wird die Transformation erneut initialisiert und kann wiederverwendet werden. Bei Apps mit früheren Versionen von .NET Framework als Zielplattform wird bei dem Versuch, die Entschlüsselungsmethode durch Aufrufen von <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=name> nach einem Aufruf von <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=name> wiederzuverwenden, eine <xref:System.Security.Cryptography.CryptographicException> ausgelöst, oder es werden fehlerhafte Daten erstellt.|
|Vorschlag|Der Einfluss dieser Änderung sollte klein sein, da dies das erwartete Verhalten ist. Für Anwendungen, die vom bisherigen Verhalten abhängen, muss dieses Verhalten nicht übernommen werden, wenn Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei die folgende Konfigurationseinstellung hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter .NET Framework 4.6.2 oder einer höheren Version ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem <code>&lt;runtime&gt;</code>-Abschnitt der Anwendungskonfigurationsdatei die folgende Konfigurationseinstellung hinzugefügt wird:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.6.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType></li></ul>|

