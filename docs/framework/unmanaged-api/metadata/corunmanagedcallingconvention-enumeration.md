---
title: CorUnmanagedCallingConvention-Enumeration
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 58d30e71929d314ee36adb9f83270858ff8a161b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442441"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention-Enumeration
Gibt die Aufruf Konventionen für nicht verwalteten Code an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Die C-Programmiersprachen Aufruf Konvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Die Standard Aufruf Konvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Die "This"-Aufruf Konvention.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Die "schnelle" Aufruf Konvention.|  
|`IMAGE_CEE_CS_CALLCONV_C`|Nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Nicht verwendet.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Nicht verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR unterstützt die "schnelle" Aufruf Konvention nicht in der .NET Framework Version 1,0.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corhdr. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Metadatenenumerationen](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
