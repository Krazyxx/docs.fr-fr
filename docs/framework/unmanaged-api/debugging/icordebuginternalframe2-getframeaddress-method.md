---
title: ICorDebugInternalFrame2::GetFrameAddress, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab729bafdd8987a7c5a03145e02f5c8e5d441a3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711614"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress, méthode
Retourne l’adresse de la pile du frame interne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pAddress`  
 [out] Pointeur vers le `CORDB_ADDRESS` pour le frame interne.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|L’adresse du frame interne a été retourné avec succès.|  
|E_FAIL|L’adresse du frame interne n’a pas pu être retourné.|  
|E_INVALIDARG|`pAddress` a la valeur `null`.|  
  
## <a name="remarks"></a>Notes  
 La valeur retournée dans `pAddress` peut être utilisée pour déterminer l’emplacement du frame interne par rapport aux autres frames sur la pile. Même sur les ordinateurs basés sur IA-64, le frame interne se trouve uniquement sur la pile, et aucun pointeur correspondant à un magasin de stockage.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [ICorDebugInternalFrame2, interface](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)
