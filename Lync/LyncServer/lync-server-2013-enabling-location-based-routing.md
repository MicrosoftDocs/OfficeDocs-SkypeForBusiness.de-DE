---
title: 'Lync Server 2013: Aktivieren des Location-Based Routings'
description: 'Lync Server 2013: Aktivieren des Location-Based Routings.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557621"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3c1dd-103">Aktivieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c1dd-103">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c1dd-104">_**Letztes Änderungsstand des Themas:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="3c1dd-104">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="3c1dd-105">Nachdem Enterprise-VoIP bereitgestellt wurde und netzwerkregionen,-Standorte und-Subnetze definiert sind, können Sie Location-Based Routing aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-105">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="3c1dd-106">Für die folgenden Enterprise-VoIP-Elemente muss Location-Based Routing aktiviert sein:</span><span class="sxs-lookup"><span data-stu-id="3c1dd-106">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="3c1dd-107">Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="3c1dd-107">Network sites</span></span>

  - <span data-ttu-id="3c1dd-108">Trunk Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="3c1dd-108">Trunk configurations</span></span>

  - <span data-ttu-id="3c1dd-109">VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3c1dd-109">Voice policies</span></span>

  - <span data-ttu-id="3c1dd-110">Routing Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3c1dd-110">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="3c1dd-111">Aktivieren Location-Based Routings an Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="3c1dd-111">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="3c1dd-112">Nachdem Sie Enterprise-VoIP bereitgestellt und Netzwerkstandorte konfiguriert haben, können Sie Location-Based Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-112">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="3c1dd-113">Zunächst erstellen Sie eine VoIP-Routing Richtlinie, um dem Netzwerkstandort die entsprechenden PSTN-Verwendungen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-113">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="3c1dd-114">Wenn Sie PSTN-Verwendungen einer VoIP-Routing Richtlinie zuweisen, sollten Sie sicherstellen, dass Sie nur PSTN-Verwendungen verwenden, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für den Standort oder ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der keine Location-Based Routing Einschränkungen erforderlich sind. Verwenden Sie die lync Server Windows PowerShell-Befehl, New-csvoiceroutingpolicy "oder lync Server-Systemsteuerung, um VoIP-Routing Richtlinien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-114">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="3c1dd-115">Weitere Informationen finden Sie unter [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="3c1dd-115">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="3c1dd-116">In diesem Beispiel werden in den folgenden Tabellen-und Windows PowerShell Befehlen zwei VoIP-Routing Richtlinien und die zugehörigen in diesem Szenario definierten PSTN-Verwendungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-116">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="3c1dd-117">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="3c1dd-118">VoIP-Routing Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="3c1dd-118">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="3c1dd-119">VoIP-Routing Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="3c1dd-119">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-120">VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="3c1dd-120">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-121">VoIP-Routing Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="3c1dd-121">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-122">Hyderabad-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3c1dd-122">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c1dd-123">PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="3c1dd-123">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-124">Verwendung von Delhi, PBX del Usage, PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="3c1dd-124">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-125">Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</span><span class="sxs-lookup"><span data-stu-id="3c1dd-125">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="3c1dd-126">Konfigurieren Sie als nächstes Location-Based Routing für die entsprechenden Netzwerkstandorte, und ordnen Sie Ihnen die Richtlinien für das VoIP-Routing zu.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-126">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="3c1dd-127">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSite, um Location-Based Routing zu aktivieren und VoIP-Routing Richtlinien ihren Netzwerkstandorten zuzuordnen, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="3c1dd-128">In diesem Beispiel wird in der folgenden Tabelle Location-Based Routing für zwei verschiedene Netzwerkstandorte (Delhi und Hyderabad) veranschaulicht, die in diesem Szenario mithilfe der lync Server Windows PowerShell definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-128">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="3c1dd-129">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="3c1dd-130">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="3c1dd-131">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-132">Name der Website</span><span class="sxs-lookup"><span data-stu-id="3c1dd-132">Site Name</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-133">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-133">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-134">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-134">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c1dd-135">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="3c1dd-135">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-136">True</span><span class="sxs-lookup"><span data-stu-id="3c1dd-136">True</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-137">True</span><span class="sxs-lookup"><span data-stu-id="3c1dd-137">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-138">VoIP-Routingrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3c1dd-138">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-139">VoIP-Routing Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="3c1dd-139">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-140">Hyderabad-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3c1dd-140">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c1dd-141">Subnetze</span><span class="sxs-lookup"><span data-stu-id="3c1dd-141">Subnets</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-142">Subnetz 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-142">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-143">Subnetz 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-143">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="3c1dd-144">Location-Based Routing an Trunks aktivieren</span><span class="sxs-lookup"><span data-stu-id="3c1dd-144">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="3c1dd-145">Bevor eine trunkkonfiguration für Location-Based Routing aktiviert werden kann, müssen Sie für jeden trunk oder jeden Netzwerkstandort eine trunkkonfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-145">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="3c1dd-146">Verwenden Sie den Befehl lync Server Windows PowerShell, New-CsTrunkConfiguration, um eine trunkkonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-146">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="3c1dd-147">Wenn mehrere Trunks einem bestimmten System (also Gateway oder Nebenstellenanlage) zugeordnet sind, muss jede trunkkonfiguration so geändert werden, dass Location-Based Routing Einschränkungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-147">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="3c1dd-148">Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3c1dd-148">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="3c1dd-149">In diesem Beispiel veranschaulichen die folgenden Windows PowerShell Befehle das Erstellen einer trunkkonfiguration für jeden trunk in der in diesem Szenario definierten Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-149">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="3c1dd-150">Nachdem Sie eine trunkkonfiguration pro trunk konfiguriert haben, können Sie mit dem Befehl lync Server Windows PowerShell-CsTrunkConfiguration Location-Based Routing an Ihre Trunks aktivieren, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-150">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="3c1dd-151">Aktivieren Sie Location-Based Routing an Trunks, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie den Netzwerkstandort zu, auf dem sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-151">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="3c1dd-152">Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3c1dd-152">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="3c1dd-153">In diesem Beispiel ist Location-Based Routing für jeden trunk aktiviert, der PSTN-Gateways in Delhi und Hyderabad zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="3c1dd-153">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="3c1dd-154">Aktivieren Sie Location-Based Routing nicht für Trunks, die keine Anrufe an das PSTN weiterleiten; Sie müssen den trunk jedoch weiterhin dem Netzwerkstandort zuordnen, in dem sich das System befindet, da Location-Based Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die über diesen Trunk verbundene Endpunkte erreichen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-154">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="3c1dd-155">In diesem Beispiel ist Location-Based Routing für jeden trunk, der PBX-Systemen in Delhi und Hyderabad zugeordnet ist, nicht aktiviert:</span><span class="sxs-lookup"><span data-stu-id="3c1dd-155">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="3c1dd-156">Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (d. h. eine Nebenstellenanlage) weiterleiten, haben ähnliche Einschränkungen wie lync-Endpunkte von Benutzern, die für Location-Based Routing aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-156">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="3c1dd-157">Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von lync-Benutzern tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-157">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="3c1dd-158">Sie können auch Anrufe an und von anderen Systemen ablegen, die Anrufe nicht an das PSTN-Netzwerk weiterleiten (d. h. an einen Endpunkt, der mit einer anderen Nebenstellenanlage verbunden ist), unabhängig vom Netzwerkstandort, dem das System zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-158">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="3c1dd-159">Alle eingehenden Anrufe, ausgehende Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen Location-Based Routing-Erzwingung.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-159">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="3c1dd-160">Für solche Anrufe müssen nur PSTN-Gateways verwendet werden, die als lokal für solche Systeme definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-160">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="3c1dd-161">In der folgenden Tabelle ist die trunkkonfiguration von vier Trunks an zwei unterschiedlichen Netzwerkstandorten dargestellt: zwei mit PSTN-Gateways und zwei mit PBX-Systemen verbunden.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-161">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c1dd-162">Name</span><span class="sxs-lookup"><span data-stu-id="3c1dd-162">Name</span></span></th>
<th><span data-ttu-id="3c1dd-163">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="3c1dd-163">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="3c1dd-164">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="3c1dd-164">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-165">Wert "pstngateway: trunk 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="3c1dd-165">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-166">Richtig</span><span class="sxs-lookup"><span data-stu-id="3c1dd-166">True</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-167">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-167">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c1dd-168">Wert "pstngateway: trunk 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="3c1dd-168">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-169">Richtig</span><span class="sxs-lookup"><span data-stu-id="3c1dd-169">True</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-170">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-170">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-171">Wert "pstngateway: trunk 3 del-PBX</span><span class="sxs-lookup"><span data-stu-id="3c1dd-171">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-172">False</span><span class="sxs-lookup"><span data-stu-id="3c1dd-172">False</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-173">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-173">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c1dd-174">Wert "pstngateway: trunk 4 Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="3c1dd-174">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-175">False</span><span class="sxs-lookup"><span data-stu-id="3c1dd-175">False</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-176">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="3c1dd-176">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="3c1dd-177">Aktivieren Location-Based Weiterleitung an VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="3c1dd-177">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="3c1dd-178">Um Location-Based Routing für bestimmte Benutzer zu erzwingen, konfigurieren Sie die VoIP-Richtlinie dieser Benutzer, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-178">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="3c1dd-179">Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsVoicePolicy, um eine neue VoIP-Richtlinie oder CsVoicePolicy zu erstellen, wenn Sie eine vorhandene Richtlinie verwenden, um Location-Based Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-179">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="3c1dd-180">Weitere Informationen finden Sie unter [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="3c1dd-180">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="3c1dd-181">In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell Befehle das Aktivieren der Aktivierung der PSTN-Maut Umgehung für die in diesem Szenario definierten VoIP-Richtlinien in Delhi und Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-181">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="3c1dd-182">Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-182">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="3c1dd-183">VoIP-Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="3c1dd-183">Voice policy 1</span></span></th>
<th><span data-ttu-id="3c1dd-184">VoIP-Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="3c1dd-184">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-185">VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="3c1dd-185">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-186">VoIP-Richtlinie für Delhi</span><span class="sxs-lookup"><span data-stu-id="3c1dd-186">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-187">Hyderabad-VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="3c1dd-187">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c1dd-188">PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="3c1dd-188">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-189">Verwendung von Delhi, PBX del Usage, PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="3c1dd-189">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-190">Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</span><span class="sxs-lookup"><span data-stu-id="3c1dd-190">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c1dd-191">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="3c1dd-191">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-192">True</span><span class="sxs-lookup"><span data-stu-id="3c1dd-192">True</span></span></p></td>
<td><p><span data-ttu-id="3c1dd-193">True</span><span class="sxs-lookup"><span data-stu-id="3c1dd-193">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="3c1dd-194">Aktivieren Location-Based Routings in der Routingkonfiguration</span><span class="sxs-lookup"><span data-stu-id="3c1dd-194">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="3c1dd-195">Schließlich können Sie Location-Based Routing an Ihre Routingkonfiguration Global aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-195">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="3c1dd-196">Verwenden Sie den Befehl lync Server Windows PowerShell, New-CsRoutingConfiguration, um Location-Based Routing zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-196">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="3c1dd-197">Weitere Informationen finden Sie unter [Sets-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3c1dd-197">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c1dd-198">während Location-Based Routing über eine globale Konfiguration aktiviert werden muss, wird der Satz von angewendeten Regeln nur für die Standorte, Benutzer und Trunks erzwungen, für die er gemäß der in dieser Dokumentation angegebenen Konfiguration konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c1dd-198">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c1dd-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c1dd-199">See Also</span></span>


[<span data-ttu-id="3c1dd-200">Konfigurieren Location-Based Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c1dd-200">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

