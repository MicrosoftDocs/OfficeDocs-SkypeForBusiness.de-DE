---
title: 'Lync Server 2013: Eingehende Anrufe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c007fbaec317a8e9d9d374ea62dafcab6c7a63f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="18058-102">Eingehende Anrufe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18058-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18058-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="18058-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="18058-104">Die Weiterleitung eingehender Anrufe an Benutzer, die für standortbasierte Routings aktiviert sind, hängt von der Position des Endpunkts des Benutzers ab.</span><span class="sxs-lookup"><span data-stu-id="18058-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="18058-105">Die Weiterleitung eingehender Anrufe ist auf die folgende Weise betroffen.</span><span class="sxs-lookup"><span data-stu-id="18058-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="18058-106">Wenn ein Benutzer einen eingehenden Anruf an einem Endpunkt hat, der sich in einer standortbasierten Routing fähigen Netzwerk Website befindet, und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="18058-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="18058-107">Wenn ein Benutzer einen eingehenden Anruf an einem Endpunkt hat, der sich in einer standortbasierten Routing fähigen Netzwerk Website befindet, und sich der Endpunkt an einem anderen Netzwerkstandort als dem PSTN-Gateway befindet, wird der Anruf nicht weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="18058-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="18058-108">Wenn ein Benutzer keine Endpunkte an derselben Netzwerk Website wie das PSTN-Gateway hat, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers weitergeleitet, und eine Benachrichtigung über verpasste Anrufe wird an den angerufenen Teilnehmer gesendet.</span><span class="sxs-lookup"><span data-stu-id="18058-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="18058-109">Die Einstellungen für die Anrufweiterleitung eines Benutzers, der für standortbasiertes Routing aktiviert ist, werden weiterhin erzwungen, die weitergeleiteten Anrufe unterliegen jedoch standortbasierten Routing Einschränkungen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="18058-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="18058-110">Die folgende Tabelle zeigt, wie sich der standortbasierte Routing auf das Routing von eingehenden Anrufen auswirkt, abhängig von der Position des Endpunkts des aufgerufenen.</span><span class="sxs-lookup"><span data-stu-id="18058-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="18058-111">Die Netzwerk Website des PSTN-Gateways ist für standortbasiertes Routing aktiviert, und das ortsbasierte Routing ermöglicht nur das Routing von PSTN-Anrufen an Endpunkte innerhalb desselben Netzwerkstandorts.</span><span class="sxs-lookup"><span data-stu-id="18058-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="18058-112">Angerufener empfängt einen eingehenden Anruf aus dem Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="18058-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="18058-113">Endgerät des Angerufenen befindet sich am selben Netzwerkstandort wie das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="18058-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="18058-114">Endgerät des Angerufenen befindet sich nicht am selben Netzwerkstandort wie das PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="18058-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="18058-115">Endgerät des Angerufenen befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="18058-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18058-116">Routing eines eingehenden Telefonfestnetzanrufs</span><span class="sxs-lookup"><span data-stu-id="18058-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="18058-117">Eingehender Anruf wird an die Endgeräte des Angerufenen weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="18058-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="18058-118">Eingehender Anruf wird nicht an die Endgeräte des Angerufenen weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="18058-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="18058-119">Eingehender Anruf wird nicht an die Endgeräte des Angerufenen weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="18058-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="18058-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18058-120">See Also</span></span>


[<span data-ttu-id="18058-121">Szenarien für das standortbasierte Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18058-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

