---
title: 'Lync Server 2013: Aktivieren des standortbasierten Routings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="a2b34-102">Aktivieren des standortbasierten Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b34-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2b34-103">_**Letztes Änderungsdatum des Themas:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="a2b34-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="a2b34-104">Nachdem Enterprise-VoIP bereitgestellt und netzwerkregionen,-Websites und-Subnetze definiert sind, können Sie standortbasiertes Routing aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2b34-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="a2b34-105">Standortbasiertes Routing muss für die folgenden Enterprise-VoIP-Elemente aktiviert sein:</span><span class="sxs-lookup"><span data-stu-id="a2b34-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="a2b34-106">Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="a2b34-106">Network sites</span></span>

  - <span data-ttu-id="a2b34-107">Trunk-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a2b34-107">Trunk configurations</span></span>

  - <span data-ttu-id="a2b34-108">VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a2b34-108">Voice policies</span></span>

  - <span data-ttu-id="a2b34-109">Routing Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a2b34-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="a2b34-110">Aktivieren von Standort basiertem Routing auf Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="a2b34-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="a2b34-111">Nachdem Sie Enterprise-VoIP und konfigurierte Netzwerk Websites bereitgestellt haben, können Sie das standortbasierte Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a2b34-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="a2b34-112">Zuerst erstellen Sie eine VoIP-Routing Richtlinie, um die Netzwerk Website mit den entsprechenden PSTN-Nutzungen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="a2b34-113">Stellen Sie beim Zuweisen von PSTN-Nutzungen zu einer VoIP-Routing Richtlinie sicher, dass nur PSTN-Nutzungen verwendet werden, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website oder ein PSTN-Gateway verwenden, das sich in einem Bereich befindet, in dem standortbasierte Routing Einschränkungen nicht erforderlich sind. Verwenden Sie den lync Server Windows PowerShell-Befehl, die CsVoiceRoutingPolicy-oder lync Server-Systemsteuerung, um VoIP-Routing Richtlinien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="a2b34-114">Weitere Informationen finden Sie unter [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="a2b34-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="a2b34-115">In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell-Befehle zwei VoIP-Routing Richtlinien und die zugehörigen PSTN-Nutzungen, die in diesem Szenario definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a2b34-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="a2b34-116">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2b34-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="a2b34-117">VoIP-Routing Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="a2b34-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="a2b34-118">VoIP-Routing Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="a2b34-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-119">VoIP-Richtlinienkennung</span><span class="sxs-lookup"><span data-stu-id="a2b34-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="a2b34-120">Delhi-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b34-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a2b34-121">Hyderabad-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b34-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b34-122">PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="a2b34-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="a2b34-123">Nutzung von Delhi, Nutzung von Telefonanlagen, Telefonanlagen Hyd</span><span class="sxs-lookup"><span data-stu-id="a2b34-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="a2b34-124">Hyderabad-Nutzung, Nutzung von Telefonanlagen Hyd, Telefonanlagen Nutzung</span><span class="sxs-lookup"><span data-stu-id="a2b34-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="a2b34-125">Konfigurieren Sie als nächstes standortbasiertes Routing für die entsprechenden Netzwerk Websites, und ordnen Sie Ihre VoIP-Routing Richtlinien zu.</span><span class="sxs-lookup"><span data-stu-id="a2b34-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="a2b34-126">Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsNetworkSite, um standortbasiertes Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="a2b34-127">In diesem Beispiel wird in der folgenden Tabelle die standortbasierte Weiterleitung für zwei verschiedene Netzwerkstandorte (Delhi und Hyderabad) veranschaulicht, die in diesem Szenario mithilfe der lync Server Windows PowerShell definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a2b34-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="a2b34-128">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2b34-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="a2b34-129">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="a2b34-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="a2b34-130">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a2b34-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-131">Websitename</span><span class="sxs-lookup"><span data-stu-id="a2b34-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="a2b34-132">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="a2b34-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a2b34-133">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a2b34-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b34-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="a2b34-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="a2b34-135">True</span><span class="sxs-lookup"><span data-stu-id="a2b34-135">True</span></span></p></td>
<td><p><span data-ttu-id="a2b34-136">True</span><span class="sxs-lookup"><span data-stu-id="a2b34-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-137">VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b34-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a2b34-138">Delhi-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b34-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="a2b34-139">Hyderabad-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b34-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b34-140">Subnetze</span><span class="sxs-lookup"><span data-stu-id="a2b34-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="a2b34-141">Subnetz 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="a2b34-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a2b34-142">Subnetz 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a2b34-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="a2b34-143">Aktivieren von Standort basiertem Routing zu Trunks</span><span class="sxs-lookup"><span data-stu-id="a2b34-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="a2b34-144">Bevor eine trunk-Konfiguration für standortbasiertes Routing aktiviert werden kann, müssen Sie für jeden trunk oder jede Netzwerk Website eine trunk-Konfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="a2b34-145">Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsTrunkConfiguration, um eine trunk-Konfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="a2b34-146">Wenn mehrere Trunks einem bestimmten System (also Gateway oder PBX) zugeordnet sind, muss jede trunk-Konfiguration so geändert werden, dass standortbasierte Routing Einschränkungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a2b34-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="a2b34-147">Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a2b34-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="a2b34-148">In diesem Beispiel veranschaulichen die folgenden Windows PowerShell-Befehle das Erstellen einer trunk-Konfiguration für jeden trunk in der Bereitstellung, die in diesem Szenario definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a2b34-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="a2b34-149">Nachdem eine trunk-Konfiguration pro trunk konfiguriert wurde, können Sie den lync Server-Windows PowerShell-Befehl, CsTrunkConfiguration, verwenden, um standortbasiertes Routing für Ihre Trunks zu aktivieren, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="a2b34-150">Aktivieren Sie das standortbasierte Routing für Trunks, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="a2b34-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="a2b34-151">Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a2b34-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="a2b34-152">In diesem Beispiel wird für jeden trunk, der PSTN-Gateways in Delhi und Hyderabad zugeordnet ist, ein standortbasiertes Routing aktiviert:</span><span class="sxs-lookup"><span data-stu-id="a2b34-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="a2b34-153">Aktivieren Sie das standortbasierte Routing nicht für Trunks, die keine Anrufe an das PSTN weiterleiten. Sie müssen den trunk jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet, da standortbasierte Routing Einschränkungen für PSTN-Anrufe, die über diesen Trunk verbunden sind, erzwungen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="a2b34-154">Für dieses Beispiel ist standortbasiertes Routing für jeden trunk, der PBX-Systemen in Delhi und Hyderabad zugeordnet ist, nicht aktiviert:</span><span class="sxs-lookup"><span data-stu-id="a2b34-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="a2b34-155">Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (also eine Telefonanlage) weiterleiten, weisen ähnliche Einschränkungen wie lync-Endpunkte von Benutzern auf, die für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a2b34-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="a2b34-156">Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von lync-Benutzern tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="a2b34-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="a2b34-157">Sie können auch Anrufe von und zu anderen Systemen tätigen, die keine Anrufe an das PSTN-Netzwerk (also einen mit einer anderen Telefonanlage verbundenen Endpunkt) weiterleiten, und zwar unabhängig von der Netzwerk Website, der das System zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a2b34-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="a2b34-158">Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen standortbasierten Routing-Erzwingungen.</span><span class="sxs-lookup"><span data-stu-id="a2b34-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="a2b34-159">Bei solchen anrufen müssen nur PSTN-Gateways verwendet werden, die für solche Systeme als lokal definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a2b34-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="a2b34-160">In der folgenden Tabelle wird die trunk-Konfiguration von vier Trunks auf zwei verschiedenen Netzwerkstandorten veranschaulicht: zwei mit PSTN-Gateways verbunden und zwei mit PBX-Systemen verbunden.</span><span class="sxs-lookup"><span data-stu-id="a2b34-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2b34-161">Name</span><span class="sxs-lookup"><span data-stu-id="a2b34-161">Name</span></span></th>
<th><span data-ttu-id="a2b34-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="a2b34-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="a2b34-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="a2b34-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-164">PstnGateway: trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="a2b34-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="a2b34-165">True</span><span class="sxs-lookup"><span data-stu-id="a2b34-165">True</span></span></p></td>
<td><p><span data-ttu-id="a2b34-166">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="a2b34-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b34-167">PstnGateway: trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="a2b34-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="a2b34-168">True</span><span class="sxs-lookup"><span data-stu-id="a2b34-168">True</span></span></p></td>
<td><p><span data-ttu-id="a2b34-169">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a2b34-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-170">PstnGateway: trunk 3 del-PBX</span><span class="sxs-lookup"><span data-stu-id="a2b34-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="a2b34-171">Falsch</span><span class="sxs-lookup"><span data-stu-id="a2b34-171">False</span></span></p></td>
<td><p><span data-ttu-id="a2b34-172">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="a2b34-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b34-173">PstnGateway: trunk 4 Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="a2b34-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="a2b34-174">Falsch</span><span class="sxs-lookup"><span data-stu-id="a2b34-174">False</span></span></p></td>
<td><p><span data-ttu-id="a2b34-175">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a2b34-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="a2b34-176">Aktivieren von Standort basiertem Routing zu VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a2b34-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="a2b34-177">Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, konfigurieren Sie die VoIP-Richtlinie dieser Benutzer, um die PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="a2b34-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="a2b34-178">Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsVoicePolicy, zum Erstellen einer neuen VoIP-Richtlinie oder eines festgelegten CsVoicePolicy, wenn Sie eine vorhandene Richtlinie verwenden, um standortbasiertes Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.</span><span class="sxs-lookup"><span data-stu-id="a2b34-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="a2b34-179">Weitere Informationen finden Sie unter [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="a2b34-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="a2b34-180">In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell-Befehle die Verhinderung von PSTN-Maut Umgehung für die in diesem Szenario definierten VoIP-Richtlinien in Delhi und Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="a2b34-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="a2b34-181">Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2b34-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="a2b34-182">VoIP-Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="a2b34-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="a2b34-183">VoIP-Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="a2b34-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-184">VoIP-Richtlinienkennung</span><span class="sxs-lookup"><span data-stu-id="a2b34-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="a2b34-185">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="a2b34-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="a2b34-186">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a2b34-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2b34-187">PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="a2b34-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="a2b34-188">Nutzung von Delhi, Nutzung von Telefonanlagen, Telefonanlagen Hyd</span><span class="sxs-lookup"><span data-stu-id="a2b34-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="a2b34-189">Hyderabad-Nutzung, Nutzung von Telefonanlagen Hyd, Telefonanlagen Nutzung</span><span class="sxs-lookup"><span data-stu-id="a2b34-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2b34-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="a2b34-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="a2b34-191">True</span><span class="sxs-lookup"><span data-stu-id="a2b34-191">True</span></span></p></td>
<td><p><span data-ttu-id="a2b34-192">True</span><span class="sxs-lookup"><span data-stu-id="a2b34-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="a2b34-193">Aktivieren des standortbasierten Routings in der Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a2b34-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="a2b34-194">Schließlich können Sie auf globaler Ebene standortbasiertes Routing für Ihre Routingkonfiguration aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2b34-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="a2b34-195">Verwenden Sie den Windows PowerShell-Befehl von lync Server, New-CsRoutingConfiguration, um standortbasiertes Routing zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2b34-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="a2b34-196">Weitere Informationen finden Sie unter [Satz-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a2b34-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2b34-197">während standortbasiertes Routing über eine globale Konfiguration aktiviert werden muss, wird die anzuwendende Regel nur für die Websites, Benutzer und Trunks erzwungen, für die Sie konfiguriert wurde, wie in dieser Dokumentation angegeben.</span><span class="sxs-lookup"><span data-stu-id="a2b34-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2b34-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2b34-198">See Also</span></span>


[<span data-ttu-id="a2b34-199">Konfigurieren von standortbasiertem Routing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b34-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

