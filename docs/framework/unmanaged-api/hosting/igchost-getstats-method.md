---
title: IGCHost::GetStats-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: c86786a34ff236fb57a1ea6bc4d00b9cd5c4a717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134897"
---
# <a name="igchostgetstats-method"></a>IGCHost::GetStats-Methode
Ruft die Statistiken für den aktuellen Status des Garbage Collection Systems ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pStats`  
 [in, out] Ein Zeiger auf eine [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur, die die Statistiken für den aktuellen Status des Garbage Collection Systems enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die Statistiken können von einem intelligenten Zuordnungs System verwendet werden, um das Garbage Collection System zu unterstützen. Beispielsweise kann das Zuordnungs System nach dem Überprüfen der Statistik feststellen, dass es mehr Arbeitsspeicher hinzufügen oder eine Sammlung erzwingen muss.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
