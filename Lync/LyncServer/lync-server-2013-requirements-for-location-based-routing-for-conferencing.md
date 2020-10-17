---
title: 'Lync Server 2013: Anforderungen für das Location-Based Routing für Konferenzen'
description: 'Lync Server 2013: Anforderungen für Location-Based Routing für Konferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542521"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="1675d-103">Anforderungen für Location-Based Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1675d-103">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1675d-104">_**Letztes Änderungsstand des Themas:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="1675d-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="1675d-105">Im folgenden werden die Anforderungen für die Installation und Konfiguration der Location-Based Routing Konferenz Anwendung benötigt:</span><span class="sxs-lookup"><span data-stu-id="1675d-105">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="1675d-106">Lync Server 2013 Kumulatives Update 2 muss auf allen Servern oder Pools in der Topologie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-106">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1675d-107">Wenn auf einem lync-Server oder-Pool in Ihrer Topologie lync Server 2013 Kumulatives Update 2 oder höher nicht installiert ist, kann die Erzwingung des Location-Based Routings von lync-Besprechungen nicht gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-107">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="1675d-108">Lync Server 2013 Location-Based Routing ist eine Voraussetzung für Location-Based Routing Konferenz Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1675d-108">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="1675d-109">Weitere Informationen zum Konfigurieren von lync Server 2013 Location-Based Routing finden Sie unter [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1675d-109">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="1675d-110">Die Anforderungen für Location-Based Routing Konferenz Anwendung entsprechen den Anforderungen für lync Server 2013 Location-Based Routing.</span><span class="sxs-lookup"><span data-stu-id="1675d-110">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="1675d-111">Weitere Informationen finden Sie unter [Planung für Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1675d-111">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="1675d-112">Unterstützte Server</span><span class="sxs-lookup"><span data-stu-id="1675d-112">Supported Servers</span></span>

<span data-ttu-id="1675d-113">Für die Location-Based Routing Konferenz Anwendung muss lync Server 2013 Kumulatives Update 2 auf allen Front-End Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-113">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="1675d-114">Wenn lync Server 2013 Kumulatives Update 2 nicht auf einigen lync-Servern in Ihrer Topologie installiert ist, können Location-Based Routing Einschränkungen nicht vollständig in lync-Besprechungen und beratenden Anruf Übertragungen erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-114">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="1675d-115">In der folgenden Tabelle ist die Kombination von Serverrollen und Versionen aufgeführt, die Location-Based Routing unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1675d-115">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1675d-116">Front-End Pool Version</span><span class="sxs-lookup"><span data-stu-id="1675d-116">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="1675d-117">Vermittlungsserver Version</span><span class="sxs-lookup"><span data-stu-id="1675d-117">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="1675d-118">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="1675d-118">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1675d-119">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="1675d-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="1675d-120">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="1675d-120">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="1675d-121">Ja</span><span class="sxs-lookup"><span data-stu-id="1675d-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1675d-122">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="1675d-122">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="1675d-123">Lync Server 2013 Kumulatives Update 1</span><span class="sxs-lookup"><span data-stu-id="1675d-123">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="1675d-124">Nein</span><span class="sxs-lookup"><span data-stu-id="1675d-124">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1675d-125">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="1675d-125">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="1675d-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1675d-126">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="1675d-127">Nein</span><span class="sxs-lookup"><span data-stu-id="1675d-127">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1675d-128">Lync Server 2013 Kumulatives Update 2</span><span class="sxs-lookup"><span data-stu-id="1675d-128">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="1675d-129">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1675d-129">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1675d-130">Nein</span><span class="sxs-lookup"><span data-stu-id="1675d-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1675d-131">Lync Server 2013 Kumulatives Update 1</span><span class="sxs-lookup"><span data-stu-id="1675d-131">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="1675d-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1675d-132">Any</span></span></p></td>
<td><p><span data-ttu-id="1675d-133">Nein</span><span class="sxs-lookup"><span data-stu-id="1675d-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1675d-134">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1675d-134">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="1675d-135">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1675d-135">Any</span></span></p></td>
<td><p><span data-ttu-id="1675d-136">Nein</span><span class="sxs-lookup"><span data-stu-id="1675d-136">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1675d-137">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1675d-137">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1675d-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="1675d-138">Any</span></span></p></td>
<td><p><span data-ttu-id="1675d-139">Nein</span><span class="sxs-lookup"><span data-stu-id="1675d-139">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="1675d-140">Unterstützte Clients</span><span class="sxs-lookup"><span data-stu-id="1675d-140">Supported Clients</span></span>

<span data-ttu-id="1675d-141">Die lync-Clients, die Location-Based Routing von lync-Besprechungen unterstützen, sind dieselben Clients, die lync Server 2013 Location-Based Routing unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1675d-141">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="1675d-142">Weitere Informationen finden Sie [unter Client-und Server Unterstützung für Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1675d-142">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="1675d-143">Vermittlungsserver Anforderungen für beratende Anruf Übertragungen</span><span class="sxs-lookup"><span data-stu-id="1675d-143">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="1675d-144">Für die Location-Based Routing Konferenz Anwendung ist die Bereitstellung eigenständiger Vermittlungsserver erforderlich, um Location-Based Routing Einschränkungen für Anrufe in beratenden anrufen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1675d-144">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="1675d-145">Um Location-Based Routing von beratenden Anruf Übertragungen durchzusetzen, muss das Vermittlungsserver nur einem Vermittlungsserver Peer (also PBX, SIP-Gateway usw.) in netzwerkregionen zugeordnet sein, in dem Location-Based Routing erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1675d-145">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="1675d-146">Wenn weitere Vermittlungsserver Peers in derselben netzwerkregion bereitgestellt werden, muss der Vermittlungsserver Peer einem anderen Vermittlungsserver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-146">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="1675d-147">Diese Anforderung wird wie folgt beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1675d-147">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="1675d-148">Einzelne Vermittlungsserver pro mehrere Vermittlungsserver Peers wenn eine Anrufweiterleitung an einen Vermittlungsserver Peer über eine Vermittlungsserver geroutet wird, die mit mehreren SIP-Trunks für mehrere Peers konfiguriert ist (PBX und Gateways), wird die Anrufweiterleitung blockiert, um eine PSTN-Maut Umgehung zu verhindern, wenn die Anrufweiterleitung über einige SIP-Trunks zulässig ist, aber über andere SIP-Trunks nicht erlaubt ist.</span><span class="sxs-lookup"><span data-stu-id="1675d-148">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="1675d-149">Wenn beispielsweise ein einzelnes Vermittlungsserver ein PSTN-Gateway Vermittlungsserver Peer und eine Nebenstellenanlage Vermittlungsserver Peer bedient, wird das folgende Verhalten beobachtet:</span><span class="sxs-lookup"><span data-stu-id="1675d-149">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="1675d-150">Wenn ein lync-Benutzer von einer bestimmten Website (dh Standort 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1675d-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="1675d-151">Wenn ein lync-Benutzer von einer bestimmten Website (also Standort 1) versucht, einen Anruf mit einem Nebenstellen Endgerät am selben Standort (Standort 1) an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, auch wenn er nicht bei potenziellen PSTN-Maut Umgehungen auftritt.</span><span class="sxs-lookup"><span data-stu-id="1675d-151">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="1675d-152">Separate Vermittlungsserver pro Vermittlungsserver Peer</span><span class="sxs-lookup"><span data-stu-id="1675d-152">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="1675d-153">Wenn eine beratende Übertragung an einen Vermittlungsserver Peer gerichtet ist, wird die beratende Übertragung anhand des einzelnen Vermittlungsserver Peers ausgewertet, der von der Vermittlungsserver gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="1675d-153">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="1675d-154">Der Anruf wird nicht zugelassen oder darf aufgrund seines Potenzials in Verbindung mit der PSTN-Maut Umgehung ungeachtet aller anderen Vermittlungsserver-Peers am Standort entstehen, die von separaten Vermittlungsservern gewartet werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-154">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="1675d-155">Beispielsweise wird im Fall eines separaten Vermittlungs Servers, der ein PSTN-Gateway Vermittlungsserver Peer und einer Nebenstellenanlage Vermittlungsserver Peers bedient, das folgende Verhalten beobachtet:</span><span class="sxs-lookup"><span data-stu-id="1675d-155">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="1675d-156">Wenn ein lync-Benutzer von einer bestimmten Website (dh Standort 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf nicht zugelassen, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1675d-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="1675d-157">Wenn ein lync-Benutzer von einer bestimmten Website (also Standort 1) versucht, einen Anruf mit einem Nebenstellen Endgerät am selben Standort (Standort 1) an einen lync-Benutzer von einem anderen Standort (also Standort 2) über eine beratende Übertragung zu übertragen, wird der Anruf zugelassen, da er nicht bei potenziellen PSTN-Maut Umgehungen anfallen kann.</span><span class="sxs-lookup"><span data-stu-id="1675d-157">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="1675d-158">Von der Location-Based Routing Konferenz Anwendung nicht unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="1675d-158">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="1675d-159">Die folgenden Funktionen werden von der Location-Based Routing Konferenz Anwendung nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1675d-159">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="1675d-160">Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="1675d-160">Dial-in conferencing.</span></span> <span data-ttu-id="1675d-161">Location-Based Routing kann nicht für Einwahlkonferenzen erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="1675d-161">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="1675d-162">Alle Einwahl Anforderungen für eine bestimmte Konferenz werden nicht durch Location-Based Routing eingeschränkt, auch wenn es sich bei dem Konferenzorganisator um einen lync-Benutzer handelt, der für Location-Based Routing aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1675d-162">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="1675d-163">Es wird empfohlen, keine Konferenz Zugriffsnummern in Regionen zur Verfügung zu stellen, in denen Location-Based Routing Einschränkungen erzwungen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1675d-163">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

