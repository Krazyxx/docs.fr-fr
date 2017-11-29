---
title: "ICorProfilerInfo3::GetFunctionLeave3Info, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04f48562e1ddc07ad1ae166ec44ac7de8afd4312
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="b5b7b-102">ICorProfilerInfo3::GetFunctionLeave3Info, méthode</span><span class="sxs-lookup"><span data-stu-id="b5b7b-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="b5b7b-103">Fournit le frame de pile et la valeur de retour de la fonction signalée au profileur par la [FunctionLeave3WithInfo fonction](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (fonction).</span><span class="sxs-lookup"><span data-stu-id="b5b7b-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="b5b7b-104">Cette méthode peut être appelée uniquement pendant le rappel de `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b7b-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b5b7b-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5b7b-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b5b7b-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b5b7b-107">[in] Le `FunctionID` de la fonction qui retourne.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="b5b7b-108">[in] Handle opaque qui représente des informations sur un frame de pile donné.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="b5b7b-109">Le profileur doit fournir les mêmes `eltInfo` qui a été attribué au profileur par la [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (fonction).</span><span class="sxs-lookup"><span data-stu-id="b5b7b-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="b5b7b-110">[out] Handle opaque qui représente des informations génériques sur un frame de pile donné.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="b5b7b-111">Ce handle est uniquement valide pendant le rappel `FunctionLeave3WithInfo` au cours duquel le profileur a appelé la méthode `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="b5b7b-112">[out] Un pointeur vers un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure qui contient la valeur retournée à partir de la fonction.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="b5b7b-113">Pour accéder aux informations de valeur de retour, le `COR_PRF_ENABLE_FUNCTION_RETVAL` indicateur doit être défini.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="b5b7b-114">Le profileur peut utiliser le [méthode ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) pour définir les indicateurs d’événement.</span><span class="sxs-lookup"><span data-stu-id="b5b7b-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5b7b-115">Remarques</span><span class="sxs-lookup"><span data-stu-id="b5b7b-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5b7b-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b5b7b-116">Requirements</span></span>  
 <span data-ttu-id="b5b7b-117">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5b7b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5b7b-118">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5b7b-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5b7b-119">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5b7b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5b7b-120">**Versions du .NET framework :**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5b7b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b7b-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5b7b-121">See Also</span></span>  
 [<span data-ttu-id="b5b7b-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b5b7b-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="b5b7b-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b5b7b-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="b5b7b-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b5b7b-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="b5b7b-125">ICorProfilerInfo3 (Interface)</span><span class="sxs-lookup"><span data-stu-id="b5b7b-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="b5b7b-126">Interfaces de profilage</span><span class="sxs-lookup"><span data-stu-id="b5b7b-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="b5b7b-127">Profilage</span><span class="sxs-lookup"><span data-stu-id="b5b7b-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)