---
title: Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server.
ms.openlocfilehash: c3741527b83634d8a3571daa2623af55806e7f19
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993599"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="3f926-103">Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="3f926-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="3f926-104">Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3f926-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="3f926-105">Hoher Verfügbarkeit bezieht sich auf und stellen Sie sicher, dass Skype für Business Server-Dienste verfügbar sind, auch wenn Sie einen oder mehrere Server ausfällt. Disaster Recovery bezieht sich auf Aufbewahrung Dienste sein und sollte bei einem Notfall natürlichen oder Human verursacht und wie viele Daten aus vor dem Datenverlust möglichst beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3f926-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="3f926-106">In diesem Abschnitt wird erläutert, wie Sie diese Funktionen bereitstellen. Außerdem erfahren Sie, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3f926-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="3f926-107">SQL-Spiegelung wird steht in Skype für Business Server 2015 jedoch nicht mehr in unterstützt Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f926-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3f926-108">Die AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL clustering Failovermethoden werden bevorzugt mit Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f926-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="3f926-109">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3f926-109">Related sections</span></span>

[<span data-ttu-id="3f926-110">Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="3f926-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="3f926-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f926-111">See also</span></span>

[<span data-ttu-id="3f926-112">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="3f926-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="3f926-113">Bereitstellen Sie kombinierte Front-End-Pools für Disaster Recovery in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="3f926-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="3f926-114">Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3f926-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
