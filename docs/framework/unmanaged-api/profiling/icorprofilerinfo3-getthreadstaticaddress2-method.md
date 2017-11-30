---
title: "ICorProfilerInfo3::GetThreadStaticAddress2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d657f0d6a28f19c45910fa354b7b40822ad12947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="15fa8-102">ICorProfilerInfo3::GetThreadStaticAddress2 方法</span><span class="sxs-lookup"><span data-stu-id="15fa8-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="15fa8-103">获取指定线程和应用程序域范围内的指定线程静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="15fa8-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15fa8-104">语法</span><span class="sxs-lookup"><span data-stu-id="15fa8-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15fa8-105">参数</span><span class="sxs-lookup"><span data-stu-id="15fa8-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="15fa8-106">[in]包含请求的线程静态字段的类 ID。</span><span class="sxs-lookup"><span data-stu-id="15fa8-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="15fa8-107">[in]请求的线程静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="15fa8-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="15fa8-108">[in] 应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="15fa8-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="15fa8-109">[in]是请求的静态字段的作用域的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="15fa8-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="15fa8-110">[out]指向位于指定线程静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="15fa8-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15fa8-111">备注</span><span class="sxs-lookup"><span data-stu-id="15fa8-111">Remarks</span></span>  
 <span data-ttu-id="15fa8-112">`GetThreadStaticAddress2`方法可能会返回以下项之一：</span><span class="sxs-lookup"><span data-stu-id="15fa8-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="15fa8-113">如果尚未分配为给定的静态字段指定的上下文中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="15fa8-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="15fa8-114">可能会在垃圾回收堆中的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="15fa8-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="15fa8-115">这些地址可能会变得无效垃圾回收后，以便垃圾回收后，探查器不应假定它们有效。</span><span class="sxs-lookup"><span data-stu-id="15fa8-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="15fa8-116">完成的类的类构造函数之前，`GetThreadStaticAddress2`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的静态字段的一些和定位垃圾回收对象。</span><span class="sxs-lookup"><span data-stu-id="15fa8-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="15fa8-117">[Icorprofilerinfo2:: Getthreadstaticaddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)方法类似于是`GetThreadStaticAddress2`方法，但不是接受的应用程序域自变量。</span><span class="sxs-lookup"><span data-stu-id="15fa8-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15fa8-118">要求</span><span class="sxs-lookup"><span data-stu-id="15fa8-118">Requirements</span></span>  
 <span data-ttu-id="15fa8-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15fa8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15fa8-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15fa8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15fa8-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15fa8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15fa8-122">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15fa8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15fa8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15fa8-123">See Also</span></span>  
 [<span data-ttu-id="15fa8-124">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="15fa8-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="15fa8-125">分析接口</span><span class="sxs-lookup"><span data-stu-id="15fa8-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="15fa8-126">分析</span><span class="sxs-lookup"><span data-stu-id="15fa8-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)