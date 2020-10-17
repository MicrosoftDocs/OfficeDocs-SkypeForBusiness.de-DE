---
title: 'Lync Server 2013: Bereitstellungsprozess für Location-Based Routing'
description: 'Lync Server 2013: Bereitstellungsprozess für Location-Based Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551061"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="02022-103">Bereitstellungsprozess für Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02022-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02022-104">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="02022-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="02022-105">Dieses Thema bietet eine Übersicht über den Prozess, der beim Konfigurieren Location-Based Routings erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="02022-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="02022-106">Sie müssen lync Server Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie Location-Based Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="02022-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="02022-107">Die für Location-Based Routing erforderlichen Komponenten sind bereits installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="02022-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="02022-108">Location-Based Routing Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="02022-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02022-109">Phase</span><span class="sxs-lookup"><span data-stu-id="02022-109">Phase</span></span></th>
<th><span data-ttu-id="02022-110">Schritte</span><span class="sxs-lookup"><span data-stu-id="02022-110">Steps</span></span></th>
<th><span data-ttu-id="02022-111">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="02022-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="02022-112">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="02022-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-113">Bereitstellen von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="02022-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="02022-114">Konfigurieren von Trunks</span><span class="sxs-lookup"><span data-stu-id="02022-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="02022-115">Erstellen von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="02022-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="02022-116">Definieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="02022-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="02022-117">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="02022-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="02022-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-118">CsAdministrator</span></span><br />
<span data-ttu-id="02022-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="02022-120">Bereitstellen von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="02022-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02022-121">Überprüfen Ihrer Enterprise-VoIP-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="02022-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="02022-122">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="02022-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="02022-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-123">CsAdministrator</span></span><br />
<span data-ttu-id="02022-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02022-125">Konfigurieren von netzwerkregionen, Standorten und Subnetzen</span><span class="sxs-lookup"><span data-stu-id="02022-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="02022-126">Erstellen von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="02022-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="02022-127">Erstellen von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="02022-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="02022-128">Assoziierte Subnetze mit Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="02022-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="02022-129">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="02022-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="02022-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-130">CsAdministrator</span></span><br />
<span data-ttu-id="02022-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="02022-132">Grundlegende Informationen zu Netzwerkregionen, Standorten und Subnetzen</span><span class="sxs-lookup"><span data-stu-id="02022-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="02022-133">Erstellen oder Ändern einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="02022-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="02022-134">Erstellen oder Ändern eines Netzwerkstandorts</span><span class="sxs-lookup"><span data-stu-id="02022-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="02022-135">Zuordnen eines Subnetzes zu einem Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="02022-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02022-136">Konfigurieren des Location-Based Routings</span><span class="sxs-lookup"><span data-stu-id="02022-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="02022-137">Erstellen von Richtlinien für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="02022-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="02022-138">Definieren einer separaten trunkkonfiguration pro trunk</span><span class="sxs-lookup"><span data-stu-id="02022-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="02022-139">Ändern von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="02022-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="02022-140">Aktivieren Location-Based Routing Konfiguration</span><span class="sxs-lookup"><span data-stu-id="02022-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="02022-141">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="02022-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="02022-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-142">CsAdministrator</span></span><br />
<span data-ttu-id="02022-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02022-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="02022-144">Beispielbereitstellung</span><span class="sxs-lookup"><span data-stu-id="02022-144">Sample Deployment</span></span>

<span data-ttu-id="02022-145">Die folgende Bereitstellung wird verwendet, um die durch Location-Based Routing aktivierten Mechanismen zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="02022-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="02022-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="02022-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="02022-147">Eingehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="02022-147">Incoming PSTN calls</span></span>

<span data-ttu-id="02022-148">Ein Administrator kann den definierten trunk aktivieren, um Anrufe an "Standort 1-Gateway" für Location-Based Routing weiterzuleiten und das "Standort 1-Gateway" zu Standort 1 zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="02022-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="02022-149">Nach der Aktivierung werden Anrufe, die über das Gateway "Standort 1" weitergeleitet werden, nur an Benutzer weitergeleitet, die sich an Standort 1 befinden.</span><span class="sxs-lookup"><span data-stu-id="02022-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="02022-150">Alle Anrufe, die über den trunk "Standort 1-Gateway" geleitet werden, der für Benutzer an einem anderen Standort bestimmt ist, wie etwa Standort 2, werden blockiert, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="02022-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="02022-151">Alle eingehenden PSTN-Anrufe über "Standort 1-Gateway" dürfen nur an Endpunkte an Standort 1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="02022-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="02022-152">Wenn beispielsweise "lync Benutzer 1" zu Standort 2 reist, werden alle eingehenden PSTN-Anrufe über "Standort 1-Gateway" nicht an die Endpunkte von "lync User 1" an Standort 2 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="02022-153">Dieselbe Routingregel gilt, wenn "lync Benutzer 1" zu einem unbekannten Netzwerkstandort reist, in dem der Speicherort des Benutzers nicht ermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="02022-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="02022-154">In der folgenden Tabelle wird die Benutzerfreundlichkeit von "lync User 1" in diesem Kontext erläutert.</span><span class="sxs-lookup"><span data-stu-id="02022-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="02022-155">Lync User 1-Endpunkte an Netzwerkstandort 1</span><span class="sxs-lookup"><span data-stu-id="02022-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="02022-156">Lync User 1-Endpunkte an Netzwerkstandort 2</span><span class="sxs-lookup"><span data-stu-id="02022-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="02022-157">Lync User 1-Endpunkte befinden sich an einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="02022-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-158">Eingehende PSTN-Anrufe an lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="02022-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="02022-159">Anrufe werden an diesem Speicherort an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="02022-160">Anrufe werden an diesem Speicherort nicht an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="02022-161">Anrufe werden an diesem Speicherort nicht an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="02022-162">Ausgehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="02022-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="02022-163">Auf VoIP-Routen wird in beiden VoIP-Richtlinien verwiesen, die direkt Benutzern zugewiesen sind, sowie auf VoIP-Routing Richtlinien, die Netzwerkstandorten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="02022-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="02022-164">Beide Richtlinien enthalten Verweise auf Routen, die verwendet werden können, um einen Anruf anders weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="02022-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="02022-165">Beispielsweise kann ein Administrator eine VoIP-Routing Richtlinie für alle Benutzer definieren, die sich im Netzwerkstandort 1 befinden, um alle ausgehenden Anrufe über das Gateway "Standort 1" weiterzuleiten, während die VoIP-Richtlinie einiger Benutzer eine Route für alle ausgehenden Anrufe über das Gateway "Standort 2" definiert.</span><span class="sxs-lookup"><span data-stu-id="02022-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="02022-166">Während sich diese Benutzer im Netzwerkstandort 1 befinden, werden Ihre ausgehenden Anrufe über das Gateway "Standort 1" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="02022-167">Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing konfiguriert ist, überschreibt die Route der VoIP-Routing Richtlinie des Netzwerkstandorts die VoIP-Richtlinien Route des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="02022-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="02022-168">Diese Regel ist besonders nützlich für Benutzer, die vorübergehend zu einer anderen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="02022-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="02022-169">In diesem speziellen Fall verwendet ein Benutzer immer ein Gateway, das lokal an seinem Standort ist; Wenn sich "lync User 3" unter "Standort 2" befindet, werden alle ausgehenden Anrufe über "Standort-2-Gateway" weitergeleitet, aber wenn er zu Standort 1 reist, werden alle ausgehenden Anrufe, die bei Standort 1 getätigt werden, über "Standort 1-Gateway" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="02022-170">In der folgenden Tabelle wird die Benutzererfahrung von lync User 1, die einen ausgehenden Anruf von den folgenden Netzwerkstandorten aus durch zeigt, dargestellt.</span><span class="sxs-lookup"><span data-stu-id="02022-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="02022-171">Netzwerkstandort 1</span><span class="sxs-lookup"><span data-stu-id="02022-171">Network site 1</span></span></th>
<th><span data-ttu-id="02022-172">Netzwerkstandort 2</span><span class="sxs-lookup"><span data-stu-id="02022-172">Network site 2</span></span></th>
<th><span data-ttu-id="02022-173">Unbekannter Netzwerkstandort oder nicht für Location-Based Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="02022-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-174">Autorisierung für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="02022-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="02022-175">VoIP-Richtlinie für lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="02022-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="02022-176">VoIP-Richtlinie für lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="02022-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="02022-177">VoIP-Richtlinie für lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="02022-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02022-178">Weiterleiten von ausgehenden Anrufen</span><span class="sxs-lookup"><span data-stu-id="02022-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="02022-179">VoIP-Routing Richtlinie für Standort 1</span><span class="sxs-lookup"><span data-stu-id="02022-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="02022-180">VoIP-Routing Richtlinie für Standort 2</span><span class="sxs-lookup"><span data-stu-id="02022-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="02022-181">VoIP-Richtlinie des Benutzers und nur für nicht für Location-Based Routing aktivierte Systeme</span><span class="sxs-lookup"><span data-stu-id="02022-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="02022-182">Anruf Übertragungen und-Weiterleitungen</span><span class="sxs-lookup"><span data-stu-id="02022-182">Call transfers and forwards</span></span>

<span data-ttu-id="02022-183">Wenn Anrufe übertragen oder weitergeleitet werden, ist das Routing von Anrufen von Location-Based Routing betroffen.</span><span class="sxs-lookup"><span data-stu-id="02022-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="02022-184">In der folgenden Tabelle wird lync-Benutzer 1, der einen PSTN-Anruf an einen anderen lync-Benutzer übertragen oder weiterleitet, dargestellt.</span><span class="sxs-lookup"><span data-stu-id="02022-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02022-185">Benutzer, der die Anrufweiterleitung initiiert oder weiterleitet</span><span class="sxs-lookup"><span data-stu-id="02022-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="02022-186">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="02022-186">Lync user 2</span></span></th>
<th><span data-ttu-id="02022-187">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="02022-187">Lync user 4</span></span></th>
<th><span data-ttu-id="02022-188">Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="02022-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-189">Lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="02022-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="02022-190">Anrufweiterleitung oder-Übertragung ist zulässig</span><span class="sxs-lookup"><span data-stu-id="02022-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="02022-191">Anrufweiterleitung oder-Übertragung ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="02022-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="02022-192">Anrufweiterleitung oder-Übertragung ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="02022-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="02022-193">In der folgenden Tabelle wird veranschaulicht, wie sich Location-Based Routing auf die Weiterleitung des Anrufs basierend auf dem Standort des übertragenden lync-Benutzers (lync Benutzer 2, lync-Benutzer 4 usw.) an einen PSTN-Endpunkt auswirkt.</span><span class="sxs-lookup"><span data-stu-id="02022-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02022-194">Endpunkt, an den der Anruf übertragen oder an diese weitergeleitet wird</span><span class="sxs-lookup"><span data-stu-id="02022-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="02022-195">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="02022-195">Lync user 2</span></span></th>
<th><span data-ttu-id="02022-196">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="02022-196">Lync user 4</span></span></th>
<th><span data-ttu-id="02022-197">Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="02022-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-198">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="02022-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="02022-199">Anrufweiterleitung oder-Übertragung wird über Standort 1-VoIP-Routing Richtlinie und Ausstieg über Standort 1-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="02022-200">Anrufweiterleitung oder-Übertragung wird über Standort 2-VoIP-Routing Richtlinie und Ausstieg über Standort-2-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="02022-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="02022-201">Anrufweiterleitung oder-Übertragung wird über die VoIP-Richtlinie für lync-Benutzer weitergeleitet und über ein Gateway nicht für standortbasiertes Routing aktiviert (sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="02022-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="02022-202">Gleichzeitiges Klingeln</span><span class="sxs-lookup"><span data-stu-id="02022-202">Simultaneous ringing</span></span>

<span data-ttu-id="02022-203">Nachdem das standortbasierte Routing in der Beispieltopologie konfiguriert wurde, werden die folgenden Interaktionen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="02022-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="02022-204">In der folgenden Tabelle wird gezeigt, ob Location-Based Routing das gleichzeitige Klingeln für verschiedene lync-Benutzer ermöglicht (also lync User 2, lync User 4 usw.).</span><span class="sxs-lookup"><span data-stu-id="02022-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02022-205">Ziel eines eingehenden PSTN-Anrufs</span><span class="sxs-lookup"><span data-stu-id="02022-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="02022-206">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="02022-206">Lync user 2</span></span></th>
<th><span data-ttu-id="02022-207">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="02022-207">Lync user 4</span></span></th>
<th><span data-ttu-id="02022-208">Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="02022-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-209">Lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="02022-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="02022-210">Gleichzeitiges Klingeln ist zulässig</span><span class="sxs-lookup"><span data-stu-id="02022-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="02022-211">Gleichzeitiges Klingeln ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="02022-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="02022-212">Gleichzeitiges Klingeln ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="02022-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="02022-213">In der folgenden Tabelle wird gezeigt, ob Location-Based Routing das gleichzeitige Klingeln an einem PSTN-Endpunkt von verschiedenen lync-Benutzern ermöglicht (also lync User 2, lync User 4 usw.).</span><span class="sxs-lookup"><span data-stu-id="02022-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02022-214">Gleichzeitiges Klingel Ziel</span><span class="sxs-lookup"><span data-stu-id="02022-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="02022-215">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="02022-215">Lync user 2</span></span></th>
<th><span data-ttu-id="02022-216">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="02022-216">Lync user 4</span></span></th>
<th><span data-ttu-id="02022-217">Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="02022-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02022-218">Mobiltelefon für lync-Benutzer 1 (PSTN-Endpunkt)</span><span class="sxs-lookup"><span data-stu-id="02022-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="02022-219">Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und Ausstieg über Standort 1-Gateway</span><span class="sxs-lookup"><span data-stu-id="02022-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="02022-220">Anruf weitergeleitet über die VoIP-Routing Richtlinie von Netzwerkstandort 2 und Ausgangspunkt über Standort 2-Gateway</span><span class="sxs-lookup"><span data-stu-id="02022-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="02022-221">Anrufweiterleitung über die VoIP-Richtlinie für Anrufer und Austritt über ein PSTN-Gateway, das für Location-Based Routing nicht aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="02022-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02022-222">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02022-222">See Also</span></span>


[<span data-ttu-id="02022-223">Planen von Location-Based Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02022-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

