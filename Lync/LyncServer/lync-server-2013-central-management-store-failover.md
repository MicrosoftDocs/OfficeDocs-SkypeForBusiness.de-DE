---
title: Lync Server 2013 Failover des zentralen Verwaltungsspeichers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508042"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="10e78-102">Failover des zentralen Verwaltungsspeichers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10e78-102">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10e78-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="10e78-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="10e78-104">Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu Servern und Diensten in ihrer lync 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="10e78-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="10e78-105">Es bietet eine robuste, schematisierten Speicherung der Daten, die für die Definition, Einrichtung, Verwaltung, Verwaltung, Beschreibung und den Betrieb einer lync 2013-Bereitstellung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="10e78-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="10e78-106">Darüber hinaus werden die Daten überprüft, um eine konsistente Konfiguration zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="10e78-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="10e78-107">Jede lync-Bereitstellung umfasst einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="10e78-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="10e78-108">Wenn Sie eine Pool Kopplung einrichten, die den Pool enthält, der den zentralen Verwaltungsspeicher hostet, wird eine Sicherungsdatenbank für den zentralen Verwaltungsspeicher im Sicherungspool eingerichtet, und die Dienste für den zentralen Verwaltungsspeicher werden in beiden Pools installiert.</span><span class="sxs-lookup"><span data-stu-id="10e78-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="10e78-109">Eine der beiden Datenbanken des zentralen Verwaltungsspeichers ist zu jedem Zeitpunkt der aktive Master und der andere ein Standby.</span><span class="sxs-lookup"><span data-stu-id="10e78-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="10e78-110">Der Inhalt wird vom Sicherungsdienst vom aktiven Master in den Standbymodus repliziert.</span><span class="sxs-lookup"><span data-stu-id="10e78-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="10e78-111">Während eines Pool Failovers, in dem sich die Pools befinden, die den zentralen Verwaltungsspeicher hosten, muss der Administrator vor dem Failover des Front-End-Pool einen Failover des zentralen Verwaltungsspeichers ausführen.</span><span class="sxs-lookup"><span data-stu-id="10e78-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="10e78-112">Nachdem der Notfall repariert wurde, ist es nicht erforderlich, den zentralen Verwaltungsspeicher zurück zu schlagen.</span><span class="sxs-lookup"><span data-stu-id="10e78-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="10e78-113">Nach der Reparatur kann der zentrale Verwaltungsspeicher im ursprünglichen Sicherungspool als aktiver Master-Manager beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="10e78-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="10e78-114">Die Entwicklungsziele für das Failover des zentralen Verwaltungsspeichers sind 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) und 5 Minuten für RPO (Recovery Points Objective).</span><span class="sxs-lookup"><span data-stu-id="10e78-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

