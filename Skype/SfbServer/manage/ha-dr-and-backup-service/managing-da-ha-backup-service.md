---
title: Verwalten von Disaster Recovery, Hochverfügbarkeits-und Sicherungsdiensten
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informieren Sie sich über Verfahren für Disaster Recovery-Vorgänge sowie zum Verwalten des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303898"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="216f7-103">Verwalten von Skype for Business Server Disaster Recovery, Hochverfügbarkeits-und Backup-Service</span><span class="sxs-lookup"><span data-stu-id="216f7-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="216f7-104">Dieser Abschnitt enthält Verfahren für Wiederherstellungsvorgänge in Notfällen sowie für die Verwaltung des Sicherungsdiensts, der die Daten in gekoppelten Front-End-Pools synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="216f7-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="216f7-105">Disaster Recovery-Verfahren, sowohl Failover als auch Failback, sind manuell.</span><span class="sxs-lookup"><span data-stu-id="216f7-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="216f7-106">Wenn ein Notfall vorliegt, muss der Administrator die Failoververfahren manuell aufrufen.</span><span class="sxs-lookup"><span data-stu-id="216f7-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="216f7-107">Das gleiche gilt für das Failback, nachdem der Pool repariert wurde.</span><span class="sxs-lookup"><span data-stu-id="216f7-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="216f7-108">Bei den Disaster Recovery-Verfahren in diesem Abschnitt wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="216f7-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="216f7-109">Sie verfügen über eine Bereitstellung mit gepaarten Front-End-Pools, die sich an verschiedenen Standorten befinden, wie unter [Planen von Höchstverfügbarkeit und Disaster Recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="216f7-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="216f7-110">Der Sicherungsdienst wurde in diesen gekoppelten Pools ausgeführt, um sie synchron zu halten.</span><span class="sxs-lookup"><span data-stu-id="216f7-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="216f7-111">Wenn der zentrale Verwaltungsspeicher in einem der Pools gehostet wird, wird er in beiden Pools installiert und ausgeführt, wobei einer dieser Pools den aktiven Master und den anderen Pool hostet, in dem sich der Standby-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="216f7-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="216f7-112">In den folgenden Verfahren bezieht sich der *PoolFQDN* -Parameter auf den FQDN des Pools, der von einem Notfall betroffen ist, nicht auf den Pool, von dem betroffene Benutzer umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="216f7-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="216f7-113">Für denselben Satz betroffener Benutzer verweist er sowohl in Failover-als auch in Failback-Cmdlets auf denselben Pool (also auf den Pool, der zuerst die Benutzer vor dem Failover verwaltet hat).</span><span class="sxs-lookup"><span data-stu-id="216f7-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="216f7-114">Angenommen, ein Fall, in dem alle Benutzer, die sich in einem Pool P1 befanden, auf den Sicherungspool P2 umgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="216f7-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="216f7-115">Wenn der Administrator alle Benutzer verschieben möchte, die von P2 aktuell gewartet werden, um von P1 gewartet zu werden, muss der Administrator die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="216f7-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="216f7-116">Führen Sie mithilfe des Failback-Cmdlets alle Benutzer, die sich ursprünglich auf P1 benetzten, von P2 zu P1 zurück.</span><span class="sxs-lookup"><span data-stu-id="216f7-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="216f7-117">In diesem Fall ist der *PoolFQDN* P1's-FQDN.</span><span class="sxs-lookup"><span data-stu-id="216f7-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="216f7-118">Über das Failover-Cmdlet können alle Benutzer, die sich ursprünglich auf P2 mit P1 befanden, einen Failover durchführen.</span><span class="sxs-lookup"><span data-stu-id="216f7-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="216f7-119">In diesem Fall ist der PoolFQDN P2-FQDN.</span><span class="sxs-lookup"><span data-stu-id="216f7-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="216f7-120">Wenn der Administrator später diese P2-Benutzer wieder in P2 zurücksetzen möchte, ist der PoolFQDN P2-FQDN.</span><span class="sxs-lookup"><span data-stu-id="216f7-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="216f7-121">Beachten Sie, dass Schritt 1 oben vor Schritt 2 ausgeführt werden muss, um die Pool Integrität beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="216f7-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="216f7-122">Wenn Sie Schritt 2 vor Schritt 1 versuchen, tritt das Cmdlet "Schritt 2" nicht auf.</span><span class="sxs-lookup"><span data-stu-id="216f7-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="216f7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="216f7-123">See Also</span></span>

[<span data-ttu-id="216f7-124">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="216f7-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
