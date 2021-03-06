---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394353"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a>Identität: SignInAsync löst eine Ausnahme für eine nicht authentifizierte Identität aus

Standardmäßig löst `SignInAsync` eine Ausnahme für Prinzipale/Identitäten aus, bei denen `IsAuthenticated` `false` ist.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

`SignInAsync` akzeptiert alle Prinzipale/Identitäten, einschließlich Identitäten, bei denen `IsAuthenticated` `false` ist.

#### <a name="new-behavior"></a>Neues Verhalten

Standardmäßig löst `SignInAsync` eine Ausnahme für Prinzipale/Identitäten aus, bei denen `IsAuthenticated` `false` ist. Es gibt ein neues Flag, mit dem dieses Verhalten unterdrückt werden kann, aber das Standardverhalten wurde geändert.

#### <a name="reason-for-change"></a>Grund für die Änderung

Das alte Verhalten war problematisch, da diese Prinzipale standardmäßig von `[Authorize]` / `RequireAuthenticatedUser()` abgelehnt wurden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

In ASP.NET Core 3.0 Preview 6 gibt es das Flag `RequireAuthenticatedSignIn` in `AuthenticationOptions`, das standardmäßig `true` ist. Legen Sie dieses Flag auf `false` fest, um das alte Verhalten wiederherzustellen.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
