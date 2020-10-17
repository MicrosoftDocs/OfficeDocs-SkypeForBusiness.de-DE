---
title: 'Lync Server 2013: Anruf Übertragungen und Anrufweiterleitung'
description: 'Lync Server 2013: Anruf Übertragungen und Anrufweiterleitung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565251"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="ae602-103">Anruf Übertragungen und Anrufweiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae602-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae602-104">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ae602-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ae602-105">Wenn ein PSTN-Endpunkt beteiligt ist, analysiert Location-Based Routing die Position des Endpunkts der Calle und den Endpunkt, an den der Anruf übertragen oder an ihn weitergeleitet wird (d. h. Transfer/Forward-Ziel).</span><span class="sxs-lookup"><span data-stu-id="ae602-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="ae602-106">Location-Based Routing bestimmt, ob der Anruf je nach Standort beider Endpunkte übertragen oder weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae602-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="ae602-107">In der folgenden Tabelle wird das Szenario eines lync-Benutzers in einem Anruf mit einem PSTN-Endpunkt veranschaulicht, und der lync-Benutzer übergibt den Anruf an einen anderen lync-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ae602-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="ae602-108">Je nach Standort des Netzwerkstandorts des Endpunkts des Empfängers wirkt sich Location-Based Routing auf das Routing der Anrufweiterleitung oder der Weiterleitung aus.</span><span class="sxs-lookup"><span data-stu-id="ae602-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="ae602-109">Initiieren der Anrufweiterleitung oder Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="ae602-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae602-110">Benutzer, der die Anrufweiterleitung/-Weiterleitung initiiert</span><span class="sxs-lookup"><span data-stu-id="ae602-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="ae602-111">Der Zielendpunkt befindet sich am gleichen Netzwerkstandort wie der Benutzer, der die Anrufweiterleitung oder Weiterleitung initiiert.</span><span class="sxs-lookup"><span data-stu-id="ae602-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="ae602-112">Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als der Benutzer, der die Anrufweiterleitung initiiert oder weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="ae602-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="ae602-113">Der Zielendpunkt befindet sich im unbekannten Netzwerkstandort oder Netzwerkstandort ist für Location-Based Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="ae602-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae602-114">Lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="ae602-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="ae602-115">Anrufweiterleitung oder-Übertragung ist zulässig</span><span class="sxs-lookup"><span data-stu-id="ae602-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="ae602-116">Anrufweiterleitung oder-Übertragung ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="ae602-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="ae602-117">Anrufweiterleitung oder-Übertragung ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="ae602-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="ae602-118">Beispiel: ein lync-Benutzer in einem Anruf mit einem PSTN-Endpunkt überträgt den Anruf an einen anderen lync-Benutzer, der sich am gleichen Netzwerkstandort befindet.</span><span class="sxs-lookup"><span data-stu-id="ae602-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="ae602-119">In diesem Fall ist die Anrufweiterleitung zulässig.</span><span class="sxs-lookup"><span data-stu-id="ae602-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="ae602-120">In der folgenden Tabelle wird das Szenario eines lync-Benutzers in einem Anruf mit einem anderen lync-Benutzer dargestellt, und einer der Benutzer übergibt den Anruf an einen PSTN-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="ae602-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="ae602-121">Je nach Standort des Benutzers, an den der Anruf weitergeleitet wird, wird in der Tabelle ausführlich beschrieben, wie sich Location-Based Routing auf den Anruf auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ae602-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="ae602-122">Anrufweiterleitung oder Weiterleitung an PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae602-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae602-123">Anrufweiterleitung/Endpunkt Ziel weiterleiten</span><span class="sxs-lookup"><span data-stu-id="ae602-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="ae602-124">Lync-Benutzer am gleichen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="ae602-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="ae602-125">Lync-Benutzer an unterschiedlichen Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="ae602-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="ae602-126">Ein oder beide lync-Benutzer an einem unbekannten Netzwerkstandort oder Netzwerkstandort sind für Location-Based Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="ae602-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae602-127">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae602-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ae602-128">Anrufweiterleitung oder-Übertragung zulässig durch die Website VoIP-Routing Richtlinie des übertragenen Benutzers</span><span class="sxs-lookup"><span data-stu-id="ae602-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ae602-129">Anrufweiterleitung oder-Übertragung zulässig durch die Website VoIP-Routing Richtlinie des übertragenen Benutzers</span><span class="sxs-lookup"><span data-stu-id="ae602-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ae602-130">Anrufweiterleitung oder Übertragung, die von der VoIP-Richtlinie des übertragenen Benutzers zugelassen wird, nur über Trunks, die für Location-Based Routing nicht aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="ae602-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="ae602-131">Beispiel: ein lync-Benutzer in einem Anruf mit einem anderen lync-Benutzer, der sich am gleichen Netzwerkstandort befindet, überträgt den Anruf an einen PSTN-Endpunkt, und die Anrufweiterleitung wird zugelassen.</span><span class="sxs-lookup"><span data-stu-id="ae602-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ae602-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae602-132">See Also</span></span>


[<span data-ttu-id="ae602-133">Szenarien für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae602-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

