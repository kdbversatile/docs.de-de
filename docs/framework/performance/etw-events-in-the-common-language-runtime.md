---
title: ETW-Ereignisse in der Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: 49d1141540fb00ab7ef462da5af84f02e6d9fc4d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937856"
---
# <a name="etw-events-in-the-common-language-runtime"></a>ETW-Ereignisse in der Common Language Runtime
Die Common Language Runtime (CLR) stellt nützliche Diagnoseinformationen für die Ereignisablaufverfolgung für Windows (ETW) durch eine große Vielfalt von Ereignissen für das Debuggen und die Profilerstellung bereit. CLR-ETW-Ereignisse nutzen das Windows-ETW-Ablaufverfolgungssystem, um die bestehende Unterstützung für die Profilerstellung und das Debuggen zu erweitern, die von der Common Language Runtime bereitgestellt wird.  
  
 Weitere Informationen zu etw finden Sie im Artikel [verbessern der Debuggen und Leistungsoptimierung mit etw](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) . Weitere Informationen zu Xperf finden Sie im Eintrag [Windows Performance Toolkit – Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) im NTDebugging-Blog.  
  
 Der .NET Framework 4 oder höher ist für alle in den Ereignis Themen beschriebenen Ereignisse erforderlich. Das Betriebssystem „Windows Vista“ ist die mindestens erforderliche Version für den Client, und Windows Server 2008 ist die mindestens erforderliche Version für den Server.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)](controlling-logging.md)  
 Beschreibt die Tools und Befehle zum Erfassen und Anzeigen von ETW-Ereignissen.  
  
 [CLR ETW Providers (CLR-ETW-Anbieter)](clr-etw-providers.md)  
 Bietet Informationen zu den Runtime- und Rundownanbietern, und wie Sie diese für die ETW-Datensammlung nutzen können.  
  
 [CLR ETW Keywords and Levels (CLR-ETW-Schlüsselwörter und -Ebenen)](clr-etw-keywords-and-levels.md)  
 Beschreibt die Schlüsselwörter für die Runtime- und Rundownanbieter, die das Filtern der Ereignisse nach Kategorie ermöglichen.  
  
 [CLR-ETW-Ereignisse](clr-etw-events.md)  
 Bietet detaillierte Informationen zu CLR-ETW-Ereignissen sowie zu deren Schlüsselwörtern, Ebenen und Ereignisdaten.  
  
## <a name="see-also"></a>Siehe auch

- [ETW Events in the .NET Framework (ETW-Ereignisse in .NET Framework)](etw-events.md)
