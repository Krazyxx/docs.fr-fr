---
title: "ICorProfilerInfo::ForceGC, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.ForceGC
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3a3389c6675e992c362e3e0a77dfbc97e142ef8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="5c178-102">ICorProfilerInfo::ForceGC, méthode</span><span class="sxs-lookup"><span data-stu-id="5c178-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="5c178-103">Force un garbage collection pour se produire dans le common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5c178-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c178-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5c178-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5c178-105">Remarques</span><span class="sxs-lookup"><span data-stu-id="5c178-105">Remarks</span></span>  
 <span data-ttu-id="5c178-106">Le `ForceGC` méthode doit être appelée uniquement à partir d’un thread qui n’a jamais exécuté du code managé et n’a pas de rappels de profileur sur sa pile.</span><span class="sxs-lookup"><span data-stu-id="5c178-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="5c178-107">L’implémentation la plus commode consiste à créer un thread séparé dans le profileur appelle `ForceGC` quand il est signalé.</span><span class="sxs-lookup"><span data-stu-id="5c178-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c178-108">Spécifications</span><span class="sxs-lookup"><span data-stu-id="5c178-108">Requirements</span></span>  
 <span data-ttu-id="5c178-109">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c178-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c178-110">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c178-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c178-111">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c178-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c178-112">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c178-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c178-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c178-113">See Also</span></span>  
 [<span data-ttu-id="5c178-114">ICorProfilerInfo (Interface)</span><span class="sxs-lookup"><span data-stu-id="5c178-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)