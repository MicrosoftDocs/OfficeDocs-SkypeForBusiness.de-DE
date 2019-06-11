---
title: 'Lync Server 2013: Durchstellung und Weiterleitung von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="398d1-102">Durchstellung und Weiterleitung von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="398d1-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="398d1-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="398d1-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="398d1-104">Wenn ein PSTN-Endpunkt beteiligt ist, analysiert standortbasiertes Routing die Position des Endpunkts der Calle und den Endpunkt, an den der Anruf übertragen oder weitergeleitet wird (d. h. Übertragung/Forward-Ziel).</span><span class="sxs-lookup"><span data-stu-id="398d1-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="398d1-105">Standortbasiertes Routing bestimmt, ob der Anruf je nach Position beider Endpunkte übertragen oder weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="398d1-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="398d1-106">In der folgenden Tabelle wird das Szenario eines lync-Benutzers in einem Anruf mit einem PSTN-Endpunkt veranschaulicht, und der lync-Benutzer übergibt den Anruf an einen anderen lync-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="398d1-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="398d1-107">Je nach dem Standort des Netzwerkstandorts des Endpunkts des Empfängers wirkt sich der standortbasierte Routing auf das Routing der Anrufweiterleitung oder der Weiterleitung aus.</span><span class="sxs-lookup"><span data-stu-id="398d1-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="398d1-108">Einleitung der Anrufdurchstellung oder -weiterleitung</span><span class="sxs-lookup"><span data-stu-id="398d1-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="398d1-109">Benutzer, der die Durchstellung oder Weiterleitung des Anrufs einleitet</span><span class="sxs-lookup"><span data-stu-id="398d1-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="398d1-110">Der Zielendpunkt befindet sich am gleichen Netzwerkstandort wie der Benutzer, der die Anrufdurchstellung oder -weiterleitung einleitet</span><span class="sxs-lookup"><span data-stu-id="398d1-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="398d1-111">Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als der Benutzer, der die Anrufdurchstellung oder -weiterleitung einleitet</span><span class="sxs-lookup"><span data-stu-id="398d1-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="398d1-112">Der Zielendpunkt ist auf der unbekannten Netzwerk Website oder Netzwerk Website nicht für standortbasiertes Routing aktiviert.</span><span class="sxs-lookup"><span data-stu-id="398d1-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="398d1-113">Lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="398d1-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="398d1-114">Anrufweiterleitung oder -durchstellung ist erlaubt</span><span class="sxs-lookup"><span data-stu-id="398d1-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="398d1-115">Anrufweiterleitung oder -durchstellung ist nicht erlaubt</span><span class="sxs-lookup"><span data-stu-id="398d1-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="398d1-116">Anrufweiterleitung oder -durchstellung ist nicht erlaubt</span><span class="sxs-lookup"><span data-stu-id="398d1-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="398d1-117">Beispiel: ein lync-Benutzer in einem Anruf mit einem PSTN-Endpunkt übergibt den Anruf an einen anderen lync-Benutzer, der sich am gleichen Netzwerkstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="398d1-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="398d1-118">In diesem Fall ist die Durchstellung des Anrufs erlaubt.</span><span class="sxs-lookup"><span data-stu-id="398d1-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="398d1-119">In der folgenden Tabelle wird das Szenario eines lync-Benutzers in einem Anruf mit einem anderen lync-Benutzer veranschaulicht, und einer der Benutzer übergibt den Anruf an einen PSTN-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="398d1-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="398d1-120">Die Tabelle zeigt im Detail, wie sich das standortbasierte Routing abhängig vom Standort des Benutzers, an den der Anruf durchgestellt werden soll, auf den Anruf auswirkt.</span><span class="sxs-lookup"><span data-stu-id="398d1-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="398d1-121">Anrufdurchstellung oder -weiterleitung an einen Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="398d1-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="398d1-122">Zielendpunkt für die Anrufdurchstellung oder -weiterleitung</span><span class="sxs-lookup"><span data-stu-id="398d1-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="398d1-123">Lync-Benutzer auf derselben Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="398d1-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="398d1-124">Lync-Benutzer an verschiedenen Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="398d1-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="398d1-125">Ein oder beide lync-Benutzer in einer unbekannten Netzwerk Website oder Netzwerk Website sind für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="398d1-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="398d1-126">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="398d1-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="398d1-127">Anrufweiterleitung oder -durchstellung wird von der VoIP-Routingrichtlinie am Standort des durchgestellten Benutzers zugelassen</span><span class="sxs-lookup"><span data-stu-id="398d1-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="398d1-128">Anrufweiterleitung oder -durchstellung wird von der VoIP-Routingrichtlinie am Standort des durchgestellten Benutzers zugelassen</span><span class="sxs-lookup"><span data-stu-id="398d1-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="398d1-129">Anrufweiterleitung oder -durchstellung wird von der VoIP-Richtlinie des durchgestellten Benutzers nur durch Trunks zugelassen, die nicht für standortbasiertes Routing aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="398d1-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="398d1-130">Beispiel: ein lync-Benutzer in einem Anruf mit einem anderen lync-Benutzer, der sich am gleichen Netzwerkstandort befindet, übernimmt den Anruf an einen PSTN-Endpunkt, und die Anrufübertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="398d1-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="398d1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="398d1-131">See Also</span></span>


[<span data-ttu-id="398d1-132">Szenarien für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="398d1-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

