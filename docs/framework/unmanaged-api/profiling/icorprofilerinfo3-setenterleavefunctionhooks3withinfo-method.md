---
title: "ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a30dde6f406cfb6d1140e7cd8e2a8f8f3ab40006
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="05451-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo 方法</span><span class="sxs-lookup"><span data-stu-id="05451-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="05451-103">指定将调用的探查器实现函数[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)托管函数的挂钩。</span><span class="sxs-lookup"><span data-stu-id="05451-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05451-104">语法</span><span class="sxs-lookup"><span data-stu-id="05451-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05451-105">参数</span><span class="sxs-lookup"><span data-stu-id="05451-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="05451-106">[in]指向要用作的实现的`FunctionEnter3WithInfo`回调。</span><span class="sxs-lookup"><span data-stu-id="05451-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="05451-107">[in]指向要用作的实现的`FunctionLeave3WithInfo`回调。</span><span class="sxs-lookup"><span data-stu-id="05451-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="05451-108">[in]指向要用作的实现的`FunctionTailcall3WithInfo`回调。</span><span class="sxs-lookup"><span data-stu-id="05451-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05451-109">备注</span><span class="sxs-lookup"><span data-stu-id="05451-109">Remarks</span></span>  
 <span data-ttu-id="05451-110">[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)挂钩提供堆栈帧和参数检查。</span><span class="sxs-lookup"><span data-stu-id="05451-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="05451-111">若要访问该信息，请`COR_PRF_ENABLE_FUNCTION_ARGS`， `COR_PRF_ENABLE_FUNCTION_RETVAL`，和/或`COR_PRF_ENABLE_FRAME_INFO`标志必须设置。</span><span class="sxs-lookup"><span data-stu-id="05451-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="05451-112">探查器可以使用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法来设置事件标志，然后使用`SetEnterLeaveFunctionHooks3WithInfo`方法注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="05451-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="05451-113">一次只有一组回调可能处于活动状态和最新版本将优先。</span><span class="sxs-lookup"><span data-stu-id="05451-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="05451-114">因此，如果探查器同时调用[SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)和`SetEnterLeaveFunctionHooks3WithInfo`，`SetEnterLeaveFunctionHooks3WithInfo`使用。</span><span class="sxs-lookup"><span data-stu-id="05451-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="05451-115">`SetEnterLeaveFunctionHooks3WithInfo`可能仅从探查器的调用方法[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="05451-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05451-116">要求</span><span class="sxs-lookup"><span data-stu-id="05451-116">Requirements</span></span>  
 <span data-ttu-id="05451-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05451-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05451-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05451-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05451-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05451-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05451-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05451-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05451-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05451-121">See Also</span></span>  
 [<span data-ttu-id="05451-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="05451-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="05451-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="05451-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="05451-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="05451-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="05451-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="05451-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="05451-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="05451-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="05451-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="05451-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="05451-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="05451-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="05451-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="05451-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 [<span data-ttu-id="05451-130">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="05451-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="05451-131">分析接口</span><span class="sxs-lookup"><span data-stu-id="05451-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="05451-132">分析</span><span class="sxs-lookup"><span data-stu-id="05451-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)