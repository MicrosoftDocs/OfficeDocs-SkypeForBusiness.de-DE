---
title: Aktivieren des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie standortbasiertes Routing für das direkte Routing aktivieren können, einschließlich der Aktivierung für Benutzer, Netzwerk Websites, Gateway-Konfigurationen und Anruf Richtlinien.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158992"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="35854-103">Aktivieren des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="35854-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="35854-104">Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, dass Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md) gelesen haben, und führen Sie die Schritte unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md)aus.</span><span class="sxs-lookup"><span data-stu-id="35854-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="35854-105">In diesem Artikel wird beschrieben, wie standortbasiertes Routing für das direkte Routing aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="35854-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="35854-106">Nachdem Sie das direkte Routing für das Telefon System bereitgestellt und netzwerkregionen,-Standorte und-Subnetze eingerichtet haben, können Sie das standortbasierte Routing aktivieren.</span><span class="sxs-lookup"><span data-stu-id="35854-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="35854-107">Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="35854-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="35854-108">Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="35854-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="35854-109">Sie müssen standortbasiertes Routing für Folgendes aktivieren:</span><span class="sxs-lookup"><span data-stu-id="35854-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="35854-110">Benutzer</span><span class="sxs-lookup"><span data-stu-id="35854-110">Users</span></span>
- <span data-ttu-id="35854-111">Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="35854-111">Network sites</span></span>
- <span data-ttu-id="35854-112">Gateway-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="35854-112">Gateway configurations</span></span>
- <span data-ttu-id="35854-113">Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="35854-113">Calling policies</span></span>

<span data-ttu-id="35854-114">Sie können das [Microsoft Team Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShel](#using-powershell)l verwenden, um standortbasiertes Routing zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="35854-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="35854-115">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="35854-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="35854-116">Aktivieren des standortbasierten Routings für Benutzer</span><span class="sxs-lookup"><span data-stu-id="35854-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="35854-117">Erstellen Sie eine VoIP-Routing Richtlinie, und weisen Sie der Richtlinie PSTN-Nutzungen zu.</span><span class="sxs-lookup"><span data-stu-id="35854-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="35854-118">Wenn Sie einer Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="35854-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="35854-119">Verwenden Sie PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="35854-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="35854-120">Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="35854-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="35854-121">Weisen Sie die VoIP-Routing Richtlinie Benutzern zu, für die Routing Einschränkungen erzwungen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="35854-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="35854-122">Weitere Informationen zum Erstellen von VoIP-Routing Richtlinien und zum Zuweisen der Richtlinien zu Benutzern finden Sie unter [Verwalten von VoIP-Routing Richtlinien in Microsoft Teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="35854-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="35854-123">Aktivieren des standortbasierten Routings für Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="35854-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="35854-124">Aktivieren Sie standortbasiertes Routing für Ihre Websites, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="35854-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="35854-125">Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte** > **Netzwerktopologie**, wählen Sie eine Netzwerk Website aus, klicken Sie auf **Bearbeiten**, und aktivieren Sie dann **standortbasiertes Routing**.</span><span class="sxs-lookup"><span data-stu-id="35854-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="35854-126">Weitere Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="35854-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="35854-127">Aktivieren des standortbasierten Routings für Gateways</span><span class="sxs-lookup"><span data-stu-id="35854-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="35854-128">Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="35854-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="35854-129">Wechseln Sie in der linken Navigationsleiste zu **VoIP** > **Direct Routing**, und klicken Sie dann auf die Registerkarte **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="35854-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="35854-130">Wählen Sie den SBC aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="35854-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="35854-131">Aktivieren Sie unter **standortbasiertes Routing und Medienoptimierung**die **Option standortbasiertes Routing aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="35854-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="35854-132">Geben Sie die Gateway-Standort-ID an, und legen Sie dann den Bypass-Modus fest.</span><span class="sxs-lookup"><span data-stu-id="35854-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="35854-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="35854-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="35854-134">Aktivieren des standortbasierten Routings für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="35854-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="35854-135">Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die Anrufrichtlinie des Benutzers ein, um die PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="35854-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="35854-136">Aktivieren Sie dazu die Einstellung **Gebühren Umgehung** in der Anrufrichtlinie verhindern.</span><span class="sxs-lookup"><span data-stu-id="35854-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="35854-137">Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="35854-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="35854-138">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="35854-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="35854-139">Aktivieren des standortbasierten Routings für Benutzer</span><span class="sxs-lookup"><span data-stu-id="35854-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="35854-140">Verwenden Sie das Cmdlet " [Satz-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) ", um die PSTN-Verwendung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="35854-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="35854-141">Für mehrere Verwendungen trennen Sie jede Verwendung durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="35854-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="35854-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35854-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="35854-143">Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) , um eine VoIP-Routing Richtlinie zu erstellen, um den Benutzer mit den entsprechenden PSTN-Verwendungen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="35854-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="35854-144">Wenn Sie einer VoIP-Routing Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="35854-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="35854-145">Verwenden von PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden</span><span class="sxs-lookup"><span data-stu-id="35854-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="35854-146">Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="35854-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="35854-147">In diesem Beispiel erstellen wir zwei neue VoIP-Routing Richtlinien und weisen Ihnen PSTN-Nutzungen zu.</span><span class="sxs-lookup"><span data-stu-id="35854-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="35854-148">In der folgenden Tabelle sind die in diesem Beispiel definierten VoIP-Routing Richtlinien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="35854-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="35854-149">VoIP-Routing Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="35854-149">Voice routing policy 1</span></span>|<span data-ttu-id="35854-150">VoIP-Routing Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="35854-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="35854-151">Online-VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="35854-151">Online voice policy ID</span></span>   |<span data-ttu-id="35854-152">Delhi Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="35854-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="35854-153">Hyderabad Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="35854-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="35854-154">Online PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="35854-154">Online PSTN usages</span></span>  |<span data-ttu-id="35854-155">Ferngespräche</span><span class="sxs-lookup"><span data-stu-id="35854-155">Long Distance</span></span>  |<span data-ttu-id="35854-156">Fern-, Orts-, binnen-und fern-</span><span class="sxs-lookup"><span data-stu-id="35854-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="35854-157">Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) , um Benutzern, die Routing Einschränkungen erfordern, das Erzwingen von Online-VoIP-Routing Richtlinien zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="35854-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="35854-158">Aktivieren des standortbasierten Routings für Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="35854-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="35854-159">Verwenden Sie das Cmdlet " [festlegen-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) ", um standortbasiertes Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="35854-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="35854-160">In diesem Beispiel wird standortbasiertes Routing für die Delhi-Website und die Hyderabad-Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="35854-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="35854-161">In der folgenden Tabelle sind die Websites aufgeführt, die in diesem Beispiel für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="35854-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="35854-162">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="35854-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="35854-163">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="35854-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="35854-164">Standortname</span><span class="sxs-lookup"><span data-stu-id="35854-164">Site name</span></span>    |<span data-ttu-id="35854-165">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="35854-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="35854-166">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="35854-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="35854-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="35854-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="35854-168">Wahr</span><span class="sxs-lookup"><span data-stu-id="35854-168">True</span></span>    |<span data-ttu-id="35854-169">Wahr</span><span class="sxs-lookup"><span data-stu-id="35854-169">True</span></span>    |
    |<span data-ttu-id="35854-170">Subnetze</span><span class="sxs-lookup"><span data-stu-id="35854-170">Subnets</span></span>     |<span data-ttu-id="35854-171">Subnetz 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="35854-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="35854-172">Subnetz 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="35854-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="35854-173">Aktivieren des standortbasierten Routings für Gateways</span><span class="sxs-lookup"><span data-stu-id="35854-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="35854-174">Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) , um eine Gateway-Konfiguration für jede Gateway-oder Netzwerk Website zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35854-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="35854-175">Wenn einem System mehrere Gateways zugeordnet sind (beispielsweise Gateway oder Telefonanlage), ändern Sie die einzelnen Gateways, um standortbasierte Routing Einschränkungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="35854-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="35854-176">In diesem Beispiel erstellen wir für jedes Gateway eine Gateway-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="35854-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="35854-177">Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="35854-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="35854-178">Verwenden Sie das Cmdlet " [festlegen-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) ", um standortbasiertes Routing für Ihre Gateways zu aktivieren, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="35854-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="35854-179">Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="35854-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="35854-180">In diesem Beispiel aktivieren wir standortbasiertes Routing für jedes Gateway, das PSTN-Gateways in den Websites Delhi und Hyderabad zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="35854-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="35854-181">Aktivieren Sie das standortbasierte Routing nicht für Gateways, die keine Anrufe an das PSTN weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="35854-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="35854-182">Sie müssen das Gateway jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet.</span><span class="sxs-lookup"><span data-stu-id="35854-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="35854-183">Dies liegt daran, dass standortbasierte Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="35854-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="35854-184">In diesem Beispiel ist die standortbasierte Weiterleitung für jedes Gateway, das PBX-Systemen in den Websites Delhi und Hyderabad zugeordnet ist, nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="35854-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="35854-185">Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (beispielsweise eine Telefonanlage) weiterleiten, weisen ähnliche Einschränkungen wie Endpunkte von Team Benutzern auf, die für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="35854-185">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="35854-186">Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von Teams-Benutzern tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="35854-186">This means that these users can place and receive calls to and from Teams users regardless of the user's location.</span></span> <span data-ttu-id="35854-187">Sie können auch Anrufe von und zu anderen Systemen tätigen und empfangen, die keine Anrufe an das PSTN-Netzwerk weiterleiten (beispielsweise einen Endpunkt, der mit einer anderen Telefonanlage verbunden ist), und zwar unabhängig von der Netzwerk Website, der das System zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="35854-187">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="35854-188">Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung, die PSTN-Endpunkte einbeziehen, unterliegen standortbasierten Routing-Erzwingungen.</span><span class="sxs-lookup"><span data-stu-id="35854-188">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="35854-189">Bei diesen anrufen müssen nur PSTN-Gateways verwendet werden, die für solche Systeme als lokal definiert sind.</span><span class="sxs-lookup"><span data-stu-id="35854-189">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="35854-190">Die folgende Tabelle zeigt die Gateway-Konfiguration von vier Gateways auf zwei verschiedenen Netzwerkstandorten: zwei mit PSTN-Gateways verbunden und zwei mit PBX-Systemen verbunden.</span><span class="sxs-lookup"><span data-stu-id="35854-190">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="35854-191">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="35854-191">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="35854-192">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="35854-192">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="35854-193">PstnGateway: Gateway 1 del-GW</span><span class="sxs-lookup"><span data-stu-id="35854-193">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="35854-194">Wahr</span><span class="sxs-lookup"><span data-stu-id="35854-194">True</span></span>     |   <span data-ttu-id="35854-195">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="35854-195">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="35854-196">PstnGateway: Gateway 2 Hyd-GW</span><span class="sxs-lookup"><span data-stu-id="35854-196">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="35854-197">Wahr</span><span class="sxs-lookup"><span data-stu-id="35854-197">True</span></span>      |      <span data-ttu-id="35854-198">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="35854-198">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="35854-199">PstnGateway: Gateway 3 del-PBX</span><span class="sxs-lookup"><span data-stu-id="35854-199">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="35854-200">Falsch</span><span class="sxs-lookup"><span data-stu-id="35854-200">False</span></span>     |     <span data-ttu-id="35854-201">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="35854-201">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="35854-202">PstnGateway: Gateway 4 Hyd-PBX</span><span class="sxs-lookup"><span data-stu-id="35854-202">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="35854-203">Falsch</span><span class="sxs-lookup"><span data-stu-id="35854-203">False</span></span>     |    <span data-ttu-id="35854-204">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="35854-204">Site 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="35854-205">Aktivieren des standortbasierten Routings für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="35854-205">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="35854-206">Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die VoIP-Richtlinie der Benutzer ein, um PTSN Gebühren Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="35854-206">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="35854-207">Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , um standortbasiertes Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.</span><span class="sxs-lookup"><span data-stu-id="35854-207">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="35854-208">In diesem Beispiel verhindern wir die PSTN-Maut Umgehung für von Benutzer1-Anruf Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="35854-208">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="35854-209">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="35854-209">Related topics</span></span>

- [<span data-ttu-id="35854-210">Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams</span><span class="sxs-lookup"><span data-stu-id="35854-210">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
