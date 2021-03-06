---
title: 'ICorProfilerInfo8:: getdynamicfunctioninfo'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 45a40d49cea2dd5f881fbd47cc2fb4bd96e8f9ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243988"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>ICorProfilerInfo8:: getdynamicfunctioninfo-Methode

Ruft Informationen zu dynamischen Methoden ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

#### <a name="parameters"></a>Parameter

`functionId` \
in Die ID der Funktion, für die Informationen abgerufen werden sollen.

`moduleId` \
in Ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.

`ppvSig` \
vorgenommen Ein Zeiger auf die Signatur der Funktion.

`pbSig` \
vorgenommen Ein Zeiger auf die Anzahl von Bytes für die Funktions Signatur.

`cchName` \
[in] Die maximale Größe des `wszName`-Arrays.

`pcchName` \
vorgenommen Die Anzahl der Zeichen im `wszName` Array.

`wszName` \
vorgenommen Ein Array von `WCHAR` , bei dem es sich um den Namen der Funktion handelt, sofern vorhanden.

## <a name="remarks"></a>Hinweise

Bestimmte Methoden wie IL-Stub oder LCG verfügen über keine zugeordneten Metadaten, die mithilfe der APIs [IMetaDataImport](../metadata/imetadataimport-interface.md) und [IMetaDataImport2](../metadata/imetadataimport2-interface.md) abgerufen werden können. Solche Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.

Diese API kann verwendet werden, um Informationen zu dynamischen Methoden, einschließlich eines anzeigen Amens, abzurufen, falls verfügbar.

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** Corprof. idl, Corprof. h

**Fern** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo8-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
