---
title: '&lt;privacyNoticeAt&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30b3f0bdd1aa02473470c354a730bcfa450f0264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltprivacynoticeatgt"></a>&lt;privacyNoticeAt&gt;
表示一个配置元素，该元素指定 `wsFederationHttp` 绑定中使用的隐私声明。  
  
 \<system.serviceModel >  
\<绑定 >  
\<customBinding >  
\<绑定 >  
\<privacyNotice >  
  
## <a name="syntax"></a>语法  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`url`|一个字符串，指定隐私声明位于的 URI。|  
|`version`|一个整数，指定此隐私声明的版本。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<绑定 >](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
