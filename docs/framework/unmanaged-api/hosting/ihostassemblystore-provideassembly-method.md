---
title: IHostAssemblyStore::ProvideAssembly-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124485"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly-Methode
Ruft einen Verweis auf eine Assembly ab, auf die von [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die von [IHostAssemblyManager:: getnonhoststoreassemblys](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)zurückgegeben wird, nicht verwiesen wird. Der Common Language Runtime (CLR) ruft `ProvideAssembly` für jede Assembly auf, die nicht in der Liste angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pBindInfo`  
 in Ein Zeiger auf eine [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) -Instanz, die der Host verwendet, um bestimmte Bindungseigenschaften zu bestimmen, einschließlich der Anwesenheit oder Abwesenheit jeglicher Versions Richtlinien und der Assembly, an die die Bindung erfolgen soll.  
  
 `pAssemblyId`  
 vorgenommen Ein Zeiger auf einen eindeutigen Bezeichner für die angeforderte Assembly für dieses `IStream`.  
  
 `pHostContext`  
 vorgenommen Ein Zeiger auf Host spezifische Daten, die verwendet werden, um den Beweis der angeforderten Assembly zu bestimmen, ohne dass ein Platt Form Aufruf erforderlich ist. `pHostContext` entspricht der <xref:System.Reflection.Assembly.HostContext%2A>-Eigenschaft der verwalteten <xref:System.Reflection.Assembly>-Klasse.  
  
 `ppStmAssemblyImage`  
 vorgenommen Ein Zeiger auf die Adresse einer `IStream`, die das zu ladende portable ausführbare Image (PE) enthält, oder NULL, wenn die Assembly nicht gefunden werden konnte.  
  
 `ppStmPDB`  
 vorgenommen Ein Zeiger auf die Adresse einer `IStream`, die die Programm Debuginformationen (PDB) enthält, oder NULL, wenn die PDB-Datei nicht gefunden wurde.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.|  
|COR_E_FILENOTFOUND (0x80070002)|Die angeforderte Assembly konnte nicht gefunden werden.|  
|E_NOT_SUFFICIENT_BUFFER|Die durch `pAssemblyId` angegebene Puffergröße ist nicht groß genug zum Speichern des Bezeichners, den der Host zurückgeben möchte.|  
  
## <a name="remarks"></a>Hinweise  
 Der für `pAssemblyId` zurückgegebene Identitäts Wert wird vom Host angegeben. Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein. Die CLR verwendet diesen Wert als eindeutigen Bezeichner für den Datenstrom. Jeder Wert wird anhand der Werte für `pAssemblyId` überprüft, die von anderen Aufrufen von `ProvideAssembly`zurückgegeben werden. Wenn der Host denselben `pAssemblyId` Wert für einen anderen `IStream`zurückgibt, überprüft die CLR, ob der Inhalt dieses Streams bereits zugeordnet wurde. Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie des Bilds, anstatt eine neue zu ordnen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
