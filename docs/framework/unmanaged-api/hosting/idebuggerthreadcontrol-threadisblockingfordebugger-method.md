---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger, méthode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa72c136e98f80df6d2868c447e1c535ae61af06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739626"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a>IDebuggerThreadControl::ThreadIsBlockingForDebugger, méthode
Avertit l’hôte que le thread qui envoie ce rappel concerne à blocs dans les services de débogage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a>Notes  
 Le `ThreadIsBlockingForDebugger` méthode est toujours appelée sur un thread d’exécution.  
  
 Le `ThreadIsBlockingForDebugger` méthode donne à l’hôte une possibilité d’effectuer une autre action pendant que le thread bloque.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [IDebuggerThreadControl, interface](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
