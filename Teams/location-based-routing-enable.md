---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie standortbasiertes Routing für direktes Routing aktivieren.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a4646ba212c9e654ec06fca2fdd107b2671c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245128"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="b0da0-103">Aktivieren des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="b0da0-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="b0da0-104">Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, dass Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md) gelesen haben, und führen Sie die Schritte unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md)aus.</span><span class="sxs-lookup"><span data-stu-id="b0da0-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="b0da0-105">In diesem Artikel wird beschrieben, wie standortbasiertes Routing für das direkte Routing aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b0da0-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="b0da0-106">Nachdem Sie das direkte Routing für das Telefon System bereitgestellt und netzwerkregionen,-Standorte und-Subnetze eingerichtet haben, können Sie das standortbasierte Routing aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b0da0-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="b0da0-107">Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b0da0-108">Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b0da0-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="b0da0-109">Sie müssen standortbasiertes Routing für Folgendes aktivieren:</span><span class="sxs-lookup"><span data-stu-id="b0da0-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="b0da0-110">Nutzer</span><span class="sxs-lookup"><span data-stu-id="b0da0-110">Users</span></span>
- <span data-ttu-id="b0da0-111">Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="b0da0-111">Network sites</span></span>
- <span data-ttu-id="b0da0-112">Gateway-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="b0da0-112">Gateway configurations</span></span>
- <span data-ttu-id="b0da0-113">Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b0da0-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="b0da0-114">Aktivieren des standortbasierten Routings für Benutzer</span><span class="sxs-lookup"><span data-stu-id="b0da0-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="b0da0-115">Verwenden Sie das Cmdlet " [Satz-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) ", um die PSTN-Verwendung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="b0da0-116">Für mehrere Verwendungen trennen Sie jede Verwendung durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="b0da0-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="b0da0-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b0da0-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="b0da0-118">Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) , um eine VoIP-Routing Richtlinie zu erstellen, um den Benutzer mit den entsprechenden PSTN-Verwendungen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="b0da0-119">Wenn Sie einer VoIP-Routing Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="b0da0-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="b0da0-120">Verwenden von PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden</span><span class="sxs-lookup"><span data-stu-id="b0da0-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="b0da0-121">Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b0da0-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="b0da0-122">In diesem Beispiel erstellen wir zwei neue VoIP-Routing Richtlinien und weisen Ihnen PSTN-Nutzungen zu.</span><span class="sxs-lookup"><span data-stu-id="b0da0-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="b0da0-123">In der folgenden Tabelle sind die in diesem Beispiel definierten VoIP-Routing Richtlinien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0da0-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="b0da0-124">VoIP-Routing Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="b0da0-124">Voice routing policy 1</span></span>|<span data-ttu-id="b0da0-125">VoIP-Routing Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="b0da0-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="b0da0-126">Online-VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="b0da0-126">Online voice policy ID</span></span>   |<span data-ttu-id="b0da0-127">Delhi Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="b0da0-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="b0da0-128">Hyderabad Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="b0da0-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="b0da0-129">Online PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="b0da0-129">Online PSTN usages</span></span>  |<span data-ttu-id="b0da0-130">Ferngespräche</span><span class="sxs-lookup"><span data-stu-id="b0da0-130">Long Distance</span></span>  |<span data-ttu-id="b0da0-131">Fern-, Orts-, binnen-und fern-</span><span class="sxs-lookup"><span data-stu-id="b0da0-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="b0da0-132">Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) , um Benutzern, die Routing Einschränkungen erfordern, das Erzwingen von Online-VoIP-Routing Richtlinien zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="b0da0-133">Aktivieren des standortbasierten Routings für Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="b0da0-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="b0da0-134">Verwenden Sie das Cmdlet " [festlegen-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) ", um standortbasiertes Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="b0da0-135">In diesem Beispiel wird standortbasiertes Routing für die Delhi-Website und die Hyderabad-Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b0da0-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="b0da0-136">In der folgenden Tabelle sind die Websites aufgeführt, die in diesem Beispiel für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="b0da0-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="b0da0-137">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b0da0-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="b0da0-138">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b0da0-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="b0da0-139">Standortname</span><span class="sxs-lookup"><span data-stu-id="b0da0-139">Site name</span></span>    |<span data-ttu-id="b0da0-140">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b0da0-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="b0da0-141">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b0da0-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="b0da0-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="b0da0-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="b0da0-143">True</span><span class="sxs-lookup"><span data-stu-id="b0da0-143">True</span></span>    |<span data-ttu-id="b0da0-144">True</span><span class="sxs-lookup"><span data-stu-id="b0da0-144">True</span></span>    |
    |<span data-ttu-id="b0da0-145">Subnetze</span><span class="sxs-lookup"><span data-stu-id="b0da0-145">Subnets</span></span>     |<span data-ttu-id="b0da0-146">Subnetz 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b0da0-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="b0da0-147">Subnetz 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b0da0-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="b0da0-148">Aktivieren des standortbasierten Routings für Gateways</span><span class="sxs-lookup"><span data-stu-id="b0da0-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="b0da0-149">Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) , um eine Gateway-Konfiguration für jede Gateway-oder Netzwerk Website zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="b0da0-150">Wenn einem System mehrere Gateways zugeordnet sind (beispielsweise Gateway oder Telefonanlage), ändern Sie die einzelnen Gateways, um standortbasierte Routing Einschränkungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="b0da0-151">In diesem Beispiel erstellen wir für jedes Gateway eine Gateway-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b0da0-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="b0da0-152">Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b0da0-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="b0da0-153">Verwenden Sie das Cmdlet " [festlegen-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) ", um standortbasiertes Routing für Ihre Gateways zu aktivieren, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="b0da0-154">Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="b0da0-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="b0da0-155">In diesem Beispiel aktivieren wir standortbasiertes Routing für jedes Gateway, das PSTN-Gateways in den Websites Delhi und Hyderabad zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b0da0-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="b0da0-156">Aktivieren Sie das standortbasierte Routing nicht für Gateways, die keine Anrufe an das PSTN weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b0da0-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="b0da0-157">Sie müssen das Gateway jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet.</span><span class="sxs-lookup"><span data-stu-id="b0da0-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="b0da0-158">Dies liegt daran, dass standortbasierte Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b0da0-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="b0da0-159">In diesem Beispiel ist die standortbasierte Weiterleitung für jedes Gateway, das PBX-Systemen in den Websites Delhi und Hyderabad zugeordnet ist, nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b0da0-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="b0da0-160">Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (beispielsweise eine Telefonanlage) weiterleiten, weisen ähnliche Einschränkungen wie Endpunkte von Team Benutzern auf, die für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="b0da0-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="b0da0-161">Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von Teams-Benutzern tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="b0da0-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="b0da0-162">Sie können auch Anrufe von und zu anderen Systemen tätigen und empfangen, die keine Anrufe an das PSTN-Netzwerk weiterleiten (beispielsweise einen Endpunkt, der mit einer anderen Telefonanlage verbunden ist), und zwar unabhängig von der Netzwerk Website, der das System zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b0da0-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="b0da0-163">Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung, die PSTN-Endpunkte einbeziehen, unterliegen standortbasierten Routing-Erzwingungen.</span><span class="sxs-lookup"><span data-stu-id="b0da0-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="b0da0-164">Bei diesen anrufen müssen nur PSTN-Gateways verwendet werden, die für solche Systeme als lokal definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b0da0-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="b0da0-165">Die folgende Tabelle zeigt die Gateway-Konfiguration von vier Gateways auf zwei verschiedenen Netzwerkstandorten: zwei mit PSTN-Gateways verbunden und zwei mit PBX-Systemen verbunden.</span><span class="sxs-lookup"><span data-stu-id="b0da0-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="b0da0-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="b0da0-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="b0da0-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="b0da0-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="b0da0-168">PstnGateway: Gateway 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="b0da0-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="b0da0-169">True</span><span class="sxs-lookup"><span data-stu-id="b0da0-169">True</span></span>     |   <span data-ttu-id="b0da0-170">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b0da0-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="b0da0-171">PstnGateway: Gateway 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="b0da0-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="b0da0-172">True</span><span class="sxs-lookup"><span data-stu-id="b0da0-172">True</span></span>      |      <span data-ttu-id="b0da0-173">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b0da0-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="b0da0-174">PstnGateway: Gateway 3 del-PBX</span><span class="sxs-lookup"><span data-stu-id="b0da0-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="b0da0-175">Falsch</span><span class="sxs-lookup"><span data-stu-id="b0da0-175">False</span></span>     |     <span data-ttu-id="b0da0-176">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b0da0-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="b0da0-177">PstnGateway: Gateway 4 Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="b0da0-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="b0da0-178">Falsch</span><span class="sxs-lookup"><span data-stu-id="b0da0-178">False</span></span>     |    <span data-ttu-id="b0da0-179">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b0da0-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="b0da0-180">Aktivieren des standortbasierten Routings für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b0da0-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="b0da0-181">Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die VoIP-Richtlinie der Benutzer ein, um PTSN Gebühren Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b0da0-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="b0da0-182">Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , um standortbasiertes Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.</span><span class="sxs-lookup"><span data-stu-id="b0da0-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="b0da0-183">In diesem Beispiel verhindern wir die PSTN-Maut Umgehung für von Benutzer1-Anruf Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="b0da0-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="b0da0-184">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b0da0-184">Related topics</span></span>
- [<span data-ttu-id="b0da0-185">Planen des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="b0da0-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="b0da0-186">Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="b0da0-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="b0da0-187">Terminologie für das standortbasierte Routing</span><span class="sxs-lookup"><span data-stu-id="b0da0-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
