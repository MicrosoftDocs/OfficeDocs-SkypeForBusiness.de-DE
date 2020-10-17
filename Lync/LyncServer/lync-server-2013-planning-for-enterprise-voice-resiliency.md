---
title: 'Lync Server 2013: Planen der Ausfallsicherheit für Enterprise-VoIP'
description: 'Lync Server 2013: Planung für die Ausfallsicherheit von Enterprise-VoIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adcf09b87264666924a16543a1b21e8e3cae39f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567261"
---
# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="9495d-103">Planen der Ausfallsicherheit für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9495d-103">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9495d-104">_**Letztes Änderungsstand des Themas:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="9495d-104">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="9495d-105">Die VoIP-Ausfallsicherheit bezieht sich auf die Möglichkeit, dass Benutzer weiterhin Anrufe tätigen und empfangen können, wenn ein zentraler Standort, auf dem lync Server 2013 gehostet wird, nicht mehr verfügbar ist, sei es durch einen WAN-Ausfall (Wide Area Network) oder eine andere Ursache.</span><span class="sxs-lookup"><span data-stu-id="9495d-105">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="9495d-106">Wenn ein zentraler Standort ausfällt, muss Enterprise-VoIP-Dienst unterbrechungsfrei durch nahtloses Failover auf einen Sicherungsstandort fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9495d-106">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="9495d-107">Bei einem WAN-Ausfall müssen Zweigstellen Anrufe an ein lokales PSTN-Gateway umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9495d-107">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="9495d-108">In diesem Abschnitt wird die Planung der VoIP-Ausfallsicherheit im Fall eines Fehlers an einem zentralen Standort oder WAN erläutert.</span><span class="sxs-lookup"><span data-stu-id="9495d-108">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9495d-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9495d-109">In This Section</span></span>

  - [<span data-ttu-id="9495d-110">Planen der VoIP-Ausfallsicherheit für den zentralen Standort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9495d-110">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="9495d-111">Planen von VoIP-Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9495d-111">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

