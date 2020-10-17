---
title: 'Lync Server 2013: eingehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526612"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="323f9-102">Eingehende Anrufe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="323f9-102">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="323f9-103">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="323f9-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="323f9-104">Das Routing eingehender Anrufe an Benutzer, die für Location-Based Routing aktiviert sind, hängt vom Speicherort des Endpunkts des Benutzers ab.</span><span class="sxs-lookup"><span data-stu-id="323f9-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="323f9-105">Das Routing eingehender Anrufe wird wie folgt beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="323f9-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="323f9-106">Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem Netzwerkstandort mit Location-Based Routing aktiviert hat, und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="323f9-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="323f9-107">Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem Netzwerkstandort mit Location-Based Routing aktiviert hat, und sich der Endpunkt an einem anderen Netzwerkstandort als das PSTN-Gateway befindet, wird der Anruf nicht weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="323f9-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="323f9-108">Wenn ein Benutzer keine Endpunkte am selben Netzwerkstandort wie das PSTN-Gateway hat, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers weitergeleitet, und eine Benachrichtigung über verpasste Anrufe wird an den angerufenen Teilnehmer gesendet.</span><span class="sxs-lookup"><span data-stu-id="323f9-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="323f9-109">Die Anrufweiterleitungseinstellungen eines Benutzers, der für Location-Based Routing aktiviert ist, werden weiterhin erzwungen, jedoch werden weitergeleitete Anrufe Location-Based Routing Einschränkungen des Benutzers unterworfen.</span><span class="sxs-lookup"><span data-stu-id="323f9-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="323f9-110">In der folgenden Tabelle wird veranschaulicht, wie sich Location-Based Routing auf das Routing von eingehenden Anrufen in Abhängigkeit von der Position des Endpunkts des angerufenen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="323f9-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="323f9-111">Der Netzwerkstandort des PSTN-Gateways ist für Location-Based Routing aktiviert, und Location-Based Routing ermöglicht nur das Routing von PSTN-Anrufen an Endpunkte innerhalb desselben Netzwerkstandorts.</span><span class="sxs-lookup"><span data-stu-id="323f9-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="323f9-112">Angerufener empfängt einen eingehenden Anruf aus dem PSTN</span><span class="sxs-lookup"><span data-stu-id="323f9-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="323f9-113">Endpunkt des angerufenen befindet sich am selben Netzwerkstandort wie das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="323f9-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="323f9-114">Der Endpunkt des angerufenen befindet sich nicht am gleichen Netzwerkstandort wie das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="323f9-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="323f9-115">Endpunkt des angerufenen befindet sich an einem unbekannten Netzwerkstandort oder ist für Location-Based Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="323f9-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="323f9-116">Routing eines eingehenden PSTN-Anrufs</span><span class="sxs-lookup"><span data-stu-id="323f9-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="323f9-117">Eingehende Anrufe werden an die Endpunkte des angerufenen weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="323f9-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="323f9-118">Eingehende Anrufe werden nicht an die Endpunkte des angerufenen weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="323f9-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="323f9-119">Eingehende Anrufe werden nicht an die Endpunkte des angerufenen weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="323f9-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="323f9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="323f9-120">See Also</span></span>


[<span data-ttu-id="323f9-121">Szenarien für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="323f9-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

