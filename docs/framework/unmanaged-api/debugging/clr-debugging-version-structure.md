---
title: CLR_DEBUGGING_VERSION, structure
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4049b0ed25d4c0fda00fe9b0dad5887fa4f6996
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506938"
---
# <a name="clrdebuggingversion-structure"></a>CLR_DEBUGGING_VERSION, structure
Définit la version du produit de CLR (Common Language Runtime) à des fins de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`wStructVersion`|Le numéro de version de structure|  
|`wMajor`|Numéro de version principale.|  
|`wMinor`|Numéro de version secondaire.|  
|`wBuild`|Le numéro de build.|  
|`wRevision`|Le numéro de révision.|  
  
## <a name="remarks"></a>Notes  
 Le `CLR_DEBUGGING_VERSION` structure est identique à la structure COR_VERSION, toutefois, le `CLR_DEBUGGING_VERSION` structure fournit un champ de version de structure supplémentaire (`wStructVersion`). Actuellement, ce champ doit être défini à zéro.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [Structures de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)
