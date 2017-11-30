---
title: "ICorRuntimeHost 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 844648cd2cfafc561e27bea870703ee3a55fb404
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="7ee93-102">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="7ee93-102">ICorRuntimeHost Interface</span></span>
<span data-ttu-id="7ee93-103">提供使主机能够启动和停止公共语言运行时 (CLR) 显式创建和配置应用程序域，以访问默认域，以及枚举进程中运行的所有域的方法。</span><span class="sxs-lookup"><span data-stu-id="7ee93-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="7ee93-104">在.NET Framework 2.0 版中，此接口被取代[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee93-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ee93-105">方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-105">Methods</span></span>  
  
|<span data-ttu-id="7ee93-106">方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-106">Method</span></span>|<span data-ttu-id="7ee93-107">描述</span><span class="sxs-lookup"><span data-stu-id="7ee93-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ee93-108">CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-108">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|<span data-ttu-id="7ee93-109">将域枚举数重置回域列表的开头。</span><span class="sxs-lookup"><span data-stu-id="7ee93-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="7ee93-110">CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-110">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|<span data-ttu-id="7ee93-111">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="7ee93-111">Creates an application domain.</span></span> <span data-ttu-id="7ee93-112">调用方会收到类型的接口指针<xref:System._AppDomain>到类型的实例<xref:System.AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="7ee93-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="7ee93-113">CreateDomainEx 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-113">CreateDomainEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|<span data-ttu-id="7ee93-114">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="7ee93-114">Creates an application domain.</span></span> <span data-ttu-id="7ee93-115">此方法允许调用方传递一个 IAppDomainSetup 实例，以便配置其他功能，则返回的<xref:System._AppDomain>实例。</span><span class="sxs-lookup"><span data-stu-id="7ee93-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="7ee93-116">CreateDomainSetup 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-116">CreateDomainSetup Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="7ee93-117">获取类型的接口指针`IAppDomainSetup`到<xref:System.AppDomainSetup>实例。</span><span class="sxs-lookup"><span data-stu-id="7ee93-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="7ee93-118">`IAppDomainSetup`提供用于配置应用程序域的方面，它将在创建之前方法。</span><span class="sxs-lookup"><span data-stu-id="7ee93-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="7ee93-119">CreateEvidence 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-119">CreateEvidence Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|<span data-ttu-id="7ee93-120">获取类型的接口指针<xref:System.Security.Principal.IIdentity>，这样，主机可以在创建安全证据要传递给[CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)或[CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee93-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="7ee93-121">CreateLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-121">CreateLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="7ee93-122">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="7ee93-122">Do not use.</span></span>|  
|[<span data-ttu-id="7ee93-123">CurrentDomain 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-123">CurrentDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|<span data-ttu-id="7ee93-124">获取类型的接口指针<xref:System._AppDomain>表示加载到当前线程上的域。</span><span class="sxs-lookup"><span data-stu-id="7ee93-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="7ee93-125">DeleteLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-125">DeleteLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="7ee93-126">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="7ee93-126">Do not use.</span></span>|  
|[<span data-ttu-id="7ee93-127">EnumDomains 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-127">EnumDomains Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|<span data-ttu-id="7ee93-128">域当前进程中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="7ee93-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="7ee93-129">GetConfiguration 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-129">GetConfiguration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="7ee93-130">获取允许宿主指定 CLR 的回调配置的对象。</span><span class="sxs-lookup"><span data-stu-id="7ee93-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="7ee93-131">GetDefaultDomain 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-131">GetDefaultDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="7ee93-132">获取类型的接口指针<xref:System._AppDomain>，它表示当前进程的默认域。</span><span class="sxs-lookup"><span data-stu-id="7ee93-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="7ee93-133">LocksHeldByLogicalThread 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-133">LocksHeldByLogicalThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="7ee93-134">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="7ee93-134">Do not use.</span></span>|  
|[<span data-ttu-id="7ee93-135">MapFile 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-135">MapFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|<span data-ttu-id="7ee93-136">将指定的文件映射到内存中。</span><span class="sxs-lookup"><span data-stu-id="7ee93-136">Maps the specified file into memory.</span></span> <span data-ttu-id="7ee93-137">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="7ee93-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="7ee93-138">NextDomain 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-138">NextDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|<span data-ttu-id="7ee93-139">枚举中的下一个域中获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="7ee93-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="7ee93-140">Start 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-140">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|<span data-ttu-id="7ee93-141">启动 CLR。</span><span class="sxs-lookup"><span data-stu-id="7ee93-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="7ee93-142">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-142">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|<span data-ttu-id="7ee93-143">停止执行当前进程的运行时中的代码。</span><span class="sxs-lookup"><span data-stu-id="7ee93-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="7ee93-144">SwitchInLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-144">SwitchInLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="7ee93-145">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="7ee93-145">Do not use.</span></span>|  
|[<span data-ttu-id="7ee93-146">SwitchOutLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-146">SwitchOutLogicalThreadState Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="7ee93-147">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="7ee93-147">Do not use.</span></span>|  
|[<span data-ttu-id="7ee93-148">UnloadDomain 方法</span><span class="sxs-lookup"><span data-stu-id="7ee93-148">UnloadDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="7ee93-149">卸载指定的应用程序域中从当前进程。</span><span class="sxs-lookup"><span data-stu-id="7ee93-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ee93-150">要求</span><span class="sxs-lookup"><span data-stu-id="7ee93-150">Requirements</span></span>  
 <span data-ttu-id="7ee93-151">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee93-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee93-152">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ee93-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ee93-153">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7ee93-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ee93-154">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="7ee93-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee93-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee93-155">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="7ee93-156">承载</span><span class="sxs-lookup"><span data-stu-id="7ee93-156">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="7ee93-157">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="7ee93-157">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="7ee93-158">运行时主机</span><span class="sxs-lookup"><span data-stu-id="7ee93-158">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [<span data-ttu-id="7ee93-159">承载接口</span><span class="sxs-lookup"><span data-stu-id="7ee93-159">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="7ee93-160">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="7ee93-160">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)