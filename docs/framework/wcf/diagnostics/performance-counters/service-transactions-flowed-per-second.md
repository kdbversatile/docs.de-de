---
title: 'Dienst: Transaktionen Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: e8fbc314321a46fd3539998bd3dd22770086ca37
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164007"
---
# <a name="service-transactions-flowed-per-second"></a>Dienst: Transaktionen Flowed Per Second
Indikatorname: Transactions Flowed Per Second.  
  
## <a name="description"></a>Beschreibung  
 Anzahl der Transaktionen, die innerhalb einer Sekunde in Vorgänge in diesem Dienst übergegangen sind.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
