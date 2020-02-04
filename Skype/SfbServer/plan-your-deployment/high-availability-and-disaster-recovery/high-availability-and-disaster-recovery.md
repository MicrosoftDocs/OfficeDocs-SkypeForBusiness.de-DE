---
title: Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695970"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="95f7f-103">Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="95f7f-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="95f7f-104">Skype for Business Server bietet eine große Verfügbarkeit mit Server-Pooling, Disaster Recovery mit Pool-Kopplung und verschiedenen Modi des Back-End-Servers mit höherer Verfügbarkeit, einschließlich AlwaysOn-Verfügbarkeitsgruppen, Datenbankspiegelung und SQL-Failover-Clustering.</span><span class="sxs-lookup"><span data-stu-id="95f7f-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="95f7f-105">Die Höchstverfügbarkeit bezieht sich darauf, sicherzustellen, dass Skype for Business Server-Dienste auch dann verfügbar sind, wenn ein oder mehrere Server ausfällt.</span><span class="sxs-lookup"><span data-stu-id="95f7f-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="95f7f-106">Mit Notfallwiederherstellung ist gemeint, dass die Dienste auch bei Naturkatastrophen oder von Menschen verursachten Katastrophen verfügbar sind und so viele Daten wie möglich erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="95f7f-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="95f7f-107">Wie in früheren Versionen von lync Server ist die wichtigste Funktion der großen Verfügbarkeit für die meisten Serverfunktionen in Skype for Business Server die Serverredundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="95f7f-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="95f7f-108">Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="95f7f-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="95f7f-109">Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="95f7f-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="95f7f-110">Skype for Business Server bietet auch Disaster Recovery-Optionen für Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="95f7f-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="95f7f-111">Sie können zwei Pools in verschiedenen geografischen Bereichen einrichten, die einander als Sicherung dienen.</span><span class="sxs-lookup"><span data-stu-id="95f7f-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="95f7f-112">Wenn dann ein gesamter Pool oder Standort ausfällt, kann der Sicherungspool den Benutzern an beiden Standorten weiterhin Dienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="95f7f-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="95f7f-113">Skype for Business Server unterstützt außerdem vier Modi für die Höchstverfügbarkeit für Ihre Back-End-Server: SQL-Spiegelung, AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clusterunterstützung.</span><span class="sxs-lookup"><span data-stu-id="95f7f-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="95f7f-114">Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95f7f-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="95f7f-115">Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="95f7f-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="95f7f-116">AlwaysOn-Verfügbarkeitsgruppen werden von beständigen Chat Servern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95f7f-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="95f7f-117">In diesem Abschnitt werden diese Funktionen erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können. 
 </span><span class="sxs-lookup"><span data-stu-id="95f7f-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95f7f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95f7f-118">See also</span></span>

[<span data-ttu-id="95f7f-119">Hohe Verfügbarkeit und Verwaltung von Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="95f7f-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="95f7f-120">Disaster Recovery des Front-End-Pools in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="95f7f-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="95f7f-121">Benutzerfreundlichkeit während eines Pool Fehlers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="95f7f-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="95f7f-122">Verfügbarkeit von Back-End-Servern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="95f7f-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="95f7f-123">Höhere Verfügbarkeit von Dateien in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="95f7f-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
