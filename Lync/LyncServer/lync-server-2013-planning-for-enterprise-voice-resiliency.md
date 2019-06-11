---
title: 'Lync Server 2013: Planen der Ausfallsicherheit für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66bba2fe6f53198fcc1e1fc423423e02d46ac8b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="11fe2-102">Planen der Ausfallsicherheit für Enterprise-VoIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11fe2-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11fe2-103">_**Letztes Änderungsdatum des Themas:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="11fe2-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="11fe2-104">Die sprach Stabilität bezieht sich auf die Möglichkeit von Benutzern, weiterhin Anrufe zu tätigen und zu empfangen, wenn ein zentraler Standort, der lync Server 2013 hostet, nicht mehr zur Verfügung steht, ob es sich um einen WAN-Fehler (Wide Area Network) oder eine andere Ursache handelt.</span><span class="sxs-lookup"><span data-stu-id="11fe2-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="11fe2-105">Wenn ein zentraler Standort ausfällt, muss der Enterprise-VoIP-Dienst durch ein nahtloses Failover zu einer Sicherungswebsite unterbrechungsfrei fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="11fe2-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="11fe2-106">Bei einem WAN-Fehler müssen Branch Site-Aufrufe an ein lokales PSTN-Gateway umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="11fe2-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="11fe2-107">In diesem Abschnitt wird die Planung der sprach Sicherheit bei einem zentralen Standort-oder WAN-Fehler erläutert.</span><span class="sxs-lookup"><span data-stu-id="11fe2-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11fe2-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="11fe2-108">In This Section</span></span>

  - [<span data-ttu-id="11fe2-109">Planen von VoIP-Ausfallsicherheit für den zentralen Standort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11fe2-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="11fe2-110">Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11fe2-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

