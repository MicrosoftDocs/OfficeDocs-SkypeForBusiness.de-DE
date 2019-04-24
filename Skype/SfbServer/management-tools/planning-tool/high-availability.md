---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Das Hauptfenster Hochverfügbarkeits-Schema für die meisten Serverrollen in Skype für Business Server 2015 basiert auf Serverredundanz über pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 50cc5f371e4964555aae2a7f50ce3d1431f4f10c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217257"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="1044c-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="1044c-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="1044c-105">Das Hauptfenster Hochverfügbarkeits-Schema für die meisten Serverrollen in Skype für Business Server 2015 basiert auf Serverredundanz über pooling.</span><span class="sxs-lookup"><span data-stu-id="1044c-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="1044c-106">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="1044c-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="1044c-107">Skype für Business Server 2015 erfordert mindestens zwei Front-End-Servern, um hohe Verfügbarkeit zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1044c-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="1044c-108">Das Planungstool verwendet die folgenden Kriterien, um festzustellen, ob sie zusätzliche Server hinzufügen, um hohe Verfügbarkeit zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="1044c-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="1044c-109">Wenn die Bereitstellung mindestens zwei Front-End-Server enthält, werden das Planungstool keinen zusätzlichen Server hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1044c-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="1044c-110">Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1044c-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="1044c-111">Wenn die Bereitstellung beständigen Chat enthält, das Planungstool für das Hinzufügen eines zusätzlichen Servers, aber nicht erhöhen der Anzahl Pool.</span><span class="sxs-lookup"><span data-stu-id="1044c-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="1044c-112">Angenommen, wenn die Bereitstellung bereits vier Servern enthält, das Planungstool schlägt (für insgesamt fünf Servern) einen weiteren Server hinzufügen jedoch behält einen einzelnen Pool.</span><span class="sxs-lookup"><span data-stu-id="1044c-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="1044c-113">Das Planungstool fügt auch eine Spiegeldatenbank SQL für alle Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="1044c-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="1044c-114">Beispielsweise wenn eine Front-End-SQL Server-Datenbank vorhanden ist, wird das Planungstool die anderen Datenbank als der Spiegeldatenbank für diese Vorlage hinzufügen und nennen Sie es als"Front-End Spiegel SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1044c-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="1044c-115">Weitere Informationen zur Vorbereitung Ihrer Umgebung für hohe Verfügbarkeit finden Sie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="1044c-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

