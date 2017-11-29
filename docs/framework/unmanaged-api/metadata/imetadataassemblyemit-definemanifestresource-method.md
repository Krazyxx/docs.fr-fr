---
title: "IMetaDataAssemblyEmit::DefineManifestResource, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="ab8af-102">IMetaDataAssemblyEmit::DefineManifestResource, méthode</span><span class="sxs-lookup"><span data-stu-id="ab8af-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="ab8af-103">Crée une structure `ManifestResource` contenant les métadonnées pour la ressource de manifeste spécifiée et retourne le jeton de métadonnées associé.</span><span class="sxs-lookup"><span data-stu-id="ab8af-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab8af-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ab8af-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab8af-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ab8af-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ab8af-106">[in] Le nom de la ressource.</span><span class="sxs-lookup"><span data-stu-id="ab8af-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="ab8af-107">[in] Un jeton de métadonnées de type `mdtFile` ou `mdtAssemblyRef` qui mappe au fournisseur de ressources.</span><span class="sxs-lookup"><span data-stu-id="ab8af-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="ab8af-108">Une valeur NULL indique que le fichier dans lequel les métadonnées sont incorporées est le fournisseur de ressources.</span><span class="sxs-lookup"><span data-stu-id="ab8af-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="ab8af-109">[in] Offset au début de la ressource dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="ab8af-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="ab8af-110">Pour les ressources dans les fichiers autonomes, il sera toujours zéro.</span><span class="sxs-lookup"><span data-stu-id="ab8af-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="ab8af-111">Si la ressource est incorporée dans un fichier exécutable portable (fichier exécutable portable), il s’agit d’un décalage de l’objet BLOB, qui commence à l’emplacement spécifié dans le fichier d’en-tête cor.h de ressource.</span><span class="sxs-lookup"><span data-stu-id="ab8af-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="ab8af-112">[in] Combinaison de bits des valeurs d’indicateurs qui spécifient les paramètres de propriété pour la définition de ressource.</span><span class="sxs-lookup"><span data-stu-id="ab8af-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="ab8af-113">[out] Pointeur vers le jeton de métadonnées retourné.</span><span class="sxs-lookup"><span data-stu-id="ab8af-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab8af-114">Remarques</span><span class="sxs-lookup"><span data-stu-id="ab8af-114">Remarks</span></span>  
 <span data-ttu-id="ab8af-115">Un `ManifestResource` structure de métadonnées doit être définie pour chaque ressource est implémentée dans chacun des fichiers de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="ab8af-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab8af-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="ab8af-116">Requirements</span></span>  
 <span data-ttu-id="ab8af-117">**Plateforme :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab8af-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab8af-118">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab8af-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab8af-119">**Bibliothèque :** utilisé en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab8af-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab8af-120">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab8af-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8af-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab8af-121">See Also</span></span>  
 [<span data-ttu-id="ab8af-122">IMetaDataAssemblyEmit (Interface)</span><span class="sxs-lookup"><span data-stu-id="ab8af-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)