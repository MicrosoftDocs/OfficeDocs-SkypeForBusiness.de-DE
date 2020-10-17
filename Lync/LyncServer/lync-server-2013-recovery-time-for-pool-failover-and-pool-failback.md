---
title: Lync Server 2013 Wiederherstellungszeit für Pool-Failover und Pool-Failback
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
ms.openlocfilehash: c1221d145951b4f780638cc2681f6d6cff822a4e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512022"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="37978-102">Wiederherstellungszeit für Pool-Failover und Pool-Failback in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37978-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37978-103">_**Letztes Änderungsstand des Themas:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="37978-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="37978-p101">Für Pool-Failover und Pool-Failback liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 30 Minuten. Dies ist die Zeit, die erforderlich ist, bis das Failover stattfindet, nachdem Administratoren festgestellt haben, dass ein Notfall vorliegt, und die Failover-Prozeduren initiiert haben. Hierin ist die Zeit, die Administratoren für die Bewertung der Situation und die Entscheidungsfindung benötigen, nicht enthalten. Auch nicht enthalten ist die Zeit, die Benutzer nach Abschluss des Failovers für die Anmeldung benötigen.</span><span class="sxs-lookup"><span data-stu-id="37978-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="37978-107">Für Pool-Failover und Pool-Failback liegt das Entwicklungsziel für das Recovery Time Objective (RTO) bei 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="37978-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="37978-108">Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Backupdienstes verloren gehen können.</span><span class="sxs-lookup"><span data-stu-id="37978-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="37978-109">Wenn ein Pool beispielsweise um 10:00 Uhr ausfällt und der RPO-Wert 30 Minuten beträgt, werden die Daten zwischen 9:30 Uhr in den Pool geschrieben.</span><span class="sxs-lookup"><span data-stu-id="37978-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="37978-110">und 10:00 A. M. wurde möglicherweise nicht in den Sicherungspool repliziert und würde verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="37978-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="37978-111">Bei allen RTO-und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren in der gleichen Weltregion mit einem Transport mit hoher Geschwindigkeit und niedriger Latenz zwischen den beiden Standorten befinden.</span><span class="sxs-lookup"><span data-stu-id="37978-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="37978-112">Diese Nummern werden für einen Pool mit 40.000 gleichzeitig aktiven Benutzern und 200.000 für lync aktivierten Benutzern im Hinblick auf ein vordefiniertes Benutzermodell gemessen, bei dem kein Rückstand in der Datenreplikation vorliegt.</span><span class="sxs-lookup"><span data-stu-id="37978-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="37978-113">Sie können auf der Grundlage von Leistungstests und Überprüfung Änderungen unterliegen.</span><span class="sxs-lookup"><span data-stu-id="37978-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

