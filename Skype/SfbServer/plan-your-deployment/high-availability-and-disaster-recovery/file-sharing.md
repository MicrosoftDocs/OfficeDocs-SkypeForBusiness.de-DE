---
title: Hohen Verfügbarkeit in Skype-Dateifreigabe für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informationen Sie zu sicherstellen hoher Verfügbarkeit für Ihre Dateifreigaben in Skype für Business Server unter Verwendung von DFS.
ms.openlocfilehash: 645aa70ffc0c42cddb6941c9766cb91bed898dc8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989909"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="c1957-103">Hohen Verfügbarkeit in Skype-Dateifreigabe für Business Server</span><span class="sxs-lookup"><span data-stu-id="c1957-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="c1957-104">Informationen Sie zu sicherstellen hoher Verfügbarkeit für Ihre Dateifreigaben in Skype für Business Server unter Verwendung von DFS.</span><span class="sxs-lookup"><span data-stu-id="c1957-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="c1957-105">Um hohe Verfügbarkeit für Dateifreigabe in Ihrer Skype für Business Server-Bereitstellung zu gewährleisten, können Sie das verteilten Dateisystem (DFS).</span><span class="sxs-lookup"><span data-stu-id="c1957-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="c1957-106">DFS unterstützt Failover von einem Dateiserver auf einen anderen innerhalb desselben Rechenzentrums.</span><span class="sxs-lookup"><span data-stu-id="c1957-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="c1957-107">Bei einer umfassenden Bereitstellung empfehlen wir Ihnen die Verwendung von dedizierten Dateiservern, die mithilfe von DFS kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="c1957-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="c1957-108">Weitere Informationen zu DFS in Windows Server 2012 finden Sie unter [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="c1957-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="c1957-109">Informationen zu DFS unter Windows Server 2008 finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="c1957-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="c1957-110">Je nach Größe Ihres Netzwerks, und die Größe des gewünschten Resiliency, können Sie ein Paar von Servern zum Hosten von alle Dateifreigaben in einer Website verwenden oder ein Paar pro Front-End-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1957-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="c1957-111">DFS ist ein best Effort Datei Replikationsmechanismus, ohne veröffentlichte Recovery Time Objective (RTO) und Recovery Point Objective (RPO) Engagement.</span><span class="sxs-lookup"><span data-stu-id="c1957-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="c1957-112">Ein Failover zwischen DFS-Servern sollten schnell ausgeführt werden, aber Daten Replikation Verzögerung möglicherweise verhindern, dass Benutzer wird Arbeit fortsetzen, wenn das Failover erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c1957-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="c1957-p103">Wenn Sie DFS verwenden und der Datenspeicher bei der Dateifreigabe wichtig ist, sollten Sie die Dateifreigaben öfter speichern, zum Beispiel alle vier bis acht Stunden. Wenn eine Dateifreigabe ausfällt und die Replikation nicht auf dem neuesten Stand ist, können Sie die Sicherung verwenden, um den Inhalt des ausgefallenen Servers auf dem anderen Server wiederherzustellen, der mit dem jetzt nicht mehr verfügbaren Server kombiniert ist.</span><span class="sxs-lookup"><span data-stu-id="c1957-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

