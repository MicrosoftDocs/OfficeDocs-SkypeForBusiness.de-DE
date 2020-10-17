---
title: 'Lync Server 2013: Location-Based weiterleiten und beratende Anruf Übertragungen'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513812"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="6bd52-102">Location-Based Weiterleiten von Anrufen und Anrufweiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bd52-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bd52-103">_**Letztes Änderungsstand des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="6bd52-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="6bd52-104">Neben der Erzwingung Location-Based Routings an lync-Besprechungen erzwingt die Location-Based Routing Konferenz Anwendung Location-Based Routing Einschränkungen für Anrufe, die an PSTN-Endpunkten ausgehen.</span><span class="sxs-lookup"><span data-stu-id="6bd52-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="6bd52-105">Bei einer beratenden Anrufweiterleitung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Benutzer überträgt.</span><span class="sxs-lookup"><span data-stu-id="6bd52-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="6bd52-106">Ein PSTN-Endpunkt ruft beispielsweise Benutzer a (lync-angerufener) auf.</span><span class="sxs-lookup"><span data-stu-id="6bd52-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="6bd52-107">Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B (lync-Benutzer) weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6bd52-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="6bd52-108">Benutzer a platziert den Anruf mit dem PSTN-Benutzer in der Warteschleife und ruft Benutzer b an, der mit dem PSTN-Benutzer zu sprechen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="6bd52-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="6bd52-109">Der Benutzer a übergibt den Anruf einhalten an Benutzer B.</span><span class="sxs-lookup"><span data-stu-id="6bd52-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="6bd52-110">**Anruffluss für Anrufweiterleitung mit beratender Funktion**</span><span class="sxs-lookup"><span data-stu-id="6bd52-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="6bd52-111">![Standortbasiertes Routing für Konferenz Diagramm](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Standortbasiertes Routing für Konferenz Diagramm")</span><span class="sxs-lookup"><span data-stu-id="6bd52-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="6bd52-112">Wenn ein für Location-Based Routing aktivierter Benutzer eine beratende Anrufübertragung eines PSTN-Endpunkts initiiert (wie in der obigen Abbildung dargestellt), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und dem lync-Benutzer a und der andere zwischen lync User a und lync User B erstellt. das folgende Verhalten wird von der Location-Based Routing Konferenz Anwendung erzwungen:</span><span class="sxs-lookup"><span data-stu-id="6bd52-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="6bd52-113">Wenn das SIP-Trunk Routing der PSTN-Anruf autorisiert ist, den PSTN-Anruf an den Netzwerkstandort weiterzuleiten, auf dem sich der lync-Benutzer B (also das Übertragungsziel) befindet, wird die Anrufweiterleitung zugelassen. Andernfalls wird die beratende Anrufweiterleitung blockiert.</span><span class="sxs-lookup"><span data-stu-id="6bd52-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="6bd52-114">Diese Autorisierung wird basierend auf dem Standort des übertragenen Teilnehmers am gleichen Netzwerkstandort wie der SIP-Trunk ausgeführt, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="6bd52-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="6bd52-115">Wenn das SIP-Trunk Routing des eingehenden PSTN-Anrufs nicht zum Weiterleiten von Anrufen an den Netzwerkstandort autorisiert ist, auf dem sich der übermittelte Teilnehmer (lync User B) befindet oder sich der übertragene Teilnehmer an einem unbekannten Netzwerkstandort befindet, wird die beratende Anrufweiterleitung an den PSTN-Endpunkt (i.e. Anruf Übertragungsziel) blockiert.</span><span class="sxs-lookup"><span data-stu-id="6bd52-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="6bd52-116">In der folgenden Tabelle wird beschrieben, wie Location-Based Routing Einschränkungen von der Location-Based Routing Konferenz Anwendung für beratende Anruf Übertragungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6bd52-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="6bd52-117">Obwohl PBX-Endpunkte keinem Netzwerkstandort direkt zugeordnet sind, kann dem SIP-Trunk, mit dem die Nebenstellenanlage verbunden ist, ein Netzwerkstandort zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="6bd52-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="6bd52-118">Daher kann der PBX-Endpunkt indirekt einem Netzwerkstandort zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6bd52-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-119">Netzwerkstandort der Anruf übertragenden Partei</span><span class="sxs-lookup"><span data-stu-id="6bd52-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="6bd52-120">Netzwerkstandort des Anruf Übertragungs Ziels</span><span class="sxs-lookup"><span data-stu-id="6bd52-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="6bd52-121">Verhalten</span><span class="sxs-lookup"><span data-stu-id="6bd52-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd52-122">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-123">Lync-Benutzer am gleichen Netzwerkstandort (also Standort 1)</span><span class="sxs-lookup"><span data-stu-id="6bd52-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-124">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-125">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-126">Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="6bd52-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-127">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="6bd52-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd52-128">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-129">Lync-Benutzer an einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="6bd52-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="6bd52-130">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="6bd52-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-131">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-132">Verbund-lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="6bd52-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="6bd52-133">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="6bd52-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd52-134">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-135">Nebenstellen Endpunkt am gleichen Standort (Standort 1)</span><span class="sxs-lookup"><span data-stu-id="6bd52-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-136">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-137">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-138">Nebenstellen Endpunkt an verschiedenen Standorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="6bd52-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-139">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="6bd52-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd52-140">Nebenstellen Endpunkt am gleichen Standort (Standort 1)</span><span class="sxs-lookup"><span data-stu-id="6bd52-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-141">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-142">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-143">Nebenstellen Endpunkt an einem anderen Standort (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="6bd52-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-144">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6bd52-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6bd52-145">Die beratende Übertragung wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="6bd52-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd52-146">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="6bd52-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6bd52-147">Lync-Benutzer am gleichen Netzwerkstandort (also Standort 1)</span><span class="sxs-lookup"><span data-stu-id="6bd52-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-148">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-149">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="6bd52-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6bd52-150">Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</span><span class="sxs-lookup"><span data-stu-id="6bd52-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6bd52-151">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd52-152">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="6bd52-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6bd52-153">Lync-Benutzer an einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="6bd52-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="6bd52-154">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd52-155">PBX-Endpunkt an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="6bd52-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6bd52-156">Verbund-lync-Benutzer</span><span class="sxs-lookup"><span data-stu-id="6bd52-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="6bd52-157">Beratende Übertragung wird zugelassen</span><span class="sxs-lookup"><span data-stu-id="6bd52-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

