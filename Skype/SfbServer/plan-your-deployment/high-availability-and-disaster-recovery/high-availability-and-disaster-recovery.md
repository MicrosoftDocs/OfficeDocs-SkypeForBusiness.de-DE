---
title: Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server.
ms.openlocfilehash: 94db95c097fca62e31a01efd1d254ab6d3cd6d37
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996459"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="24328-103">Planen Sie für hohe Verfügbarkeit und Disaster Recovery in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="24328-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="24328-104">Skype für Business Server bietet eine hohe Verfügbarkeit mit pooling Disaster Recovery mit poolpaaren und mehreren Modi für die Back-End-Server hohe Verfügbarkeit, einschließlich AlwaysOn Availability Groups, datenbankspiegelung und Failover-Clusterunterstützung mit SQL Server.</span><span class="sxs-lookup"><span data-stu-id="24328-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="24328-105">Hoher Verfügbarkeit bezieht sich auf und stellen Sie sicher, dass Skype für Business Server-Dienste verfügbar sind, auch wenn Sie einen oder mehrere Server ausfällt.</span><span class="sxs-lookup"><span data-stu-id="24328-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="24328-106">Für die Notfallwiederherstellung müssen die Dienste auch bei Naturkatastrophen oder von Menschen verursachten Katastrophen aktiv gehalten und so viele Daten wie möglich bewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="24328-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="24328-107">Wie in früheren Versionen von Lync Server ist das Hauptfenster hohe Verfügbarkeit-Feature für die meisten Serverrollen in Skype für Business Server Serverredundanz über pooling.</span><span class="sxs-lookup"><span data-stu-id="24328-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="24328-108">Wenn ein Server in einer bestimmten Serverrolle ausfällt, wird die Last dieses Servers von den anderen Servern im Pool mit der gleichen Rolle übernommen.</span><span class="sxs-lookup"><span data-stu-id="24328-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="24328-109">Dies gilt für Front End- und Edge-Server ebenso wie für Vermittlungsserver und Directors.</span><span class="sxs-lookup"><span data-stu-id="24328-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="24328-110">Skype für Business Server bietet auch Disaster Recovery-Optionen für Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="24328-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="24328-111">Sie können zwei Pools in verschiedenen geografischen Bereichen einrichten, die einander als Sicherung dienen.</span><span class="sxs-lookup"><span data-stu-id="24328-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="24328-112">Wenn dann ein gesamter Pool oder Standort ausfällt, kann der Sicherungspool den Benutzern an beiden Standorten weiterhin Dienste bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="24328-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="24328-113">Unterstützt Skype für Business Server auch Kommunikationsmodi hohe Verfügbarkeit für die Back-End-Server: SQL-Spiegelung, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL-Failover-Clusterunterstützung.</span><span class="sxs-lookup"><span data-stu-id="24328-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24328-114">SQL-Spiegelung wird steht in Skype für Business Server 2015 jedoch nicht mehr in unterstützt Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="24328-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="24328-115">Die AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL clustering Failovermethoden werden bevorzugt mit Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="24328-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="24328-116">AlwaysOn Availability Groups werden für Persistent Chatserver nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24328-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="24328-117">In diesem Abschnitt werden diese Funktionen erläutert. Zudem wird erklärt, welche Schritte Sie für die hohe Verfügbarkeit und Notfallwiederherstellung für einige Ihrer anderen Serverrollen ausführen können. 
 </span><span class="sxs-lookup"><span data-stu-id="24328-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="24328-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24328-118">See also</span></span>

[<span data-ttu-id="24328-119">Hohe Verfügbarkeit und Verwaltung von Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="24328-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="24328-120">Front-End-Pool Disaster Recovery in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="24328-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="24328-121">Benutzerfreundlichkeit während des Ausfalls eines Pools in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="24328-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="24328-122">Back-End-Server hohe Verfügbarkeit in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="24328-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="24328-123">Hohen Verfügbarkeit in Skype-Dateifreigabe für Business Server</span><span class="sxs-lookup"><span data-stu-id="24328-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)