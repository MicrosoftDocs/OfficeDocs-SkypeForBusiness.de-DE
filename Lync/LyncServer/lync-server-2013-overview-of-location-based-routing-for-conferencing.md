---
title: 'Lync Server 2013: Übersicht über das Location-Based Routing für Konferenzen'
description: 'Lync Server 2013: Übersicht über das Location-Based Routing für Konferenzen.'
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
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577371"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="71a8a-103">Übersicht über Location-Based Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a8a-103">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a8a-104">_**Letztes Änderungsstand des Themas:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="71a8a-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="71a8a-105">Die Location-Based Routing Konferenz Anwendung bietet lync-Konferenzen einen Mechanismus zur Verhinderung der PSTN-Maut Umgehung.</span><span class="sxs-lookup"><span data-stu-id="71a8a-105">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="71a8a-106">Die Anwendung überwacht aktive Konferenzen und erzwingt Location-Based Routing Einschränkungen basierend auf dem Speicherort der teilnehmenden lync-Benutzer.</span><span class="sxs-lookup"><span data-stu-id="71a8a-106">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="71a8a-107">Die Location-Based Routing Konferenz Anwendung bestimmt, ob Location-Based Routing in einer lync-Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="71a8a-107">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="71a8a-108">Der Besprechungsorganisator ist für Location-Based Routing aktiviert.</span><span class="sxs-lookup"><span data-stu-id="71a8a-108">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="71a8a-109">Location-Based Routing Einschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für Location-Based Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="71a8a-109">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="71a8a-110">Mindestens ein Besprechungsteilnehmer ist ein PSTN-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="71a8a-110">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="71a8a-111">Location-Based Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte enthalten.</span><span class="sxs-lookup"><span data-stu-id="71a8a-111">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="71a8a-112">Der Netzwerkstandort, an dem das PSTN-Gateway verwendet wurde, um die Konferenz mit dem PSTN zu überbrücken, befindet sich ebenso wie die Netzwerkstandorte, von denen die Organisatoren und Teilnehmer eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="71a8a-112">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="71a8a-113">Die Location-Based Routing Konferenz Anwendung verhindert die Teilnahme von lync-Benutzern und PSTN-Endpunkten von verschiedenen Netzwerkstandorten an dieselbe Konferenz.</span><span class="sxs-lookup"><span data-stu-id="71a8a-113">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="71a8a-114">Wenn der Organisator einer Besprechung für Location-Based Routing aktiviert ist, erzwingt die Konferenz Anwendung die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="71a8a-114">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="71a8a-115">Die Endpunkte, die an einer lync-Besprechung teilnehmen können, hängen von den Endpunkten ab, die bereits der Konferenz beigetreten sind, und diese Einschränkung wird als Joined Endpoint Leave und neue Endpunkte an der Konferenz angepasst.</span><span class="sxs-lookup"><span data-stu-id="71a8a-115">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="71a8a-116">Wenn Organisatoren und Teilnehmern eine lync-Besprechung vom gleichen Netzwerkstandort aus beitreten, können ein PSTN-Endpunkt, ein anderer Teilnehmer desselben Netzwerkstandorts, ein anderer Teilnehmer von einem anderen Netzwerkstandort oder ein Teilnehmer an einem unbekannten Netzwerkstandort beitreten.</span><span class="sxs-lookup"><span data-stu-id="71a8a-116">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="71a8a-117">Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, kann ein PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem für Location-Based Routing aktivierten SIP-Trunk abweicht.</span><span class="sxs-lookup"><span data-stu-id="71a8a-117">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="71a8a-118">Wenn Organisatoren und Teilnehmer an der Besprechung vom gleichen Netzwerkstandort aus beitreten und Teilnehmer derselben Besprechung aus dem PSTN beitreten, kann ein lync-Endpunkt von einem anderen Netzwerkstandort nicht an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="71a8a-118">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="71a8a-119">Diese Location-Based Routing Einschränkungen für Konferenzen werden in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="71a8a-119">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71a8a-120">Benutzer in einer Konferenz zu einem bestimmten Zeitpunkt</span><span class="sxs-lookup"><span data-stu-id="71a8a-120">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="71a8a-121">Benutzer dürfen an der Konferenz teilnehmen</span><span class="sxs-lookup"><span data-stu-id="71a8a-121">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="71a8a-122">Benutzer dürfen nicht an der Konferenz teilnehmen</span><span class="sxs-lookup"><span data-stu-id="71a8a-122">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71a8a-123">Lync VoIP-Clientbenutzer (n) von einem einzelnen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-123">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="71a8a-124">Lync VoIP-Clientbenutzer am gleichen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-124">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="71a8a-125">Lync VoIP-Clientbenutzer von einem anderen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-125">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="71a8a-126">Lync VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-126">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="71a8a-127">Partner für lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="71a8a-127">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="71a8a-128">Benutzer Beitritt von einem PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="71a8a-128">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="71a8a-129">Keine</span><span class="sxs-lookup"><span data-stu-id="71a8a-129">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71a8a-130">Lync VoIP-Clientbenutzer (n) von einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-130">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="71a8a-131">Lync VoIP-Clientbenutzer von einem beliebigen Standort aus</span><span class="sxs-lookup"><span data-stu-id="71a8a-131">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="71a8a-132">Lync VoIP-Clientbenutzer von einem unbekannten Standort</span><span class="sxs-lookup"><span data-stu-id="71a8a-132">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="71a8a-133">Partner für lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="71a8a-133">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="71a8a-134">Benutzer Beitritt über einen PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="71a8a-134">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71a8a-135">Lync VoIP-Clientbenutzer von verschiedenen Netzwerkstandorten aus</span><span class="sxs-lookup"><span data-stu-id="71a8a-135">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="71a8a-136">Lync VoIP-Clientbenutzer von einem beliebigen Netzwerkstandort aus</span><span class="sxs-lookup"><span data-stu-id="71a8a-136">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="71a8a-137">Lync VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-137">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="71a8a-138">Partner für lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="71a8a-138">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="71a8a-139">Benutzer Beitritt über einen PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="71a8a-139">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71a8a-140">Lync VoIP-Clientbenutzer von einem einzelnen Netzwerkstandort aus und Benutzer, die von einem PSTN-Endpunkt beitreten</span><span class="sxs-lookup"><span data-stu-id="71a8a-140">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="71a8a-141">Lync VoIP-Clientbenutzer am gleichen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-141">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="71a8a-142">Lync VoIP-Clientbenutzer von einem anderen Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-142">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="71a8a-143">Lync VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="71a8a-143">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="71a8a-144">Partner für lync-VoIP-Clientbenutzer</span><span class="sxs-lookup"><span data-stu-id="71a8a-144">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="71a8a-145">Im folgenden finden Sie weitere Merkmale der Anwendung für die Location-Based Routing Konferenz:</span><span class="sxs-lookup"><span data-stu-id="71a8a-145">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="71a8a-146">Wenn ein Benutzer nicht berechtigt ist, an einer Konferenz teilzunehmen, die Location-Based Routing Einschränkungen unterliegt, wird der Benutzer an der Konferenz angerufen, und sein lync-Client meldet, dass der Anruf nicht abgeschlossen oder beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="71a8a-146">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="71a8a-147">Ein PSTN-Endpunkt, der einer Konferenz mit Location-Based Routing-Erzwingung Beitritt, wird nicht auf den Beitritt zur Konferenz beschränkt, unabhängig von seinem Status, wenn der Endpunkt über einen trunk Beitritt, der für Location-Based Routing nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="71a8a-147">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="71a8a-148">Ein Nebenstellen System, das mit einem Vermittlungs Server über einen SIP-Trunk verbunden ist und keine Anrufe an das PSTN ausgeht, hat dieselben erzwungenen wie lync-Benutzer, die sich am selben Netzwerkstandort befinden, an dem der SIP-Trunk definiert ist.</span><span class="sxs-lookup"><span data-stu-id="71a8a-148">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="71a8a-149">Beispielsweise kann ein PSTN-Endpunkt an einer Konferenz mit einem PBX-Benutzer und einem lync-Benutzer teilnehmen, wenn er sich am selben Netzwerkstandort befindet; Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort als der lync-Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="71a8a-149">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

