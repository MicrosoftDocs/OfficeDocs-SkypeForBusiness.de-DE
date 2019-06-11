---
title: 'Lync Server 2013: Anforderungen für standortbasiertes Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 925b71497012d7e6ed9c19042a079a7b30630c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="3474f-102">Voraussetzungen für standortbasiertes Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3474f-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3474f-103">_**Letztes Änderungsdatum des Themas:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="3474f-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="3474f-104">Im folgenden werden die Anforderungen für die Installation und Konfiguration der standortbasierten Routing Konferenz Anwendung benötigt:</span><span class="sxs-lookup"><span data-stu-id="3474f-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="3474f-105">Das kumulative Update 2 von lync Server 2013 muss auf allen Servern oder Pools in Ihrer Topologie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3474f-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3474f-106">Wenn auf einem lync-Server oder-Pool in Ihrer Topologie lync Server 2013 Kumulatives Update 2 oder höher nicht installiert ist, kann die Erzwingung des standortbasierten Routings von lync-Besprechungen nicht garantiert werden.</span><span class="sxs-lookup"><span data-stu-id="3474f-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="3474f-107">Das standortbasierte Routing von lync Server 2013 ist eine Voraussetzung für eine standortbasierte Routing Konferenz Anwendung.</span><span class="sxs-lookup"><span data-stu-id="3474f-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="3474f-108">Weitere Informationen zum Konfigurieren des standortbasierten Routings von lync Server 2013 finden Sie unter [Konfigurieren des Standort](lync-server-2013-configuring-location-based-routing.md)basierten Routings.</span><span class="sxs-lookup"><span data-stu-id="3474f-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="3474f-109">Die Anforderungen einer standortbasierten Routing Konferenz Anwendung entsprechen den Anforderungen für das standortbasierte Routing von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3474f-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="3474f-110">Weitere Informationen finden Sie unter [Planung für standortbasiertes Routing](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3474f-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="3474f-111">Unterstützte Server</span><span class="sxs-lookup"><span data-stu-id="3474f-111">Supported Servers</span></span>

<span data-ttu-id="3474f-112">Für die standortbasierte Routing Konferenz Anwendung muss lync Server 2013 Kumulatives Update 2 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3474f-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="3474f-113">Wenn das kumulative Update 2 von lync Server 2013 auf einigen lync-Servern in Ihrer Topologie nicht installiert ist, können standortbasierte Routing Einschränkungen in lync-Besprechungen und beratenden Anruf Übertragungen nicht vollständig erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="3474f-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="3474f-114">In der folgenden Tabelle ist die Kombination aus Serverrollen und Versionen aufgeführt, die standortbasiertes Routing unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3474f-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3474f-115">Version des Front-End-Pools</span><span class="sxs-lookup"><span data-stu-id="3474f-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="3474f-116">Mediation Server-Version</span><span class="sxs-lookup"><span data-stu-id="3474f-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="3474f-117">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="3474f-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3474f-118">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="3474f-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="3474f-119">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="3474f-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="3474f-120">Ja</span><span class="sxs-lookup"><span data-stu-id="3474f-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3474f-121">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="3474f-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="3474f-122">Lync Server 2013 Kumulatives Update 1</span><span class="sxs-lookup"><span data-stu-id="3474f-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="3474f-123">Nein</span><span class="sxs-lookup"><span data-stu-id="3474f-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3474f-124">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="3474f-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="3474f-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3474f-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="3474f-126">Nein</span><span class="sxs-lookup"><span data-stu-id="3474f-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3474f-127">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="3474f-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="3474f-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3474f-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3474f-129">Nein</span><span class="sxs-lookup"><span data-stu-id="3474f-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3474f-130">Lync Server 2013 Kumulatives Update 1</span><span class="sxs-lookup"><span data-stu-id="3474f-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="3474f-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="3474f-131">Any</span></span></p></td>
<td><p><span data-ttu-id="3474f-132">Nein</span><span class="sxs-lookup"><span data-stu-id="3474f-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3474f-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3474f-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="3474f-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="3474f-134">Any</span></span></p></td>
<td><p><span data-ttu-id="3474f-135">Nein</span><span class="sxs-lookup"><span data-stu-id="3474f-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3474f-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3474f-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="3474f-137">Beliebig</span><span class="sxs-lookup"><span data-stu-id="3474f-137">Any</span></span></p></td>
<td><p><span data-ttu-id="3474f-138">Nein</span><span class="sxs-lookup"><span data-stu-id="3474f-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="3474f-139">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="3474f-139">Supported Clients</span></span>

<span data-ttu-id="3474f-140">Die lync-Clients, die das standortbasierte Routing von lync-Besprechungen unterstützen, sind dieselben Clients, die das standortbasierte Routing von lync Server 2013 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3474f-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="3474f-141">Weitere Informationen finden Sie [unter Client-und Server Unterstützung für standortbasiertes Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3474f-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="3474f-142">Vermittlungs Server Anforderungen für beratende Anruf Übertragungen</span><span class="sxs-lookup"><span data-stu-id="3474f-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="3474f-143">Für die standortbasierte Routing Konferenz Anwendung müssen eigenständige Vermittlungsserver bereitgestellt werden, um standortbasierte Routing Einschränkungen bei Beratenden Anruf Übertragungen durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3474f-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="3474f-144">Um die standortbasierte Weiterleitung von beratenden Anruf Übertragungen zu erzwingen, muss der Vermittlungsserver nur einem Vermittlungsserver-Peer (also einer Telefonanlage, einem SIP-Gateway usw.) in netzwerkregionen zugeordnet sein, in denen ein standortbasiertes Routing erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3474f-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="3474f-145">Wenn weitere Vermittlungsserver-Peers im gleichen Netzwerkbereich bereitgestellt werden, muss der Vermittlungsserver-Peer einem anderen Vermittlungsserver zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="3474f-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="3474f-146">Diese Anforderung wird wie folgt erläutert:</span><span class="sxs-lookup"><span data-stu-id="3474f-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="3474f-147">Einzelner Vermittlungsserver pro mehrere Vermittlungsserver-Peers wenn eine beratende Anrufübertragung an einen Vermittlungsserver-Peer über einen Vermittlungsserver weitergeleitet wird, der mit mehreren SIP-Stämmen für mehrere Peers (also PBX-Anlagen und Gateways) konfiguriert ist, werden die beratenden die Anrufübertragung wird blockiert, um eine PSTN-Maut Umgehung zu verhindern, wenn die Anrufumleitung über einige SIP-Stämme zugelassen, aber über andere SIP-Stämme nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="3474f-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="3474f-148">Wenn beispielsweise ein einzelner Vermittlungsserver einen Vermittlungsserver-Peer des PSTN-Gateways und einen PBX-Vermittlungsserver-Peer bedient, wird das folgende Verhalten beobachtet:</span><span class="sxs-lookup"><span data-stu-id="3474f-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="3474f-149">Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um die PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="3474f-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="3474f-150">Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PBX-Endpunkt am gleichen Standort (Standort 1) an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, auch wenn er nicht in potenziellem PSTN Tol anfällt. l umgeht.</span><span class="sxs-lookup"><span data-stu-id="3474f-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="3474f-151">Separate Vermittlungsserver pro Vermittlungsserver-Peer</span><span class="sxs-lookup"><span data-stu-id="3474f-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="3474f-152">Wenn eine beratende Übertragung auf einen Vermittlungsserver-Peer ausgerichtet ist, wird die beratende Übertragung mit dem einzelnen Mediation Server-Peer bewertet, der vom Vermittlungsserver gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="3474f-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="3474f-153">Der Anruf wird aufgrund seines Potenzials, in der PSTN-Maut Umgehung zu entstehen, ungeachtet aller anderen Vermittlungsserver-Peers in der Website, die von separaten Vermittlungsservern gewartet werden, nicht zugelassen oder zulässig.</span><span class="sxs-lookup"><span data-stu-id="3474f-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="3474f-154">Bei einem separaten Vermittlungsserver, der einen Vermittlungsserver-Peer des PSTN-Gateways und einen PBX-Vermittlungsserver-Peer bedient, wird beispielsweise folgendes Verhalten beobachtet:</span><span class="sxs-lookup"><span data-stu-id="3474f-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="3474f-155">Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um die PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="3474f-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="3474f-156">Wenn ein lync-Benutzer von einer bestimmten Website (also Website 1) versucht, einen Anruf mit einem PBX-Endpunkt am gleichen Standort (Standort 1) an einen lync-Benutzer von einer anderen Website (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf zugelassen, da er nicht in potenzielle PSTN-Maut Umgehung fällt. Ing.</span><span class="sxs-lookup"><span data-stu-id="3474f-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="3474f-157">Funktionen, die von der standortbasierten Routing Konferenz Anwendung nicht unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="3474f-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="3474f-158">Die folgenden Funktionen werden von der standortbasierten Routing Konferenz Anwendung nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="3474f-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="3474f-159">Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="3474f-159">Dial-in conferencing.</span></span> <span data-ttu-id="3474f-160">Standortbasiertes Routing kann für Einwahlkonferenzen nicht erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="3474f-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="3474f-161">Jede Einwahl Anforderung an eine bestimmte Konferenz wird nicht durch standortbasiertes Routing eingeschränkt, auch wenn es sich bei dem Konferenzorganisator um einen lync-Benutzer handelt, der für standortbasiertes Routing aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3474f-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="3474f-162">Es wird empfohlen, keine Konferenz Zugriffsnummern in Regionen bereitzustellen, in denen standortbasierte Routing Einschränkungen erzwungen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3474f-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

