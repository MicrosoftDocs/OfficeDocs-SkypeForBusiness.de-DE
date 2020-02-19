---
title: 'Lync Server 2013: Bereitstellungsprozess für standortbasiertes Routing'
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
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="ea198-102">Bereitstellungsprozess für standortbasiertes Routing in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea198-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea198-103">_**Letztes Änderungsstand des Themas:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ea198-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ea198-104">Dieses Thema bietet eine Übersicht über den Prozess, der bei der Konfiguration des standortbasierten Routings erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ea198-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="ea198-105">Sie müssen lync Server Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie das standortbasierte Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ea198-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="ea198-106">Die Komponenten, die für das standortbasierte Routing erforderlich sind, sind bereits installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ea198-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="ea198-107">Standortbasierter Routing Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="ea198-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea198-108">Phase</span><span class="sxs-lookup"><span data-stu-id="ea198-108">Phase</span></span></th>
<th><span data-ttu-id="ea198-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="ea198-109">Steps</span></span></th>
<th><span data-ttu-id="ea198-110">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="ea198-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="ea198-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ea198-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-112">Bereitstellen von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="ea198-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ea198-113">Konfigurieren von Trunks</span><span class="sxs-lookup"><span data-stu-id="ea198-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="ea198-114">Erstellen von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ea198-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="ea198-115">Definieren von VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="ea198-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ea198-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="ea198-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ea198-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-117">CsAdministrator</span></span><br />
<span data-ttu-id="ea198-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ea198-119">Bereitstellen von Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="ea198-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea198-120">Überprüfen Ihrer Enterprise-VoIP-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ea198-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea198-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="ea198-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ea198-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-122">CsAdministrator</span></span><br />
<span data-ttu-id="ea198-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea198-124">Konfigurieren von netzwerkregionen, Standorten und Subnetzen</span><span class="sxs-lookup"><span data-stu-id="ea198-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ea198-125">Erstellen von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="ea198-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="ea198-126">Erstellen von Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="ea198-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="ea198-127">Assoziierte Subnetze mit Netzwerkstandorten</span><span class="sxs-lookup"><span data-stu-id="ea198-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ea198-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="ea198-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ea198-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-129">CsAdministrator</span></span><br />
<span data-ttu-id="ea198-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ea198-131">Grundlegende Informationen zu Netzwerkregionen, Standorten und Subnetzen</span><span class="sxs-lookup"><span data-stu-id="ea198-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="ea198-132">Erstellen oder Ändern einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="ea198-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="ea198-133">Erstellen oder Ändern eines Netzwerkstandorts</span><span class="sxs-lookup"><span data-stu-id="ea198-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="ea198-134">Zuordnen eines Subnetzes zu einem Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="ea198-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea198-135">Konfigurieren des standortbasierten Routings</span><span class="sxs-lookup"><span data-stu-id="ea198-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ea198-136">Erstellen von Richtlinien für das VoIP-Routing</span><span class="sxs-lookup"><span data-stu-id="ea198-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="ea198-137">Definieren einer separaten trunkkonfiguration pro trunk</span><span class="sxs-lookup"><span data-stu-id="ea198-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="ea198-138">Ändern von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ea198-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="ea198-139">Aktivieren der standortbasierten Routing Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ea198-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ea198-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="ea198-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="ea198-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-141">CsAdministrator</span></span><br />
<span data-ttu-id="ea198-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ea198-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="ea198-143">Beispielbereitstellung</span><span class="sxs-lookup"><span data-stu-id="ea198-143">Sample Deployment</span></span>

<span data-ttu-id="ea198-144">Die folgende Bereitstellung dient zur Veranschaulichung der Mechanismen, die durch standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="ea198-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="ea198-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="ea198-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="ea198-146">Eingehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="ea198-146">Incoming PSTN calls</span></span>

<span data-ttu-id="ea198-147">Ein Administrator kann den definierten trunk so konfigurieren, dass er Anrufe an das Gateway "Standort 1" für das standortbasierte Routing weiterleitet und das "Standort 1-Gateway" mit Standort 1 verbindet.</span><span class="sxs-lookup"><span data-stu-id="ea198-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="ea198-148">Nach der Aktivierung werden Anrufe, die über das Gateway "Standort 1" weitergeleitet werden, nur an Benutzer weitergeleitet, die sich an Standort 1 befinden.</span><span class="sxs-lookup"><span data-stu-id="ea198-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="ea198-149">Alle Anrufe, die über den trunk "Standort 1-Gateway" geleitet werden, der für Benutzer an einem anderen Standort bestimmt ist, wie etwa Standort 2, werden blockiert, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="ea198-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="ea198-150">Alle eingehenden PSTN-Anrufe über "Standort 1-Gateway" dürfen nur an Endpunkte an Standort 1 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ea198-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="ea198-151">Wenn beispielsweise "lync Benutzer 1" zu Standort 2 reist, werden alle eingehenden PSTN-Anrufe über "Standort 1-Gateway" nicht an die Endpunkte von "lync User 1" an Standort 2 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="ea198-152">Dieselbe Routingregel gilt, wenn "lync Benutzer 1" zu einem unbekannten Netzwerkstandort reist, in dem der Speicherort des Benutzers nicht ermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea198-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="ea198-153">In der folgenden Tabelle wird die Benutzerfreundlichkeit von "lync User 1" in diesem Kontext erläutert.</span><span class="sxs-lookup"><span data-stu-id="ea198-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="ea198-154">Lync User 1-Endpunkte an Netzwerkstandort 1</span><span class="sxs-lookup"><span data-stu-id="ea198-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="ea198-155">Lync User 1-Endpunkte an Netzwerkstandort 2</span><span class="sxs-lookup"><span data-stu-id="ea198-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="ea198-156">Lync User 1-Endpunkte befinden sich an einem unbekannten Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="ea198-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-157">Eingehende PSTN-Anrufe an lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="ea198-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="ea198-158">Anrufe werden an diesem Speicherort an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="ea198-159">Anrufe werden an diesem Speicherort nicht an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="ea198-160">Anrufe werden an diesem Speicherort nicht an Endpunkte weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="ea198-161">Ausgehende PSTN-Anrufe</span><span class="sxs-lookup"><span data-stu-id="ea198-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="ea198-162">Auf VoIP-Routen wird in beiden VoIP-Richtlinien verwiesen, die direkt Benutzern zugewiesen sind, sowie auf VoIP-Routing Richtlinien, die Netzwerkstandorten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ea198-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="ea198-163">Beide Richtlinien enthalten Verweise auf Routen, die verwendet werden können, um einen Anruf anders weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="ea198-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="ea198-164">Beispielsweise kann ein Administrator eine VoIP-Routing Richtlinie für alle Benutzer definieren, die sich im Netzwerkstandort 1 befinden, um alle ausgehenden Anrufe über das Gateway "Standort 1" weiterzuleiten, während die VoIP-Richtlinie einiger Benutzer eine Route für alle ausgehenden Anrufe über das Gateway "Standort 2" definiert.</span><span class="sxs-lookup"><span data-stu-id="ea198-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="ea198-165">Während sich diese Benutzer im Netzwerkstandort 1 befinden, werden Ihre ausgehenden Anrufe über das Gateway "Standort 1" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="ea198-166">Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der für das standortbasierte Routing konfiguriert ist, überschreibt die Route der VoIP-Routing Richtlinie des Netzwerkstandorts die VoIP-Richtlinien Route des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ea198-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="ea198-167">Diese Regel ist besonders nützlich für Benutzer, die vorübergehend zu einer anderen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="ea198-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="ea198-168">In diesem speziellen Fall verwendet ein Benutzer immer ein Gateway, das lokal an seinem Standort ist; Wenn sich "lync User 3" unter "Standort 2" befindet, werden alle ausgehenden Anrufe über "Standort-2-Gateway" weitergeleitet, aber wenn er zu Standort 1 reist, werden alle ausgehenden Anrufe, die bei Standort 1 getätigt werden, über "Standort 1-Gateway" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="ea198-169">In der folgenden Tabelle wird die Benutzererfahrung von lync User 1, die einen ausgehenden Anruf von den folgenden Netzwerkstandorten aus durch zeigt, dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ea198-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="ea198-170">Netzwerkstandort 1</span><span class="sxs-lookup"><span data-stu-id="ea198-170">Network site 1</span></span></th>
<th><span data-ttu-id="ea198-171">Netzwerkstandort 2</span><span class="sxs-lookup"><span data-stu-id="ea198-171">Network site 2</span></span></th>
<th><span data-ttu-id="ea198-172">Unbekannter Netzwerkstandort oder nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea198-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-173">Autorisierung für ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="ea198-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="ea198-174">VoIP-Richtlinie für lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="ea198-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="ea198-175">VoIP-Richtlinie für lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="ea198-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="ea198-176">VoIP-Richtlinie für lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="ea198-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea198-177">Weiterleiten von ausgehenden Anrufen</span><span class="sxs-lookup"><span data-stu-id="ea198-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="ea198-178">VoIP-Routing Richtlinie für Standort 1</span><span class="sxs-lookup"><span data-stu-id="ea198-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ea198-179">VoIP-Routing Richtlinie für Standort 2</span><span class="sxs-lookup"><span data-stu-id="ea198-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ea198-180">VoIP-Richtlinie des Benutzers und nur für Systeme, die nicht für standortbasiertes Routing aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="ea198-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="ea198-181">Anruf Übertragungen und-Weiterleitungen</span><span class="sxs-lookup"><span data-stu-id="ea198-181">Call transfers and forwards</span></span>

<span data-ttu-id="ea198-182">Bei der Übertragung oder Weiterleitung von Anrufen wird das Routing der Anrufe von Standort basiertem Routing beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="ea198-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="ea198-183">In der folgenden Tabelle wird lync-Benutzer 1, der einen PSTN-Anruf an einen anderen lync-Benutzer übertragen oder weiterleitet, dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ea198-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea198-184">Benutzer, der die Anrufweiterleitung initiiert oder weiterleitet</span><span class="sxs-lookup"><span data-stu-id="ea198-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="ea198-185">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="ea198-185">Lync user 2</span></span></th>
<th><span data-ttu-id="ea198-186">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="ea198-186">Lync user 4</span></span></th>
<th><span data-ttu-id="ea198-187">Lync-Benutzer im Netzwerkstandort nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea198-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-188">Lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="ea198-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="ea198-189">Anrufweiterleitung oder-Übertragung ist zulässig</span><span class="sxs-lookup"><span data-stu-id="ea198-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="ea198-190">Anrufweiterleitung oder-Übertragung ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="ea198-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="ea198-191">Anrufweiterleitung oder-Übertragung ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="ea198-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="ea198-192">Die folgende Tabelle zeigt, wie sich das standortbasierte Routing auf die Weiterleitung des Anrufs auswirkt, basierend auf dem Speicherort des übertragenden lync-Benutzers (lync Benutzer 2, lync-Benutzer 4 usw.) an einen PSTN-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="ea198-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea198-193">Endpunkt, an den der Anruf übertragen oder an diese weitergeleitet wird</span><span class="sxs-lookup"><span data-stu-id="ea198-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="ea198-194">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="ea198-194">Lync user 2</span></span></th>
<th><span data-ttu-id="ea198-195">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="ea198-195">Lync user 4</span></span></th>
<th><span data-ttu-id="ea198-196">Lync-Benutzer im Netzwerkstandort nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea198-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-197">PSTN-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ea198-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ea198-198">Anrufweiterleitung oder-Übertragung wird über Standort 1-VoIP-Routing Richtlinie und Ausstieg über Standort 1-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="ea198-199">Anrufweiterleitung oder-Übertragung wird über Standort 2-VoIP-Routing Richtlinie und Ausstieg über Standort-2-Gateway weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea198-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="ea198-200">Anrufweiterleitung oder-Übertragung wird über die VoIP-Richtlinie für lync-Benutzer weitergeleitet und über ein Gateway nicht für standortbasiertes Routing aktiviert (sofern verfügbar)</span><span class="sxs-lookup"><span data-stu-id="ea198-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="ea198-201">Gleichzeitiges Klingeln</span><span class="sxs-lookup"><span data-stu-id="ea198-201">Simultaneous ringing</span></span>

<span data-ttu-id="ea198-202">Nachdem das standortbasierte Routing in der Beispieltopologie konfiguriert wurde, werden die folgenden Interaktionen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="ea198-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="ea198-203">In der folgenden Tabelle wird gezeigt, ob das standortbasierte Routing das gleichzeitige Klingeln für verschiedene lync-Benutzer ermöglicht (also lync User 2, lync User 4 usw.).</span><span class="sxs-lookup"><span data-stu-id="ea198-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea198-204">Ziel eines eingehenden PSTN-Anrufs</span><span class="sxs-lookup"><span data-stu-id="ea198-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="ea198-205">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="ea198-205">Lync user 2</span></span></th>
<th><span data-ttu-id="ea198-206">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="ea198-206">Lync user 4</span></span></th>
<th><span data-ttu-id="ea198-207">Lync-Benutzer im Netzwerkstandort nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea198-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-208">Lync-Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="ea198-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="ea198-209">Gleichzeitiges Klingeln ist zulässig</span><span class="sxs-lookup"><span data-stu-id="ea198-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="ea198-210">Gleichzeitiges Klingeln ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="ea198-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="ea198-211">Gleichzeitiges Klingeln ist nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="ea198-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="ea198-212">In der folgenden Tabelle wird veranschaulicht, ob das standortbasierte Routing das gleichzeitige Klingeln an einen PSTN-Endpunkt von verschiedenen lync-Benutzern ermöglicht (also lync User 2, lync User 4 usw.).</span><span class="sxs-lookup"><span data-stu-id="ea198-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea198-213">Gleichzeitiges Klingel Ziel</span><span class="sxs-lookup"><span data-stu-id="ea198-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="ea198-214">Lync-Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="ea198-214">Lync user 2</span></span></th>
<th><span data-ttu-id="ea198-215">Lync-Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="ea198-215">Lync user 4</span></span></th>
<th><span data-ttu-id="ea198-216">Lync-Benutzer im Netzwerkstandort nicht für standortbasiertes Routing aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea198-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea198-217">Mobiltelefon für lync-Benutzer 1 (PSTN-Endpunkt)</span><span class="sxs-lookup"><span data-stu-id="ea198-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="ea198-218">Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und Ausstieg über Standort 1-Gateway</span><span class="sxs-lookup"><span data-stu-id="ea198-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="ea198-219">Anruf weitergeleitet über die VoIP-Routing Richtlinie von Netzwerkstandort 2 und Ausgangspunkt über Standort 2-Gateway</span><span class="sxs-lookup"><span data-stu-id="ea198-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="ea198-220">Anrufweiterleitung über die VoIP-Richtlinie für Anrufer und Austritt über ein PSTN-Gateway, das nicht für standortbasiertes Routing aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="ea198-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea198-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea198-221">See Also</span></span>


[<span data-ttu-id="ea198-222">Planen des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea198-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

