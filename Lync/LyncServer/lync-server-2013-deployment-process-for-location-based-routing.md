---
title: 'Lync Server 2013: Bereitstellungsvorgang beim standortbasierten Routing'
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
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="75709-102">Bereitstellungsvorgang beim standortbasierten Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75709-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75709-103">_**Letztes Änderungsdatum des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="75709-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="75709-104">Dieses Thema bietet eine Übersicht über den Prozess, der bei der Konfiguration des standortbasierten Routings erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="75709-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="75709-105">Sie müssen lync Server Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie standortbasiertes Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="75709-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="75709-106">Die für standortbasiertes Routing erforderlichen Komponenten sind bereits installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75709-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="75709-107">Standortbasierter Routing Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="75709-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75709-108">Phase</span><span class="sxs-lookup"><span data-stu-id="75709-108">Phase</span></span></th>
<th><span data-ttu-id="75709-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="75709-109">Steps</span></span></th>
<th><span data-ttu-id="75709-110">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="75709-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="75709-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="75709-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-112">Bereitstellen von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="75709-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="75709-113">Konfigurieren von Trunks</span><span class="sxs-lookup"><span data-stu-id="75709-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="75709-114">Erstellen von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="75709-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="75709-115">Definieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="75709-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75709-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="75709-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="75709-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-117">CsAdministrator</span></span><br />
<span data-ttu-id="75709-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="75709-119">Bereitstellen von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="75709-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75709-120">Überprüfen Ihrer Enterprise-VoIP-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="75709-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75709-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="75709-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="75709-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-122">CsAdministrator</span></span><br />
<span data-ttu-id="75709-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75709-124">Konfigurieren von netzwerkregionen,-Websites und-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="75709-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="75709-125">Erstellen von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="75709-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="75709-126">Erstellen von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="75709-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="75709-127">Ordnet Subnetze mit Netzwerkstandorten zu</span><span class="sxs-lookup"><span data-stu-id="75709-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75709-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="75709-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="75709-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-129">CsAdministrator</span></span><br />
<span data-ttu-id="75709-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="75709-131">Informationen zu netzwerkregionen,-Websites und-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="75709-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="75709-132">Erstellen oder Ändern eines Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="75709-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="75709-133">Erstellen oder Ändern einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="75709-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="75709-134">Zuordnen eines Subnetzes zu einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="75709-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75709-135">Konfigurieren des standortbasierten Routings</span><span class="sxs-lookup"><span data-stu-id="75709-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="75709-136">Erstellen von VoIP-Routing Richtlinien</span><span class="sxs-lookup"><span data-stu-id="75709-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="75709-137">Separate trunk-Konfiguration pro trunk definieren</span><span class="sxs-lookup"><span data-stu-id="75709-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="75709-138">Ändern von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="75709-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="75709-139">Aktivieren der standortbasierten Routing Konfiguration</span><span class="sxs-lookup"><span data-stu-id="75709-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75709-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="75709-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="75709-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-141">CsAdministrator</span></span><br />
<span data-ttu-id="75709-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="75709-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="75709-143">Beispielbereitstellung</span><span class="sxs-lookup"><span data-stu-id="75709-143">Sample Deployment</span></span>

<span data-ttu-id="75709-144">Die folgende Bereitstellung dient zur Veranschaulichung der Mechanismen, die durch standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="75709-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="75709-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="75709-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="75709-146">Eingehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="75709-146">Incoming PSTN calls</span></span>

<span data-ttu-id="75709-147">Ein Administrator kann den festgelegten trunk aktivieren, um Anrufe an "Standort 1 Gateway" für standortbasiertes Routing weiterzuleiten und das "Standort 1 Gateway" zu Site 1 zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="75709-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="75709-148">Sobald die Option aktiviert ist, werden Anrufe, die über "Standort 1 Gateway" weitergeleitet werden, nur an Benutzer weitergeleitet, die sich in Standort 1 befinden.</span><span class="sxs-lookup"><span data-stu-id="75709-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="75709-149">Alle Anrufe, die über den trunk "Standort 1 Gateway" geleitet werden, der für Benutzer an einer anderen Website bestimmt ist, wie etwa Standort 2, werden blockiert, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="75709-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="75709-150">Alle eingehenden PSTN-Anrufe über "Standort 1 Gateway" dürfen nur an Endpunkte weitergeleitet werden, die sich in Standort 1 befinden.</span><span class="sxs-lookup"><span data-stu-id="75709-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="75709-151">Wenn beispielsweise "lync-Benutzer 1" zu Website 2 reist, werden alle eingehenden PSTN-Anrufe über "Standort 1 Gateway" nicht an die Endpunkte von "lync User 1" weitergeleitet, die sich in Standort 2 befinden.</span><span class="sxs-lookup"><span data-stu-id="75709-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="75709-152">Dieselbe Routingregel gilt, wenn "lync-Benutzer 1" zu einer unbekannten Netzwerk Website reist, in der der Standort des Benutzers nicht ermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="75709-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="75709-153">In der folgenden Tabelle wird die Benutzeroberfläche von "lync User 1" in diesem Kontext erläutert.</span><span class="sxs-lookup"><span data-stu-id="75709-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="75709-154">Lync User 1-Endpunkte, die sich in Network Site 1 befinden</span><span class="sxs-lookup"><span data-stu-id="75709-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="75709-155">Lync User 1-Endpunkte, die sich in Network Site 2 befinden</span><span class="sxs-lookup"><span data-stu-id="75709-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="75709-156">Lync User 1-Endpunkte, die sich auf einer unbekannten Netzwerk Website befinden</span><span class="sxs-lookup"><span data-stu-id="75709-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-157">Eingehende PSTN-Anrufe an lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="75709-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="75709-158">Anrufe werden an Endpunkte an diesem Speicherort weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="75709-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="75709-159">Anrufe werden an diesem Standort nicht an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="75709-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="75709-160">Anrufe werden an diesem Standort nicht an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="75709-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="75709-161">Ausgehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="75709-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="75709-162">Auf VoIP-Routen wird in beiden VoIP-Richtlinien verwiesen, die Benutzern direkt zugewiesen sind, und für VoIP-Routing Richtlinien, die Netzwerk Websites zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="75709-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="75709-163">Beide Richtlinien enthalten Verweise auf Routen, die verwendet werden können, um einen Anruf anders weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="75709-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="75709-164">Beispielsweise kann ein Administrator eine VoIP-Routing Richtlinie für alle Benutzer definieren, die sich auf der Netzwerk Website 1 befinden, um alle ausgehenden Anrufe über das "Standort 1 Gateway" weiterzuleiten, während die VoIP-Richtlinie einiger Benutzer eine Route für alle ausgehenden Anrufe über das "Standort-2-Gateway" definiert.</span><span class="sxs-lookup"><span data-stu-id="75709-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="75709-165">Während sich diese Benutzer auf der Netzwerk Website 1 befinden, werden Ihre ausgehenden Anrufe über das "Standort 1 Gateway" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="75709-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="75709-166">Wenn sich ein Benutzer in einer Netzwerk Website befindet, die für standortbasiertes Routing konfiguriert ist, setzt die VoIP-Routing Richtlinien Route des Netzwerkstandorts die VoIP-Richtlinien Route des Benutzers außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="75709-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="75709-167">Diese Regel eignet sich besonders für Benutzer, die temporär zu einer anderen Website wechseln.</span><span class="sxs-lookup"><span data-stu-id="75709-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="75709-168">In diesem speziellen Fall wird ein Nutzer immer ein Gateway verwenden, das lokal an seinem Standort liegt; Wenn sich "lync User 3" auf "Website 2" befindet, werden alle ausgehenden Anrufe über "Standort 2-Gateway" weitergeleitet, aber wenn er zu Site 1 reist, werden alle ausgehenden Anrufe, die Sie bei Standort 1 getätigt haben, durch "Standort 1 Gateway" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="75709-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="75709-169">In der folgenden Tabelle wird die Benutzeroberfläche von lync User 1 veranschaulicht, die einen ausgehenden Anruf von den folgenden Netzwerkstandorten aus durchführen.</span><span class="sxs-lookup"><span data-stu-id="75709-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="75709-170">Netzwerk Website 1</span><span class="sxs-lookup"><span data-stu-id="75709-170">Network site 1</span></span></th>
<th><span data-ttu-id="75709-171">Netzwerk Website 2</span><span class="sxs-lookup"><span data-stu-id="75709-171">Network site 2</span></span></th>
<th><span data-ttu-id="75709-172">Unbekannte Netzwerk Website oder für standortbasiertes Routing nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="75709-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-173">Autorisierung ausgehender Anrufe</span><span class="sxs-lookup"><span data-stu-id="75709-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="75709-174">Lync-Benutzer-1-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="75709-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="75709-175">Lync-Benutzer-1-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="75709-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="75709-176">Lync-Benutzer-1-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="75709-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75709-177">Weiterleiten von ausgehenden Anrufen</span><span class="sxs-lookup"><span data-stu-id="75709-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="75709-178">Website 1 – VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="75709-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="75709-179">Website 2 – VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="75709-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="75709-180">VoIP-Richtlinie des Benutzers und nur für Systeme, die für standortbasiertes Routing nicht aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="75709-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="75709-181">Anruf Übertragungen und Weiterleitungen</span><span class="sxs-lookup"><span data-stu-id="75709-181">Call transfers and forwards</span></span>

<span data-ttu-id="75709-182">Wenn Anrufe übertragen oder weitergeleitet werden, wird das Routing von Anrufen vom standortbasierten Routing beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="75709-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="75709-183">Die folgende Tabelle zeigt, wie lync-Benutzer 1 einen PSTN-Anruf an einen anderen lync-Benutzer übertragen oder weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="75709-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75709-184">Benutzer initiiert Anrufübertragung oder Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="75709-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="75709-185">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="75709-185">Lync user 2</span></span></th>
<th><span data-ttu-id="75709-186">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="75709-186">Lync user 4</span></span></th>
<th><span data-ttu-id="75709-187">Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="75709-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-188">Lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="75709-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="75709-189">Anrufweiterleitung oder -durchstellung ist erlaubt</span><span class="sxs-lookup"><span data-stu-id="75709-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="75709-190">Anrufweiterleitung oder -durchstellung ist nicht erlaubt</span><span class="sxs-lookup"><span data-stu-id="75709-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="75709-191">Anrufweiterleitung oder -durchstellung ist nicht erlaubt</span><span class="sxs-lookup"><span data-stu-id="75709-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="75709-192">Die folgende Tabelle zeigt, wie sich das standortbasierte Routing auf die Weiterleitung des Anrufs auswirkt, basierend auf dem Standort des lync-Benutzers, der übertragen wird (lync User 2, lync User 4 usw.) an einen PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="75709-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75709-193">Endpunkt, an den der Anruf übertragen oder weitergeleitet wird</span><span class="sxs-lookup"><span data-stu-id="75709-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="75709-194">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="75709-194">Lync user 2</span></span></th>
<th><span data-ttu-id="75709-195">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="75709-195">Lync user 4</span></span></th>
<th><span data-ttu-id="75709-196">Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="75709-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-197">Endpunkt im öffentlichen Telefonnetz</span><span class="sxs-lookup"><span data-stu-id="75709-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="75709-198">Anrufweiterleitung oder-Übertragung wird über Website 1-VoIP-Routing Richtlinie und-Ausstieg über das Website 1-Gateway weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="75709-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="75709-199">Anrufweiterleitung oder-Übertragung wird über die Website 2-VoIP-Routing Richtlinie und den Ausstieg über das Standort-2-Gateway weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="75709-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="75709-200">Anrufweiterleitung oder-Übertragung wird über die lync-Benutzer VoIP-Richtlinie und den Ausstieg über ein Gateway weitergeleitet, das für standortbasiertes Routing nicht aktiviert ist (sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="75709-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="75709-201">Paralleles Anrufen</span><span class="sxs-lookup"><span data-stu-id="75709-201">Simultaneous ringing</span></span>

<span data-ttu-id="75709-202">Sobald standortbasiertes Routing in der Beispieltopologie konfiguriert ist, werden die folgenden Interaktionen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="75709-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="75709-203">In der folgenden Tabelle wird gezeigt, ob das standortbasierte Routing das gleichzeitige Klingeln für verschiedene lync-Benutzer ermöglicht (also lync-Benutzer 2, lync-Benutzer 4 usw.).</span><span class="sxs-lookup"><span data-stu-id="75709-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75709-204">Eingehendes PSTN-Anruf Ziel</span><span class="sxs-lookup"><span data-stu-id="75709-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="75709-205">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="75709-205">Lync user 2</span></span></th>
<th><span data-ttu-id="75709-206">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="75709-206">Lync user 4</span></span></th>
<th><span data-ttu-id="75709-207">Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="75709-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-208">Lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="75709-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="75709-209">Gleichzeitiges Klingeln ist zulässig</span><span class="sxs-lookup"><span data-stu-id="75709-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="75709-210">Gleichzeitiges Klingeln ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="75709-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="75709-211">Gleichzeitiges Klingeln ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="75709-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="75709-212">In der folgenden Tabelle wird gezeigt, ob ein standortbasiertes Routing das gleichzeitige Anrufen an einen PSTN-Endpunkt von verschiedenen lync-Benutzern ermöglicht (also lync-Benutzer 2, lync-Benutzer 4 usw.).</span><span class="sxs-lookup"><span data-stu-id="75709-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75709-213">Ziel für paralleles Anrufen</span><span class="sxs-lookup"><span data-stu-id="75709-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="75709-214">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="75709-214">Lync user 2</span></span></th>
<th><span data-ttu-id="75709-215">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="75709-215">Lync user 4</span></span></th>
<th><span data-ttu-id="75709-216">Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="75709-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75709-217">Lync-Benutzer 1-Mobiltelefon (PSTN-Endpunkt)</span><span class="sxs-lookup"><span data-stu-id="75709-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="75709-218">Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und den Ausstieg über das Website 1-Gateway</span><span class="sxs-lookup"><span data-stu-id="75709-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="75709-219">Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und den Ausstieg über das Gateway des Standorts 2</span><span class="sxs-lookup"><span data-stu-id="75709-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="75709-220">Anrufweiterleitung über die VoIP-Richtlinie für Anrufer und wird über ein PSTN-Gateway auslaufen, das für standortbasiertes Routing nicht aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="75709-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75709-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75709-221">See Also</span></span>


[<span data-ttu-id="75709-222">Planung des standortbasierten Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75709-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

