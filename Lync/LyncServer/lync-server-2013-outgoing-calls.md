---
title: 'Lync Server 2013: ausgehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa72bb1da56862765279f25f73070863d218067
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="564cb-102">Ausgehende Anrufe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="564cb-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="564cb-103">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="564cb-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="564cb-104">Das Routing von ausgehenden Anrufen von Benutzern, die für standortbasiertes Routing aktiviert sind, wird von der Netzwerkadresse des Endpunkts des Benutzers beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="564cb-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="564cb-105">In der folgenden Tabelle wird veranschaulicht, wie sich das standortbasierte Routing auf das Routing ausgehender Anrufe in Abhängigkeit von der Position des Endpunkts des Anrufers auswirkt.</span><span class="sxs-lookup"><span data-stu-id="564cb-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="564cb-106">Anrufer, der einen ausgehenden Anruf an das PSTN abgibt</span><span class="sxs-lookup"><span data-stu-id="564cb-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="564cb-107">Benutzer Endpunkt befindet sich an einem Netzwerkstandort, der für standortbasiertes Routing aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="564cb-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="564cb-108">Benutzer Endpunkt befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="564cb-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="564cb-109">Autorisierung für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="564cb-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="564cb-110">Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</span><span class="sxs-lookup"><span data-stu-id="564cb-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="564cb-111">Anruf wird basierend auf der VoIP-Richtlinie des Benutzers autorisiert</span><span class="sxs-lookup"><span data-stu-id="564cb-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="564cb-112">Weiterleitung des ausgehenden Anrufs</span><span class="sxs-lookup"><span data-stu-id="564cb-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="564cb-113">Der Anruf wird entsprechend der VoIP-Routing Richtlinie des Netzwerkstandorts weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="564cb-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="564cb-114">Der Anruf wird entsprechend der VoIP-Richtlinie des Benutzers und nur über Trunks weitergeleitet, die nicht für standortbasiertes Routing aktiviert sind (sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="564cb-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="564cb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="564cb-115">See Also</span></span>


[<span data-ttu-id="564cb-116">Szenarien für das standortbasierte Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="564cb-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

