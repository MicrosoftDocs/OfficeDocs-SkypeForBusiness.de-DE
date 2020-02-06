---
title: Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790123"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="6fdc8-103">Bereitstellen der hohen Verfügbarkeit und Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="6fdc8-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="6fdc8-104">Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="6fdc8-105">Die Höchstverfügbarkeit bezieht sich darauf, sicherzustellen, dass Skype for Business Server-Dienste auch dann verfügbar sind, wenn ein oder mehrere Server ausfällt. Disaster Recovery bezieht sich auf die Beibehaltung der Dienste, die im Fall eines natürlichen oder von Menschen verursachten notfalls durchgeführt werden, und so viele Daten wie möglich vor dem Notfall zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="6fdc8-106">In diesem Abschnitt wird erläutert, wie Sie diese Funktionen bereitstellen. Außerdem erfahren Sie, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="6fdc8-107">Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6fdc8-108">Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="6fdc8-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="6fdc8-109">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6fdc8-109">Related sections</span></span>

[<span data-ttu-id="6fdc8-110">Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6fdc8-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="6fdc8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fdc8-111">See also</span></span>

[<span data-ttu-id="6fdc8-112">Bereitstelleneiner AlwaysOn-verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6fdc8-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="6fdc8-113">Bereitstellen gekoppelter Front-End-Pools für Disaster Recovery in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6fdc8-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="6fdc8-114">Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6fdc8-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
