---
title: CoUninitializeEE, fonction
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c4e22c2e80af37177294d86c2e5775a5c296fe7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211856"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE, fonction
`CoUninitializeEE` est obsolète et n’offre aucune fonctionnalité.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Notes  
 Le moteur d’exécution du common language runtime ne peut pas être déchargé d’un processus. Pour arrêter le moteur d’exécution, appelez [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).  
  
## <a name="see-also"></a>Voir aussi
- [CoInitializeEE, fonction](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [Fonctions statiques globales des métadonnées](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
