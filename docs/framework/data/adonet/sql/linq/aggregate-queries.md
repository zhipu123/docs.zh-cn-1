---
title: "聚合查询"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4aa6c0a9103bc4a906ecdfb51a55069e6b8b790
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="aggregate-queries"></a>聚合查询
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 支持 `Average`、`Count`、`Max`、`Min` 和 `Sum` 聚合运算符。 请注意 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中聚合运算符的以下特征：  
  
-   聚合查询是立即执行的。  
  
     有关详细信息，请参阅 [LINQ 查询简介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。  
  
-   聚合查询通常返回一个数字，而非一个集合。  
  
     有关详细信息，请参阅[聚合操作](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4)。  
  
-   不能对匿名类型调用聚合。  
  
 以下主题中的示例来自 Northwind 示例数据库。 有关详细信息，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [从数值序列中返回平均值](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 演示如何使用 <xref:System.Linq.Enumerable.Average%2A> 运算符。  
  
 [对序列中元素的数目进行计数](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 演示如何使用 <xref:System.Linq.Enumerable.Count%2A> 运算符。  
  
 [查找数值序列中的最大值](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 演示如何使用 <xref:System.Linq.Enumerable.Max%2A> 运算符。  
  
 [查找数值序列中的最小值](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 演示如何使用 <xref:System.Linq.Enumerable.Min%2A> 运算符。  
  
 [计算数值序列中值的和](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 演示如何使用 <xref:System.Linq.Enumerable.Sum%2A> 运算符。  
  
## <a name="related-sections"></a>相关章节  
 [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 提供指向 Visual Basic 和 C# 中 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的链接。  
  
 [查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 提供指向特定主题的链接，这些主题解释有关在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中设计 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的一些概念。  
  
 [LINQ 查询简介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 解释 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中查询的工作原理。
