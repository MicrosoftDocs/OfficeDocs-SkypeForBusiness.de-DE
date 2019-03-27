---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie speicherortbasierte Routing für die direkte Weiterleitung zu aktivieren.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886032"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="de350-103">Aktivieren des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="de350-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="de350-104">Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, Sie [Plan Location-Based Routing für das direkte Routing](location-based-routing-plan.md) gelesen und die Schritte unter [Configure Netzwerkeinstellungen für standortbasierte Routing](location-based-routing-configure-network-settings.md)abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="de350-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="de350-105">In diesem Artikel wird beschrieben, wie speicherortbasierte Routing für die direkte Weiterleitung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de350-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="de350-106">Nachdem Sie Phone System direkten Routing bereitstellen und von netzwerkregionen, Standorten und Subnetzen einrichten, können Sie standortbasierte Routing zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de350-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="de350-107">Um die Schritte in diesem Artikel ausführen zu können, benötigen Sie einige gute Kenntnisse im Umgang mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="de350-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="de350-108">Weitere Informationen finden Sie unter [Teams PowerShell (Übersicht)](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="de350-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="de350-109">Sie müssen den speicherortbasierte Routing für Folgendes aktivieren:</span><span class="sxs-lookup"><span data-stu-id="de350-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="de350-110">Nutzer</span><span class="sxs-lookup"><span data-stu-id="de350-110">Users</span></span>
- <span data-ttu-id="de350-111">Netzwerkstandorte</span><span class="sxs-lookup"><span data-stu-id="de350-111">Network sites</span></span>
- <span data-ttu-id="de350-112">Gateway-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="de350-112">Gateway configurations</span></span>
- <span data-ttu-id="de350-113">Aufrufen von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="de350-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="de350-114">Speicherortbasierte Routing für Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="de350-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="de350-115">Verwenden Sie das [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) -Cmdlet, um PSTN-Verwendungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="de350-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="de350-116">Trennen Sie mehrere Verwendungen jeder Verwendung durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="de350-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="de350-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="de350-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="de350-118">Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) zum Erstellen einer VoIP-Routingrichtlinie, um den Benutzer mit den entsprechenden PSTN-Verwendungen verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="de350-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="de350-119">Wenn Sie eine VoIP-Routingrichtlinie mit PSTN-Verwendungen zuweisen, stellen Sie sicher, dass Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="de350-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="de350-120">Verwenden von PSTN-Verwendungen, die VoIP-Routen, mit denen ein PSTN-Gateway lokalen zu der Website zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="de350-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="de350-121">Verwenden Sie die PSTN-Verwendungen, VoIP-Routen, die ein PSTN-Gateway befindet sich in einem Bereich, in dem Routing speicherortbasierte Einschränkungen nicht benötigte, verwenden zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="de350-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="de350-122">In diesem Beispiel werden zwei neue VoIP-Routingrichtlinien erstellen und PSTN-Verwendungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="de350-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="de350-123">In der folgenden Tabelle zeigt die in diesem Beispiel definierten VoIP-Routingrichtlinien zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de350-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="de350-124">VoIP-routing-Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="de350-124">Voice routing policy 1</span></span>|<span data-ttu-id="de350-125">VoIP-routing-Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="de350-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="de350-126">Online VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="de350-126">Online voice policy ID</span></span>   |<span data-ttu-id="de350-127">Delhi online VoIP-routing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="de350-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="de350-128">Hyderabad online VoIP-routing-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="de350-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="de350-129">Online PSTN-Verwendungen</span><span class="sxs-lookup"><span data-stu-id="de350-129">Online PSTN usages</span></span>  |<span data-ttu-id="de350-130">Ferngespräche</span><span class="sxs-lookup"><span data-stu-id="de350-130">Long Distance</span></span>  |<span data-ttu-id="de350-131">Long Distance, lokale, interne</span><span class="sxs-lookup"><span data-stu-id="de350-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="de350-132">Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) online VoIP-Routingrichtlinien zurückgegeben Benutzern zuordnen, die benötigen routing Einschränkungen erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="de350-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="de350-133">Speicherortbasierte Routing für Netzwerkstandorte aktivieren</span><span class="sxs-lookup"><span data-stu-id="de350-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="de350-134">Verwenden Sie das Cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) speicherortbasierte Routing aktivieren und Zuordnen von VoIP-Routingrichtlinien zurückgegeben zu Netzwerkstandorten, die routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="de350-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="de350-135">In diesem Beispiel können wir speicherortbasierte Routing für die Delhi und der Hyderabad-Website.</span><span class="sxs-lookup"><span data-stu-id="de350-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="de350-136">Die folgende Tabelle zeigt die Websites für standortbasierte Routing in diesem Beispiel wird aktiviert.</span><span class="sxs-lookup"><span data-stu-id="de350-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="de350-137">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="de350-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="de350-138">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="de350-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="de350-139">Standortname</span><span class="sxs-lookup"><span data-stu-id="de350-139">Site name</span></span>    |<span data-ttu-id="de350-140">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="de350-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="de350-141">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="de350-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="de350-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="de350-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="de350-143">True</span><span class="sxs-lookup"><span data-stu-id="de350-143">True</span></span>    |<span data-ttu-id="de350-144">True</span><span class="sxs-lookup"><span data-stu-id="de350-144">True</span></span>    |
    |<span data-ttu-id="de350-145">Subnetze</span><span class="sxs-lookup"><span data-stu-id="de350-145">Subnets</span></span>     |<span data-ttu-id="de350-146">Subnetz 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="de350-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="de350-147">Subnetz 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="de350-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="de350-148">Aktivieren Sie standortbasierte Routing für gateways</span><span class="sxs-lookup"><span data-stu-id="de350-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="de350-149">Verwenden Sie das Cmdlet " [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) " So erstellen Sie eine Gatewaykonfiguration für jeden Standort Gateway oder Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="de350-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="de350-150">Wenn mehrere Gateways mit einem System (beispielsweise Gateway oder PBX) verbunden sind, ändern Sie jedes Gateway, um Einschränkungen speicherortbasierte Routing zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de350-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="de350-151">In diesem Beispiel erstellen wir eine Gatewaykonfiguration für jedes Gateway.</span><span class="sxs-lookup"><span data-stu-id="de350-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="de350-152">Weitere Informationen finden Sie unter [Konfigurieren von direkten Routing](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="de350-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="de350-153">Verwenden Sie das Cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) speicherortbasierte Routing für Ihre-Gateways zu aktivieren, die routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="de350-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="de350-154">Aktivieren speicherortbasierte Routing zu Gateways, die Anrufe weiterleiten an PSTN-Gateways, die Anrufe an das Telefonfestnetz weiterleiten, und ordnen Sie den Netzwerkstandort das Gateway gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="de350-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="de350-155">In diesem Beispiel können wir speicherortbasierte Routing für jedes Gateway, das zum PSTN-Gateways an den Standorten Delhi und Hyderabad zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="de350-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="de350-156">Aktivieren Sie nicht speicherortbasierte Routing für Gateways, die Anrufe an das Telefonfestnetz weiterleiten nicht.</span><span class="sxs-lookup"><span data-stu-id="de350-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="de350-157">Sie haben jedoch weiterhin das Gateway auf den Netzwerkstandort zuzuordnen, in das System gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="de350-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="de350-158">Dies ist, da Routing speicherortbasierte Einschränkungen müssen erzwungen werden, die für PSTN-Anrufe erreichen von Endpunkten, die über dieses Gateway verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="de350-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="de350-159">In diesem Beispiel wird nicht speicherortbasierte Routing für jedes Gateway aktiviert, die mit PBX-Systemen auf den Websites Delhi und Hyderabad zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="de350-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="de350-160">Endpunkte mit Systemen, die Anrufe an das Telefonfestnetz (beispielsweise eine Nebenstellenanlage (PBX) weitergeleitet werden nicht verbunden werden als Endpunkte des Teams für standortbasierte Routing aktivierten Benutzern ähnliche Einschränkungen haben.</span><span class="sxs-lookup"><span data-stu-id="de350-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="de350-161">Dies bedeutet, dass diese Benutzer tätigen und Entgegennehmen von Anrufen zu und von Teams Benutzer unabhängig vom Standort des Benutzers können.</span><span class="sxs-lookup"><span data-stu-id="de350-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="de350-162">Sie können auch Anrufe tätigen und empfangen zu und von anderen Systemen, die Aufrufe an das PSTN-Netzwerk (beispielsweise einen Endpunkt zu einer anderen Nebenstellenanlage verbunden) unabhängig von den Netzwerkstandort weiterleiten nicht, die das System zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="de350-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="de350-163">Speicherortbasierte Routing Bescheide werden alle eingehenden Anrufe, ausgehende Anrufe, Call gehandelt und die anrufweiterleitung, die PSTN-Endgeräten betreffen erhoben.</span><span class="sxs-lookup"><span data-stu-id="de350-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="de350-164">Bei diesen anrufen müssen nur PSTN-Gateways verwenden, die als lokale Systeme dieser definiert sind.</span><span class="sxs-lookup"><span data-stu-id="de350-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="de350-165">Die folgende Tabelle enthält die Gateway-Konfiguration der vier Gateways in zwei verschiedenen Netzwerkstandorten: zwei mit PSTN-Gateways und zwei verbunden mit PBX-Systemen verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="de350-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="de350-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="de350-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="de350-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="de350-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="de350-168">PstnGateway:Gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="de350-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="de350-169">True</span><span class="sxs-lookup"><span data-stu-id="de350-169">True</span></span>     |   <span data-ttu-id="de350-170">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="de350-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="de350-171">PstnGateway:Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="de350-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="de350-172">True</span><span class="sxs-lookup"><span data-stu-id="de350-172">True</span></span>      |      <span data-ttu-id="de350-173">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="de350-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="de350-174">DEL PstnGateway:Gateway 3-PBX-Ressource</span><span class="sxs-lookup"><span data-stu-id="de350-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="de350-175">Falsch</span><span class="sxs-lookup"><span data-stu-id="de350-175">False</span></span>     |     <span data-ttu-id="de350-176">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="de350-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="de350-177">PstnGateway:Gateway 4 HYD-PBX-Ressource</span><span class="sxs-lookup"><span data-stu-id="de350-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="de350-178">Falsch</span><span class="sxs-lookup"><span data-stu-id="de350-178">False</span></span>     |    <span data-ttu-id="de350-179">Standort 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="de350-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="de350-180">Aktivieren Sie standortbasierte Routing für den Aufruf von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="de350-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="de350-181">Zum Erzwingen der speicherortbasierte Routing für bestimmte Benutzer einrichten der Benutzer VoIP-Richtlinie verhindert PTSN gebührenpflichtige umgehen.</span><span class="sxs-lookup"><span data-stu-id="de350-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="de350-182">Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) speicherortbasierte routing, indem Sie verhindern, dass PSTN gebührenpflichtige Umgehung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de350-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="de350-183">In diesem Beispiel wird verhindert, dass wir PSTN gebührenpflichtige umgangen Benutzer1 Richtlinien aufrufen.</span><span class="sxs-lookup"><span data-stu-id="de350-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="de350-184">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="de350-184">Related topics</span></span>
- [<span data-ttu-id="de350-185">Planen des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="de350-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="de350-186">Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="de350-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="de350-187">Terminologie für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="de350-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
