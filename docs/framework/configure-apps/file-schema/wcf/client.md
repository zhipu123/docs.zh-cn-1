---
title: "&lt;客户端&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d52d74c36ea1b1d722d781f554f8cc6691d53e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientgt"></a>&lt;客户端&gt;
`client` 元素定义客户端可以连接的终结点的列表。  
  
 \<系统。ServiceModel >  
\<客户端 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<终结点 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|包含终结点元素集合，这些元素指定此客户端可连接到的终结点。|  
|[\<元数据 >](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|包含用于处理元数据的设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|所有 Windows Communication Foundation (WCF) 配置元素的根元素。|  
  
## <a name="remarks"></a>备注  
 `client` 节定义客户端可以连接的终结点的列表。 客户端节中列出的每个终结点都定义了它自己的绑定、行为和协定。 它由 `name` 和 `contract` 属性共同进行唯一标识。 客户端代码指定要连接到该客户端实现的服务终结点的 `name`。 如果省略 `name` 属性，则该终结点将作为其实现的协定的默认终结点。  
  
 此外，本节还指定了用于处理元数据的设置。  
  
## <a name="example"></a>示例  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [WCF 客户端配置](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [客户端](../../../../../docs/framework/wcf/feature-details/clients.md)
