---
title: ICorDebugHeapValue3::GetMonitorEventWaitList, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27815cf8cb7fdcd1c01f26391c317d52bbb388ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628511"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList, méthode
Fournit une liste ordonnée de threads qui sont en attente sur l’événement qui est associé à un verrou du moniteur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ppThreadEnum`  
 [out] L’énumérateur ICorDebugThreadEnum qui fournit la liste ordonnée des threads.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|The list is not empty.|  
|S_FALSE|La liste est vide.|  
  
## <a name="exceptions"></a>Exceptions  
  
## <a name="remarks"></a>Notes  
 Le premier thread dans la liste est le premier thread est libéré par l’appel suivant à <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>. Le thread suivant dans la liste est publié sur l’appel suivant et ainsi de suite.  
  
 Si la liste n’est pas vide, cette méthode retourne S_OK. Si la liste est vide, la méthode retourne S_FALSE ; Dans ce cas, l’énumération est toujours valide, bien qu’il soit vide.  
  
 Dans les deux cas, l’interface d’énumération est utilisable uniquement pour la durée de l’état synchronisé actuel. Toutefois, les interfaces du thread distribuées à partir de celui-ci sont valides jusqu'à ce que le thread se termine.  
  
 Si `ppThreadEnum` n’est pas un pointeur valide, le résultat est indéfini.  
  
 Si une erreur se produit et il est impossible de déterminer qui, le cas échéant, les threads sont en attente pour l’analyse, la méthode retourne un HRESULT qui indique un échec.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)
