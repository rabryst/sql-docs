---
description: "Broker:Connection Event Class"
title: "Broker:Connection Event Class | Microsoft Docs"
ms.custom: ""
ms.date: "05/24/2019"
ms.service: sql
ms.reviewer: ""
ms.subservice: supportability
ms.topic: reference
helpviewer_keywords: 
  - "Broker:Connection event class"
ms.assetid: d3e505f2-0a43-486f-aa92-9c8e49b2dfea
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: ">=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# Broker:Connection Event Class

[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates a **Broker:Connection** event to report the status of a transport connection managed by Service Broker.  
  
## Broker:Connection Event Class Data Columns  
  
|Data column|Type|Description|Column number|Filterable|  
|-----------------|----------|-----------------|-------------------|----------------|  
|**ApplicationName**|**nvarchar**|The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. This column is populated with the values passed by the application rather than the displayed name of the program.|10|Yes|  
|**ClientProcessID**|**int**|The ID assigned by the host computer to the process where the client application is running. This data column is populated if the client process ID is provided by the client.|9|Yes|  
|**DatabaseID**|**int**|The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays the name of the database if the **ServerName** data column is captured in the trace and the server is available. Determine the value for a database by using the **DB_ID** function.|3|Yes|  
|**Error**|**int**|The message ID number in **sys.messages** for the text in the event. If this event reports an error, this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.|31|No|  
|**EventClass**|**int**|The type of event class captured. Always **138** for **Broker:Connection**.|27|No|  
|**EventSequence**|**int**|Sequence number for this event.|51|No|  
|**EventSubClass**|**nvarchar**|The connection state of this connection. For this event, the subclass is one the following values.<br /><br /> <br /><br /> **Connecting**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is initiating a transport connection.<br /><br /> **Connected**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has established a transport connection.<br /><br /> **Connect Failed**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to establish a transport connection.<br /><br /> **Closing**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is closing the transport connection.<br /><br /> **Closed**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has closed the transport connection.<br /><br /> **Accept**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has accepted a transport connection from another instance.<br /><br /> **Send IO Error**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encountered a transport error while sending a message.<br /><br /> **Receive IO Error**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encountered a transport error while receiving a message.|21|Yes|  
|**GUID**|**uniqueidentifier**|The endpoint ID of this connection.|54|No|  
|**HostName**|**nvarchar**|The name of the computer on which the client is running. This data column is populated if the host name is provided by the client. To determine the host name, use the **HOST_NAME** function.|8|Yes|  
|**IntegerData**|**int**|The number of times this connection has been closed.|25|Yes|  
|**IsSystem**|**int**|Indicates whether the event occurred on a system process or a user process.<br /><br /> 0 = user<br /><br /> 1 = system|60|No|  
|**LoginSid**|**image**|The security identification number (SID) of the logged-in user. Each SID is unique for each login in the server.|41|Yes|  
|**NTDomainName**|**nvarchar**|The Windows domain to which the user belongs.|7|Yes|  
|**NTUserName**|**nvarchar**|The name of the user that owns the connection that generated this event.|6|Yes|  
|**ObjectName**|**nvarchar**|The conversation handle of the dialog.|34|No|  
|**ServerName**|**nvarchar**|The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.|26|No|  
|**SPID**|**int**|The server process ID assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the process associated with the client.|12|Yes|  
|**StartTime**|**datetime**|The time at which the event started, when available.|14|Yes|  
|**TextData**|**ntext**|The text of the error message related to the event. For events that do not report an error, this field is empty. The error message may either be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message or a Windows error message.|1|Yes|  
|**TransactionID**|**bigint**|The system-assigned ID of the transaction.|4|No|  
  
## See Also  
 [SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  
