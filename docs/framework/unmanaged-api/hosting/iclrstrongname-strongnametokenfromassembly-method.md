---
title: Méthode ICLRStrongName::StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffc1ed158caea1e3ddbc2dc1f4f828e0618c722e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656776"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a>Méthode ICLRStrongName::StrongNameTokenFromAssembly
Crée un jeton de nom fort à partir du fichier d’assembly spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `wszFilePath`  
 [in] Le chemin d’accès au fichier exécutable portable (PE) pour l’assembly.  
  
 `ppbStrongNameToken`  
 [out] Le jeton de nom fort retourné.  
  
 `pcbStrongNameToken`  
 [out] La taille, en octets, du jeton de nom fort.  
  
## <a name="return-value"></a>Valeur de retour  
 `S_OK` Si la méthode a réussi ; Sinon, une valeur HRESULT qui indique un échec (consultez [valeurs HRESULT courantes](https://go.microsoft.com/fwlink/?LinkId=213878) pour obtenir la liste).  
  
## <a name="remarks"></a>Notes  
 Un jeton de nom fort est la forme abrégée d’une clé publique. Le jeton est un hachage 64 bits qui est créé à partir de la clé publique utilisée pour signer l’assembly. Le jeton est une partie du nom fort pour l’assembly et peut être lues à partir des métadonnées d’assembly.  
  
 Une fois que le jeton est créé, vous devez appeler la [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) méthode pour libérer la mémoire allouée.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MetaHost.h  
  
 **Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi
- [StrongNameTokenFromAssemblyEx, méthode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [ICLRStrongName, interface](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
