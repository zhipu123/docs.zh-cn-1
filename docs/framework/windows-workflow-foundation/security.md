---
title: "安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 461bc36fd85a158e67c29c3f4ad001997218c824
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="security"></a>安全性
SQL 工作流实例存储使用以下数据库安全角色确保安全访问持久性数据库中的实例状态信息。  
  
-   **System.Activities.DurableInstancing.InstanceStoreUsers**。 此角色具有对公共视图的读写访问权以及对创建、加载和保存实例所涉及的存储过程的执行权限。  
  
-   **System.Activities.DurableInstancing.InstanceStoreObservers**。 此角色具有对公共视图的只读访问权。  
  
-   **System.Activities.DurableInstancing.WorkflowActivationUsers**。 此角色对在实例激活过程中涉及的存储过程具有执行权限。 有关实例激活的详细信息，请参阅[实例激活](../../../docs/framework/windows-workflow-foundation/instance-activation.md)。 应将运行泛型宿主（如 [!INCLUDE[dublin](../../../includes/dublin-md.md)] 的工作流管理服务）的用户帐户添加到此数据库角色中。  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]安全性的持久性存储的 Windows Server App Fabric，请参阅[App Fabric 中持久性存储的安全配置](http://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  有权访问自己存在实例存储区中的实例数据的客户端对同一实例存储区中所有其他实例也具有访问权限。 实例存储区不支持在实例级别指定安全权限。 您应创建单独的实例存储区并映射不同的组/用户，使他们有权访问的存储区有所不同。
