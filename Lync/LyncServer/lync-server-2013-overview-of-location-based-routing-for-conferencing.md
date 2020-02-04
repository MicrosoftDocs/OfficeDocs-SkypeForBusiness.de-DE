---
title: 'Lync Server 2013: Übersicht über standortbasiertes Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="2ba5d-102">Übersicht über standortbasiertes Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ba5d-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba5d-103">_**Letztes Änderungsdatum des Themas:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="2ba5d-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="2ba5d-104">Die standortbasierte Routing Konferenz Anwendung stellt lync-Konferenzen einen Mechanismus zur Verhinderung der PSTN-Maut Umgehung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="2ba5d-105">Die Anwendung überwacht aktive Konferenzen und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Standort der teilnehmenden lync-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="2ba5d-106">Die standortbasierte Routing Konferenz Anwendung bestimmt, ob standortbasiertes Routing für eine lync-Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="2ba5d-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="2ba5d-107">Der Besprechungsorganisator ist für standortbasiertes Routing aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="2ba5d-108">Standortbasierte Routing Einschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="2ba5d-109">Mindestens ein Besprechungsteilnehmer befindet sich an einem Endpunkt im öffentlichen Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="2ba5d-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="2ba5d-110">Standortbasierte Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte umfassen.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="2ba5d-111">Der Netzwerkstandort, an dem sich das PSTN-Gateway zum Überbrücken der Konferenz in das PSTN befindet, wird ebenso lokalisiert wie die Netzwerkstandorte, von denen aus die Organisatoren und Teilnehmer die Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="2ba5d-112">Die standortbasierte Routing Konferenz Anwendung verhindert die Teilnahme von lync-Benutzern und PSTN-Endpunkten von verschiedenen Netzwerkstandorten an derselben Konferenz.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="2ba5d-113">Wenn der Organisator einer Besprechung für standortbasiertes Routing aktiviert ist, erzwingt die Konferenz Anwendung die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="2ba5d-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="2ba5d-114">Die Endpunkte, die an einer lync-Besprechung teilnehmen können, hängen von den Endpunkten ab, die bereits der Konferenz beigetreten sind, und diese Einschränkung passt sich an, wenn verknüpfte Endpunkte verlassen und neue Endpunkte der Konferenz</span><span class="sxs-lookup"><span data-stu-id="2ba5d-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="2ba5d-115">Wenn Organisatoren und Teilnehmer einer lync-Besprechung von derselben Netzwerk Website aus beitreten, kann ein PSTN-Endpunkt, ein anderer Teilnehmer desselben Netzwerkstandorts, ein anderer Teilnehmer einer anderen Netzwerk Website oder ein Teilnehmer von einer unbekannten Netzwerk Website teilnehmen an.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="2ba5d-116">Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, darf ein Teilnehmer an einem PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem SIP-Trunk eingeht, der für das standortbasierte Routing aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="2ba5d-117">Wenn Organisatoren und Teilnehmer an der Besprechung von der gleichen Netzwerk Website teilnehmen und Teilnehmer derselben Besprechung über das PSTN beitreten, ist ein lync-Endpunkt von einer anderen Netzwerk Website nicht berechtigt, an der Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="2ba5d-118">In der folgenden Tabelle sind diese standortbasierten Routing Einschränkungen für Konferenzen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ba5d-119">Benutzer in einer Konferenz an einem beliebigen Standort</span><span class="sxs-lookup"><span data-stu-id="2ba5d-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-120">Benutzer, die an der Konferenz teilnehmen dürfen</span><span class="sxs-lookup"><span data-stu-id="2ba5d-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-121">Benutzer, die nicht an der Konferenz teilnehmen dürfen</span><span class="sxs-lookup"><span data-stu-id="2ba5d-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba5d-122">Lync VoIP-Clientbenutzer (s) von einer einzelnen Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-123">Lync-VoIP-Clientbenutzer vom gleichen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="2ba5d-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="2ba5d-124">Lync-VoIP-Clientbenutzer von einer anderen Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="2ba5d-125">Lync-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="2ba5d-126">Verbund-lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="2ba5d-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="2ba5d-127">Benutzer, die über PSTN-Endpunkt teilnehmen</span><span class="sxs-lookup"><span data-stu-id="2ba5d-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-128">-</span><span class="sxs-lookup"><span data-stu-id="2ba5d-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ba5d-129">Lync VoIP-Clientbenutzer (s) von einer unbekannten Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-130">Lync-VoIP-Clientbenutzer von einer beliebigen Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="2ba5d-131">Lync-VoIP-Clientbenutzer von einer unbekannten Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="2ba5d-132">Verbund-lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="2ba5d-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-133">Benutzer, die über einen PSTN-Endpunkt teilnehmen</span><span class="sxs-lookup"><span data-stu-id="2ba5d-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba5d-134">Lync-VoIP-Clientbenutzer von verschiedenen Netzwerkstandorten aus</span><span class="sxs-lookup"><span data-stu-id="2ba5d-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-135">Lync-VoIP-Clientbenutzer von einer beliebigen Netzwerk Website aus</span><span class="sxs-lookup"><span data-stu-id="2ba5d-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="2ba5d-136">Lync-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="2ba5d-137">Verbund-lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="2ba5d-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-138">Benutzer, die über einen PSTN-Endpunkt teilnehmen</span><span class="sxs-lookup"><span data-stu-id="2ba5d-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ba5d-139">Lync-VoIP-Clientbenutzer von einer einzigen Netzwerk Website und Benutzern, die von einem PSTN-Endpunkt beitreten</span><span class="sxs-lookup"><span data-stu-id="2ba5d-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-140">Lync-VoIP-Clientbenutzer vom gleichen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="2ba5d-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="2ba5d-141">Lync-VoIP-Clientbenutzer von einer anderen Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="2ba5d-142">Lync-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="2ba5d-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="2ba5d-143">Verbund-lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="2ba5d-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ba5d-144">Im folgenden finden Sie zusätzliche Merkmale der standortbasierten Routing Konferenz Anwendung:</span><span class="sxs-lookup"><span data-stu-id="2ba5d-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="2ba5d-145">Wenn ein Benutzer nicht berechtigt ist, an einer Konferenz teilzunehmen, wenn standortbasierte Routing Einschränkungen gelten, wird der Benutzer, der die Konferenz führt, abgelehnt, und sein lync-Client meldet, dass der Anruf nicht abgeschlossen oder beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="2ba5d-146">Ein PSTN-Endpunkt, der an einer Konferenz mit ortsbasierten Routing Erzwingungen teilnimmt, ist nicht auf die Teilnahme an der Konferenz beschränkt, unabhängig von seinem Zustand, wenn der Endpunkt über einen trunk verbunden wird, der für standortbasiertes Routing nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="2ba5d-147">Ein PBX-System, das mit einem Vermittlungs Server über einen SIP-Stamm verbunden ist, der keine Anrufe an das PSTN abruft, hat die gleichen erzwungenen wie lync-Benutzer, die sich am gleichen Netzwerkstandort befinden, an dem der SIP-Stamm definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="2ba5d-148">Beispielsweise kann ein PSTN-Endpunkt an einer Konferenz mit einem PBX-Benutzer und einem lync-Benutzer teilnehmen, wenn er sich im gleichen Netzwerkstandort befindet. Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort als der lync-Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="2ba5d-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

