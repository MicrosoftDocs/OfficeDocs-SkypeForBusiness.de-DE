---
title: 'Lync Server 2013: Orts basiertes Routing und beratende Anruf Übertragungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="a54e4-102">Übertragungen von standortbasierten Routing-und beratenden anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a54e4-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a54e4-103">_**Letztes Änderungsdatum des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="a54e4-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="a54e4-104">Neben der Durchsetzung von Standort basiertem Routing zu lync-Besprechungen erzwingt die standortbasierte Routing Konferenz Anwendung standortbasierte Routing Einschränkungen für beratende Anruf Übertragungen, die an PSTN-Endpunkte abtreten.</span><span class="sxs-lookup"><span data-stu-id="a54e4-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="a54e4-105">Bei einer beratenden Anrufübertragung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Nutzer übermittelt.</span><span class="sxs-lookup"><span data-stu-id="a54e4-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="a54e4-106">Ein PSTN-Endpunkt ruft beispielsweise Benutzer a (lync-aufgerufener) auf.</span><span class="sxs-lookup"><span data-stu-id="a54e4-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="a54e4-107">Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B weitergeleitet werden soll (lync-Benutzer).</span><span class="sxs-lookup"><span data-stu-id="a54e4-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="a54e4-108">Der Benutzer A platziert den Anruf mit dem PSTN-Benutzer in Wartestellung und ruft Benutzer b an, der sich mit dem PSTN-Benutzer unterhalten möchte.</span><span class="sxs-lookup"><span data-stu-id="a54e4-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="a54e4-109">Benutzer a übergibt den Anruf in Wartestellung an Benutzer B.</span><span class="sxs-lookup"><span data-stu-id="a54e4-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="a54e4-110">**Anruffluss bei einer Anrufdurchstellung mit Ankündigung**</span><span class="sxs-lookup"><span data-stu-id="a54e4-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="a54e4-111">![Standortbasiertes Routing für Konferenzen (Diagramm)](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Standortbasiertes Routing für Konferenzen (Diagramm)")</span><span class="sxs-lookup"><span data-stu-id="a54e4-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="a54e4-112">Wenn ein für standortbasiertes Routing aktivierter Benutzer eine beratende Anrufübertragung eines PSTN-Endpunkts initiiert (wie in der vorhergehenden Abbildung dargestellt), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und dem lync-Benutzer a und der andere zwischen lync-Benutzer a und lync-Benutzer B erstellt. Das folgende Verhalten wird von der standortbasierten Routing Konferenz Anwendung erzwungen:</span><span class="sxs-lookup"><span data-stu-id="a54e4-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="a54e4-113">Wenn das SIP Trunk-Routing des PSTN-Anrufs autorisiert ist, den PSTN-Anruf an die Netzwerk Website weiterzuleiten, auf der sich der lync-Benutzer B (also das Übertragungsziel) befindet, wird die Anrufübertragung zugelassen. Andernfalls wird die Übertragung von beratenden anrufen blockiert.</span><span class="sxs-lookup"><span data-stu-id="a54e4-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="a54e4-114">Diese Autorisierung erfolgt auf der Grundlage des Standorts der übertragenen Partei, die sich am gleichen Netzwerkstandort wie der SIP-Stamm befindet, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="a54e4-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="a54e4-115">Wenn der SIP-Trunk-Routing der eingehende PSTN-Anruf nicht autorisiert ist, Anrufe an die Netzwerk Website weiterzuleiten, auf der sich die übertragene Partei (lync-Benutzer B) befindet oder sich die übertragene Partei an einer unbekannten Netzwerk Website befindet, wird die beratende Anrufübertragung an das PSTN durchgeführt. Endpunkt (dh Anrufübergabe Ziel) wird blockiert.</span><span class="sxs-lookup"><span data-stu-id="a54e4-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="a54e4-116">In der folgenden Tabelle wird beschrieben, wie standortbasierte Routing Einschränkungen von der standortbasierten Routing Konferenz Anwendung für Beratenden Anruf Übertragungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a54e4-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="a54e4-117">Zwar sind Nebenstellenanlagenendgeräte nicht direkt einem Netzwerkstandort zugewiesen, aber die SIP-Vermittlungsleitung, an die die jeweilige Nebenstellenanlage angeschlossen ist, kann einem Netzwerkstandort zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="a54e4-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="a54e4-118">Daher kann ein Nebenstellenanlagenendgerät indirekt einem Netzwerkstandort zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="a54e4-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-119">Netzwerkstandort des Teilnehmers, dessen Anruf durchgestellt wird</span><span class="sxs-lookup"><span data-stu-id="a54e4-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="a54e4-120">Netzwerk Website des Anruf Weiterleitungs Ziels</span><span class="sxs-lookup"><span data-stu-id="a54e4-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="a54e4-121">Verhalten</span><span class="sxs-lookup"><span data-stu-id="a54e4-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54e4-122">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-123">Lync-Benutzer an derselben Netzwerk Website (also Website 1)</span><span class="sxs-lookup"><span data-stu-id="a54e4-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-124">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-125">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-126">Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="a54e4-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-127">Eine beratende Übertragung ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54e4-128">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-129">Lync-Benutzer in einer unbekannten Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="a54e4-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="a54e4-130">Eine beratende Übertragung ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-131">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-132">Federated lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="a54e4-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="a54e4-133">Eine beratende Übertragung ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54e4-134">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-135">PBX-Endpunkt am gleichen Standort (also Standort 1)</span><span class="sxs-lookup"><span data-stu-id="a54e4-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-136">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-137">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-138">PBX-Endpunkt an verschiedenen Standorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="a54e4-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-139">Eine beratende Übertragung ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54e4-140">PBX-Endpunkt am gleichen Standort (also Standort 1)</span><span class="sxs-lookup"><span data-stu-id="a54e4-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-141">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-142">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-143">PBX-Endpunkt an einer anderen Website (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="a54e4-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-144">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="a54e4-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="a54e4-145">Eine beratende Übertragung ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54e4-146">PBX-Endpunkt auf einer beliebigen Website</span><span class="sxs-lookup"><span data-stu-id="a54e4-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="a54e4-147">Lync-Benutzer an derselben Netzwerk Website (also Website 1)</span><span class="sxs-lookup"><span data-stu-id="a54e4-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-148">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-149">PBX-Endpunkt auf einer beliebigen Website</span><span class="sxs-lookup"><span data-stu-id="a54e4-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="a54e4-150">Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="a54e4-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="a54e4-151">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a54e4-152">PBX-Endpunkt auf einer beliebigen Website</span><span class="sxs-lookup"><span data-stu-id="a54e4-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="a54e4-153">Lync-Benutzer in einer unbekannten Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="a54e4-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="a54e4-154">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a54e4-155">PBX-Endpunkt auf einer beliebigen Website</span><span class="sxs-lookup"><span data-stu-id="a54e4-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="a54e4-156">Federated lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="a54e4-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="a54e4-157">Eine beratende Übertragung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="a54e4-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

