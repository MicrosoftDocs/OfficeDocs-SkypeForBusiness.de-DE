---
title: 'Lync Server 2013: Location-Based weiterleiten und beratende Anruf Übertragungen'
description: 'Lync Server 2013: Location-Based weiterleiten und beratende Anruf Übertragungen.'
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567671"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="b2a74-103">Location-Based Weiterleiten von Anrufen und Anrufweiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2a74-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2a74-104">_**Letztes Änderungsstand des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="b2a74-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="b2a74-105">Neben der Erzwingung Location-Based Routings an lync-Besprechungen erzwingt die Location-Based Routing Konferenz Anwendung Location-Based Routing Einschränkungen für Anrufe, die an PSTN-Endpunkten ausgehen.</span><span class="sxs-lookup"><span data-stu-id="b2a74-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="b2a74-106">Bei einer beratenden Anrufweiterleitung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Benutzer überträgt.</span><span class="sxs-lookup"><span data-stu-id="b2a74-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="b2a74-107">Ein PSTN-Endpunkt ruft beispielsweise Benutzer a (lync-angerufener) auf.</span><span class="sxs-lookup"><span data-stu-id="b2a74-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="b2a74-108">Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B (lync-Benutzer) weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2a74-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="b2a74-109">Benutzer a platziert den Anruf mit dem PSTN-Benutzer in der Warteschleife und ruft Benutzer b an, der mit dem PSTN-Benutzer zu sprechen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b2a74-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="b2a74-110">Der Benutzer a übergibt den Anruf einhalten an Benutzer B.</span><span class="sxs-lookup"><span data-stu-id="b2a74-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="b2a74-111">**Anruffluss für Anrufweiterleitung mit beratender Funktion**</span><span class="sxs-lookup"><span data-stu-id="b2a74-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="b2a74-112">![Standortbasiertes Routing für Konferenz Diagramm](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Standortbasiertes Routing für Konferenz Diagramm")</span><span class="sxs-lookup"><span data-stu-id="b2a74-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="b2a74-113">Wenn ein für Location-Based Routing aktivierter Benutzer eine beratende Anrufübertragung eines PSTN-Endpunkts initiiert (wie in der obigen Abbildung dargestellt), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und dem lync-Benutzer a und der andere zwischen lync User a und lync User B erstellt. das folgende Verhalten wird von der Location-Based Routing Konferenz Anwendung erzwungen:</span><span class="sxs-lookup"><span data-stu-id="b2a74-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="b2a74-114">Wenn das SIP-Trunk Routing der PSTN-Anruf autorisiert ist, den PSTN-Anruf an den Netzwerkstandort weiterzuleiten, auf dem sich der lync-Benutzer B (also das Übertragungsziel) befindet, wird die Anrufweiterleitung zugelassen. Andernfalls wird die beratende Anrufweiterleitung blockiert.</span><span class="sxs-lookup"><span data-stu-id="b2a74-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="b2a74-115">Diese Autorisierung wird basierend auf dem Standort des übertragenen Teilnehmers am gleichen Netzwerkstandort wie der SIP-Trunk ausgeführt, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="b2a74-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="b2a74-116">Wenn das SIP-Trunk Routing des eingehenden PSTN-Anrufs nicht zum Weiterleiten von Anrufen an den Netzwerkstandort autorisiert ist, auf dem sich der übermittelte Teilnehmer (lync User B) befindet oder sich der übertragene Teilnehmer an einem unbekannten Netzwerkstandort befindet, wird die beratende Anrufweiterleitung an den PSTN-Endpunkt (i.e. Anruf Übertragungsziel) blockiert.</span><span class="sxs-lookup"><span data-stu-id="b2a74-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="b2a74-117">In der folgenden Tabelle wird beschrieben, wie Location-Based Routing Einschränkungen von der Location-Based Routing Konferenz Anwendung für beratende Anruf Übertragungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2a74-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="b2a74-118">Obwohl PBX-Endpunkte keinem Netzwerkstandort direkt zugeordnet sind, kann dem SIP-Trunk, mit dem die Nebenstellenanlage verbunden ist, ein Netzwerkstandort zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b2a74-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="b2a74-119">Daher kann der PBX-Endpunkt indirekt einem Netzwerkstandort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b2a74-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-120">Netzwerkstandort der Anruf übertragenden Partei</span><span class="sxs-lookup"><span data-stu-id="b2a74-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="b2a74-121">Netzwerkstandort des Anruf Übertragungs Ziels</span><span class="sxs-lookup"><span data-stu-id="b2a74-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="b2a74-122">Verhalten</span><span class="sxs-lookup"><span data-stu-id="b2a74-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a74-123">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-124">Lync-Benutzer am gleichen Netzwerkstandort (also Standort 1)</span><span class="sxs-lookup"><span data-stu-id="b2a74-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-125">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-126">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-127">Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="b2a74-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-128">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="b2a74-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a74-129">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-130">Lync-Benutzer an einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="b2a74-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="b2a74-131">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="b2a74-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-132">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-133">Verbund-lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="b2a74-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="b2a74-134">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="b2a74-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a74-135">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-136">Nebenstellen Endpunkt am gleichen Standort (Standort 1)</span><span class="sxs-lookup"><span data-stu-id="b2a74-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-137">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-138">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-139">Nebenstellen Endpunkt an verschiedenen Standorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="b2a74-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-140">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="b2a74-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a74-141">Nebenstellen Endpunkt am gleichen Standort (Standort 1)</span><span class="sxs-lookup"><span data-stu-id="b2a74-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-142">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-143">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-144">Nebenstellen Endpunkt an einem anderen Standort (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="b2a74-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-145">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b2a74-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b2a74-146">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="b2a74-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a74-147">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="b2a74-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="b2a74-148">Lync-Benutzer am gleichen Netzwerkstandort (also Standort 1)</span><span class="sxs-lookup"><span data-stu-id="b2a74-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-149">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-150">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="b2a74-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="b2a74-151">Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="b2a74-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="b2a74-152">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2a74-153">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="b2a74-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="b2a74-154">Lync-Benutzer an einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="b2a74-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="b2a74-155">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2a74-156">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="b2a74-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="b2a74-157">Verbund-lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="b2a74-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="b2a74-158">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="b2a74-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

