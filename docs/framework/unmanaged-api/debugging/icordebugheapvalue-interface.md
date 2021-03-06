---
title: ICorDebugHeapValue, interface
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5263474b7b5001d561652291c23220da0a942bd1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980566"
---
# <a name="icordebugheapvalue-interface"></a>ICorDebugHeapValue, interface

Une sous-classe de « ICorDebugValue » qui représente un objet qui a été collecté par le garbage collector du common language runtime (CLR).  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[CreateRelocBreakpoint, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|Non implémenté.|  
|[IsValid, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|Obtient une valeur qui indique si l’objet représenté par cet `ICorDebugHeapValue` est valide, ou a été récupéré par le garbage collector. Cette méthode a été déconseillée dans le .NET Framework version 2.0.|  
  
## <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Cette interface ne prend pas en charge l'appel à distance, que ce soit entre ordinateurs ou entre processus.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi



- [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
