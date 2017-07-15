---
title: "消息流概述 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fb0899e1-84cc-4d90-b45b-dc5a50063943
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 消息流概述
在包含相互连接的服务的分布式系统中，必须确定服务之间的因果关系。  了解作为请求流的一部分的各种组件对于支持关键方案（如运行状况监视、疑难解答和根源分析）非常重要。  为了在各种服务之间启用跟踪相关性，我们通过以下功能在 .NET Framework 4 中添加了相关支持：  
  
-   分析跟踪：采用 Windows 事件跟踪 \(ETW\) 的高性能、低详细级别的跟踪功能。  
  
-   WCF\/WF 服务的端到端活动模型：此功能支持由 <xref:System.ServiceModel> 和 <xref:System.WorkflowModel> 命名空间生成的跟踪相关性。  
  
-   WF 的 ETW 跟踪：此功能使用由 WF 服务生成的跟踪记录来查看工作流的当前状态和进度。  
  
 可使用跟踪或跟踪记录中记录的错误来查找代码缺陷或格式不正确的消息。  可使用事件的邮件头中的“相关性”节点的 ActivityId 属性来确定出错的活动。  若要按活动 ID 启用消息流跟踪，请参见[配置消息流跟踪](../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)。  本主题演示如何在入门教程中创建的项目中启用消息流跟踪。  
  
### 在入门教程中启用消息流跟踪  
  
1.  通过单击**“开始”**、**“运行”**并输入 `eventvwr.exe` 来打开事件查看器。  
  
2.  如果尚未启用分析跟踪，请展开**“应用程序和服务日志”**、**“Microsoft”**、**“Windows”**、**“应用程序服务器”\-\>“应用程序”**。  选择**“视图”**、**“显示分析和调试日志”**。  右击**“分析”**，然后选择**“启用日志”**。  将事件查看器保持打开状态，以便查看跟踪。  
  
3.  在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开在[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)中创建的示例。  请注意，您必须以管理员身份运行 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 才能创建此服务。  如果安装了 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 示例，则可以打开[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含本教程中创建的完整项目。  
  
4.  右击**“服务”**项目，并选择**“添加”**和**“新建项”**。  选择**“应用程序配置文件”**，然后单击**“确定”**。  
  
5.  将下面的代码添加到上一步中创建的 App.Config 文件。  
  
    ```  
    <system.serviceModel>  
      <diagnostics>  
        <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>  
      </diagnostics>  
    </system.serviceModel>  
  
    ```  
  
6.  通过按 Ctrl\+F5 来执行该服务器应用程序而不进行调试。  通过右击**“客户端”**项目并选择**“调试”**、**“启动新实例”**，来执行客户端项目。  
  
7.  若要跟踪从客户端到服务器的事件，请将以下内容添加到“客户端”项目中的应用程序配置文件。  
  
    ```  
    <diagnostics>  
      <endToEndTracing propagateActivity="true" messageFlowTracing="true"/>  
    </diagnostics>  
  
    ```  
  
8.  在客户端的 Program.cs 中，添加以下 Using 语句。  
  
    ```  
    using System.Diagnostics;  
  
    ```  
  
9. 在客户端项目的 program.cs 文件中的 Main 方法中，将跟踪 GUID 设置为在事件日志中传播。  
  
    ```  
    Guid guid = Guid.NewGuid();  
    Trace.CorrelationManager.ActivityId = guid;  
  
    ```  
  
10. 刷新并检查**“分析”**日志。  查找事件 ID 为 220 的事件。  选择此事件，单击预览窗格中的**“详细信息”**选项卡。  此事件将包含调用活动的相关 ID。  
  
    ```  
    <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" />  
    ```  
  
    > [!NOTE]
    >  ActivityID 中具有相同 GUID 的所有事件都与一个请求相关。  这可用于关联从特定客户端到特定服务的消息。  如果客户端调用另一个服务，则 ActivityID 可标识相同的客户端。  
  
11. 在某些情况下，ActivityID 可从原始 GUID 变为新 ActivityID。  在此情况下，会发出一个传输事件。  此事件 ID 为 499，并且此事件的标头中将包含以下数据。  
  
    ```  
    <Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">  
        <System>  
            <Provider Name="Microsoft-Windows-Application Server-Applications" Guid="{c651f5f6-1c0d-492e-8ae1-b4efd7c9d503}" />   
            <EventID>499</EventID>   
            ...  
            <Correlation ActivityID="{A066CCF1-8AB3-459B-B62F-F79F957A5036}" RelatedActivityID="{85FC0930-9C49-42DA-804B-A7368104BD1B}" />   
            ...  
       </System>  
    </Event>  
    ```  
  
    > [!NOTE]
    >  此传输事件记录了活动 ActivityID 从指定为 ActivityID 的 GUID 到指定为 RelatedActivityID 的 GUID 的更改。  在发出此传输事件后，所有事件都将包含指定为 ActivityID 的新 GUID。