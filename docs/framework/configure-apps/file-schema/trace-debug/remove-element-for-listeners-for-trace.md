---
title: "&lt;删除&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7bc4136fb917ee9b63b7cca26ba1834de21f542e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;删除&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;
删除从侦听器**侦听器**集合。  
  
 \<configuration>  
\<system.diagnostics >  
\<跟踪 >  
\<侦听器 >  
\<删除 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**name**|必需的特性。<br /><br /> 从删除的侦听器名称**侦听器**集合。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`listeners`|指定收集，侦听器存储区，并将消息路由。 侦听器将跟踪输出定向到适当的目标。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`trace`|配置 ASP.NET 跟踪服务。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  删除<xref:System.Diagnostics.DefaultTraceListener>从`Listeners`集合会更改的行为<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>， <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>， <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>，和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法。 调用`Assert`或`Fail`方法通常会导致显示一个消息框，但如果不显示消息框<xref:System.Diagnostics.DefaultTraceListener>不在`Listeners`集合。  
  
## <a name="example"></a>示例  
 下面的示例演示如何从跟踪中删除默认跟踪侦听器**侦听器**集合。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [跟踪和调试设置架构](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
