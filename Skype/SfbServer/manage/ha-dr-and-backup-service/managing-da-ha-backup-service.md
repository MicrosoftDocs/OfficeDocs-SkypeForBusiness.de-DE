---
title: Verwalten von Disaster Recovery, hohe Verfügbarkeit und Sicherungsdienst
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informationen Sie zu Verfahren für Disaster Recovery-Vorgänge und für die Verwaltung des Sicherungsdienstes, der die Daten in einem Front-End-Pools synchronisiert.
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199826"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="015a6-103">Verwalten von Skype für Business Server-Wiederherstellung, hohe Verfügbarkeit und Sicherungsdienst</span><span class="sxs-lookup"><span data-stu-id="015a6-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="015a6-104">Dieser Abschnitt enthält Verfahren für Disaster Recovery-Vorgänge und für die Verwaltung des Sicherungsdienstes, der die Daten in einem Front-End-Pools synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="015a6-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="015a6-105">Verfahren für die notfallwiederherstellung, Failover und Failback und sind manuelle.</span><span class="sxs-lookup"><span data-stu-id="015a6-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="015a6-106">Wenn ein Notfall vorhanden ist, muss der Administrator die FailoverVerfahren manuell aufrufen.</span><span class="sxs-lookup"><span data-stu-id="015a6-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="015a6-107">Das gilt auch für Failback nach der Pool repariert wird.</span><span class="sxs-lookup"><span data-stu-id="015a6-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="015a6-108">Die Notfallwiederherstellungsverfahren in diesem Abschnitt wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="015a6-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="015a6-109">Sie haben eine Bereitstellung mit gekoppelten Front-End-Pools an verschiedenen Standorten befinden, wie unter [Planen für hohe Verfügbarkeit und notfallwiederherstellung](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="015a6-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="015a6-110">Den Sicherungsdienst wurde auf diese synchronisiert bleiben diese gekoppelten Pools ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="015a6-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="015a6-111">Wenn Sie der zentralen Verwaltungsspeicher auf entweder Pool gehostet wird, ist es auf beide der gekoppelten Pools, mit einem dieser hosting aktive Masterseite Pools und das Standby-hosting Pool installiert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="015a6-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="015a6-112">In den folgenden Verfahren der Parameter *"poolfqdn"* verweist auf den FQDN des Pools, die vom Disaster betroffen ist, werden nicht auf der Pool, die Benutzer betroffen aus umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="015a6-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="015a6-113">Für den gleichen Satz von betroffenen Benutzer verweist es auf den gleichen Pool in Failover und Failback-Cmdlets (d. h., den Pool, die der Benutzer vor dem Failover zuerst verwaltet).</span><span class="sxs-lookup"><span data-stu-id="015a6-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="015a6-114">Nehmen wir beispielsweise an einen Fall, in dem alle Benutzer in einem Pool P1 wurden mit dem Sicherungspool P2 Failover verwaltet.</span><span class="sxs-lookup"><span data-stu-id="015a6-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="015a6-115">Wenn der Administrator möchte so verschieben Sie alle Benutzer, die aktuell verarbeitet vom P2 bis von P1 bedient werden, muss der Administrator die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="015a6-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="015a6-116">Zurücksetzen der Benutzer verwaltet ursprünglich auf P1 aus P2 zu P1 Fail mit dem Failback-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="015a6-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="015a6-117">In diesem Fall ist der *PoolFQDN* des P1 FQDN.</span><span class="sxs-lookup"><span data-stu-id="015a6-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="015a6-118">Ausführen eines Failovers alle Benutzer ursprünglich auf P2 bis P1 verwaltet mithilfe des Failover-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="015a6-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="015a6-119">In diesem Fall ist der PoolFQDN P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="015a6-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="015a6-120">Wenn der Administrator später Failback dieser P2-Benutzer zurück zu P2 möchte, ist der PoolFQDN P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="015a6-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="015a6-121">Beachten Sie diesen Schritt 1 weiter oben ausgeführt werden muss, bevor Sie Schritt 2, um die Integrität der Pool zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="015a6-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="015a6-122">Schritt 2-Cmdlet schlägt fehl, wenn Sie versuchen, Schritt 2, bevor Sie Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="015a6-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="015a6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="015a6-123">See Also</span></span>

[<span data-ttu-id="015a6-124">Planen der hohen Verfügbarkeit und der Notfallwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="015a6-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
