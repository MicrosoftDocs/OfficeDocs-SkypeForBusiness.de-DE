---
title: 'Lync Server 2013: Wiederherstellungsdauer bei einem Failover und Failback eines Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="f2006-102">Wiederherstellungsdauer bei einem Failover und Failback eines Pools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2006-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2006-103">_**Letztes Änderungsdatum des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="f2006-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="f2006-104">Für Pool-Failover und Pool-Failback beträgt das Entwicklungsziel für das Wiederherstellungszeitziel (RTO) 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="f2006-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="f2006-105">Dies ist der Zeitpunkt, zu dem ein Failover erfolgen muss, nachdem Administratoren festgestellt haben, dass ein Notfall aufgetreten ist, und die Failoververfahren initiiert haben.</span><span class="sxs-lookup"><span data-stu-id="f2006-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="f2006-106">Es umfasst nicht die Zeit, die Administratoren zur Beurteilung der Situation und zur Entscheidungsfindung haben, und auch nicht die Zeit, die Benutzer sich nach Abschluss des Failovers erneut anmelden müssen.</span><span class="sxs-lookup"><span data-stu-id="f2006-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="f2006-107">Für Pool-Failover und Pool-Failback beträgt das Engineering-Ziel für das Recovery Point-Ziel (RPO) 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="f2006-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="f2006-108">Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Sicherungsdienstes verloren gehen können.</span><span class="sxs-lookup"><span data-stu-id="f2006-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="f2006-109">Wenn beispielsweise ein Pool um 10:00 Uhr herunterfällt und die RPO 30 Minuten beträgt, werden die Daten in den Pool zwischen 9:30 Uhr geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2006-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="f2006-110">und 10:00 A. M. möglicherweise nicht in den Backup-Pool repliziert und gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="f2006-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="f2006-111">Bei allen RTO-und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren innerhalb desselben Welt Bereichs mit hoch Geschwindigkeits Transporten mit niedriger Latenz zwischen den beiden Standorten befinden.</span><span class="sxs-lookup"><span data-stu-id="f2006-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="f2006-112">Diese Nummern werden für einen Pool mit 40.000-aktiven Benutzern und 200.000-Benutzern für lync in Bezug auf ein vordefiniertes Benutzermodell gemessen, bei dem es bei der Datenreplikation keinen Rückstand gibt.</span><span class="sxs-lookup"><span data-stu-id="f2006-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="f2006-113">Sie unterliegen Änderungen auf der Grundlage von Leistungstests und-Validierungen.</span><span class="sxs-lookup"><span data-stu-id="f2006-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

