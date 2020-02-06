---
title: Höhere Verfügbarkeit von Dateien in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informieren Sie sich über die Gewährleistung einer höheren Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server mithilfe von DFS.
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815933"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="4047f-103">Höhere Verfügbarkeit von Dateien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4047f-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="4047f-104">Informieren Sie sich über die Gewährleistung einer höheren Verfügbarkeit Ihrer Dateifreigaben in Skype for Business Server mithilfe von DFS.</span><span class="sxs-lookup"><span data-stu-id="4047f-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="4047f-105">Wenn Sie eine höhere Verfügbarkeit für die Dateifreigabe in Ihrer Skype for Business Server-Bereitstellung gewährleisten möchten, können Sie das verteilte Datei System (Distributed File System, DFS) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4047f-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="4047f-106">DFS unterstützt Failover von einem Dateiserver auf einen anderen innerhalb desselben Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="4047f-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="4047f-107">Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="4047f-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="4047f-108">Weitere Informationen zu DFS in Windows Server 2012 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="4047f-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="4047f-109">Informationen zu DFS unter Windows Server 2008 finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="4047f-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="4047f-110">Je nach Größe Ihres Netzwerks und dem gewünschten Maß an Flexibilität können Sie mit einem Serverpaar alle Dateifreigaben auf einer Website hosten oder ein paar pro Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="4047f-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="4047f-111">Bei DFS handelt es sich um einen Best Effort-Datei Replikationsmechanismus, bei dem keine RTO-oder Recovery Point Objective (RPO)-Zusicherungen veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="4047f-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="4047f-112">Ein Failover zwischen DFS-Servern sollte schnell abgeschlossen werden, die Daten Replikationsverzögerung kann jedoch verhindern, dass Benutzer in der Lage sind, die laufende Arbeit fortzusetzen, wenn das Failover eintritt.</span><span class="sxs-lookup"><span data-stu-id="4047f-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="4047f-p103">Wenn Sie DFS verwenden und der Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfter speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt des ausgefallenen Servers auf dem anderen Server wiederherzustellen, der mit dem jetzt nicht mehr verfügbaren Server kombiniert ist.</span><span class="sxs-lookup"><span data-stu-id="4047f-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

