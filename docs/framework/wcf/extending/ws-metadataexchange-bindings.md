---
title: "WS-MetadataExchange 绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d305f3bf34b3b14da566fa792552e24e695ef33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ws-metadataexchange-bindings"></a>WS-MetadataExchange 绑定
本主题说明如何为各种传输构造默认的元数据交换绑定。  
  
## <a name="the-default-bindings"></a>默认绑定  
  
|默认绑定名称|绑定的构造方式|  
|--------------------------|------------------------------------|  
|MexHttpBinding|一个禁用传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。|  
|MexHttpsBinding|一个支持传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。|  
|MexNamedPipeBinding|一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>。|  
|MexTcpBinding|一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>。|
