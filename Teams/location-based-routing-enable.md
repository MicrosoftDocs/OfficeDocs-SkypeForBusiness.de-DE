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
ms.openlocfilehash: e4cadbfb700c7478cb77c62f4597c9ae00164b0c
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372044"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="c8890-103">Aktivieren des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="c8890-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="c8890-104">Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, stellen Sie sicher, dass Sie den [Plan standortbasiertes Routing für das direkte Routing](location-based-routing-plan.md) gelesen haben, und führen Sie die Schritte unter [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md)aus.</span><span class="sxs-lookup"><span data-stu-id="c8890-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="c8890-105">In diesem Artikel wird beschrieben, wie standortbasiertes Routing für das direkte Routing aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c8890-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="c8890-106">Nachdem Sie das direkte Routing für das Telefon System bereitgestellt und netzwerkregionen,-Standorte und-Subnetze eingerichtet haben, können Sie das standortbasierte Routing aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8890-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="c8890-107">Um die Schritte in diesem Artikel ausführen zu können, müssen Sie sich mit PowerShell-Cmdlets vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="c8890-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="c8890-108">Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c8890-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="c8890-109">Sie müssen standortbasiertes Routing für Folgendes aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c8890-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="c8890-110">Benutzer</span><span class="sxs-lookup"><span data-stu-id="c8890-110">Users</span></span>
- <span data-ttu-id="c8890-111">Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="c8890-111">Network sites</span></span>
- <span data-ttu-id="c8890-112">Gateway-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c8890-112">Gateway configurations</span></span>
- <span data-ttu-id="c8890-113">Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="c8890-113">Calling policies</span></span>

<span data-ttu-id="c8890-114">Sie können das [Microsoft Team Admin Center](#using-the-microsoft-teams-admin-center) oder [PowerShel](#using-powershell)l verwenden, um standortbasiertes Routing zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8890-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c8890-115">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="c8890-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="c8890-116">Aktivieren des standortbasierten Routings für Benutzer</span><span class="sxs-lookup"><span data-stu-id="c8890-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="c8890-117">Erstellen Sie eine VoIP-Routing Richtlinie, und weisen Sie der Richtlinie PSTN-Nutzungen zu.</span><span class="sxs-lookup"><span data-stu-id="c8890-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="c8890-118">Wenn Sie einer Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="c8890-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="c8890-119">Verwenden Sie PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8890-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="c8890-120">Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c8890-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="c8890-121">Weisen Sie die VoIP-Routing Richtlinie Benutzern zu, für die Routing Einschränkungen erzwungen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c8890-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="c8890-122">Weitere Informationen zum Erstellen von VoIP-Routing Richtlinien und zum Zuweisen der Richtlinien zu Benutzern finden Sie unter [Verwalten von VoIP-Routing Richtlinien in Microsoft Teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c8890-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="c8890-123">Aktivieren des standortbasierten Routings für Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="c8890-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="c8890-124">Aktivieren Sie standortbasiertes Routing für Ihre Websites, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="c8890-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="c8890-125">Wechseln Sie dazu in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**  >  **Netzwerktopologie**, wählen Sie eine Netzwerk Website aus, klicken Sie auf **Bearbeiten**, und aktivieren Sie dann **standortbasiertes Routing**.</span><span class="sxs-lookup"><span data-stu-id="c8890-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="c8890-126">Weitere Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="c8890-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="c8890-127">Aktivieren des standortbasierten Routings für Gateways</span><span class="sxs-lookup"><span data-stu-id="c8890-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="c8890-128">Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="c8890-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="c8890-129">Wechseln Sie in der linken Navigationsleiste zu **VoIP**  >  **Direct Routing**, und klicken Sie dann auf die Registerkarte **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="c8890-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="c8890-130">Wählen Sie den SBC aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c8890-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="c8890-131">Aktivieren Sie unter **standortbasiertes Routing und Medienoptimierung**die **Option standortbasiertes Routing aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="c8890-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="c8890-132">Geben Sie die Gateway-Standort-ID an, und legen Sie dann den Bypass-Modus fest.</span><span class="sxs-lookup"><span data-stu-id="c8890-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="c8890-133">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c8890-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="c8890-134">Aktivieren des standortbasierten Routings für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c8890-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="c8890-135">Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die Anrufrichtlinie des Benutzers ein, um die PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c8890-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="c8890-136">Aktivieren Sie dazu die Einstellung **Gebühren Umgehung** in der Anrufrichtlinie verhindern.</span><span class="sxs-lookup"><span data-stu-id="c8890-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="c8890-137">Weitere Informationen finden Sie unter [Aufrufen von Richtlinien in Teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="c8890-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="c8890-138">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8890-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="c8890-139">Aktivieren des standortbasierten Routings für Benutzer</span><span class="sxs-lookup"><span data-stu-id="c8890-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="c8890-140">Verwenden Sie das Cmdlet " [Satz-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) ", um die PSTN-Verwendung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c8890-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="c8890-141">Für mehrere Verwendungen trennen Sie jede Verwendung durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="c8890-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="c8890-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8890-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="c8890-143">Verwenden Sie das Cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) , um eine VoIP-Routing Richtlinie zu erstellen, um den Benutzer mit den entsprechenden PSTN-Verwendungen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="c8890-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="c8890-144">Wenn Sie einer VoIP-Routing Richtlinie PSTN-Nutzungen zuweisen, stellen Sie sicher, dass Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="c8890-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="c8890-145">Verwenden von PSTN-Nutzungen, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für die Website verwenden</span><span class="sxs-lookup"><span data-stu-id="c8890-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="c8890-146">Verwenden Sie PSTN-Nutzungen für VoIP-Routen, die ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der standortbasierte Routing Einschränkungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c8890-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="c8890-147">In diesem Beispiel erstellen wir zwei neue VoIP-Routing Richtlinien und weisen Ihnen PSTN-Nutzungen zu.</span><span class="sxs-lookup"><span data-stu-id="c8890-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="c8890-148">In der folgenden Tabelle sind die in diesem Beispiel definierten VoIP-Routing Richtlinien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8890-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="c8890-149">VoIP-Routing Richtlinie 1</span><span class="sxs-lookup"><span data-stu-id="c8890-149">Voice routing policy 1</span></span>|<span data-ttu-id="c8890-150">VoIP-Routing Richtlinie 2</span><span class="sxs-lookup"><span data-stu-id="c8890-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="c8890-151">Online-VoIP-Richtlinien-ID</span><span class="sxs-lookup"><span data-stu-id="c8890-151">Online voice policy ID</span></span>   |<span data-ttu-id="c8890-152">Delhi Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c8890-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="c8890-153">Hyderabad Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c8890-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="c8890-154">Online PSTN-Nutzungen</span><span class="sxs-lookup"><span data-stu-id="c8890-154">Online PSTN usages</span></span>  |<span data-ttu-id="c8890-155">Ferngespräche</span><span class="sxs-lookup"><span data-stu-id="c8890-155">Long Distance</span></span>  |<span data-ttu-id="c8890-156">Fern-, Orts-, binnen-und fern-</span><span class="sxs-lookup"><span data-stu-id="c8890-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="c8890-157">Verwenden Sie das Cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) , um Benutzern, die Routing Einschränkungen erfordern, das Erzwingen von Online-VoIP-Routing Richtlinien zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="c8890-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="c8890-158">Aktivieren des standortbasierten Routings für Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="c8890-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="c8890-159">Verwenden Sie das Cmdlet " [festlegen-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) ", um standortbasiertes Routing zu aktivieren und Ihren Netzwerk Websites VoIP-Routing Richtlinien zuzuordnen, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="c8890-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="c8890-160">In diesem Beispiel wird standortbasiertes Routing für die Delhi-Website und die Hyderabad-Website aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8890-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="c8890-161">In der folgenden Tabelle sind die Websites aufgeführt, die in diesem Beispiel für standortbasiertes Routing aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="c8890-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="c8890-162">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="c8890-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="c8890-163">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c8890-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="c8890-164">Standortname</span><span class="sxs-lookup"><span data-stu-id="c8890-164">Site name</span></span>    |<span data-ttu-id="c8890-165">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="c8890-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="c8890-166">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c8890-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="c8890-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="c8890-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="c8890-168">Wahr</span><span class="sxs-lookup"><span data-stu-id="c8890-168">True</span></span>    |<span data-ttu-id="c8890-169">Wahr</span><span class="sxs-lookup"><span data-stu-id="c8890-169">True</span></span>    |
    |<span data-ttu-id="c8890-170">Subnetze</span><span class="sxs-lookup"><span data-stu-id="c8890-170">Subnets</span></span>     |<span data-ttu-id="c8890-171">Subnetz 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="c8890-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="c8890-172">Subnetz 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="c8890-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="c8890-173">Aktivieren des standortbasierten Routings für Gateways</span><span class="sxs-lookup"><span data-stu-id="c8890-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="c8890-174">Verwenden Sie das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) , um eine Gateway-Konfiguration für jede Gateway-oder Netzwerk Website zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8890-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="c8890-175">Wenn einem System mehrere Gateways zugeordnet sind (beispielsweise Gateway oder Telefonanlage), ändern Sie die einzelnen Gateways, um standortbasierte Routing Einschränkungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c8890-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="c8890-176">In diesem Beispiel erstellen wir für jedes Gateway eine Gateway-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c8890-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="c8890-177">Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c8890-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="c8890-178">Verwenden Sie das Cmdlet " [festlegen-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) ", um standortbasiertes Routing für Ihre Gateways zu aktivieren, die Routing Einschränkungen erzwingen müssen.</span><span class="sxs-lookup"><span data-stu-id="c8890-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="c8890-179">Aktivieren Sie das standortbasierte Routing für Gateways, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie die Netzwerk Website zu, auf der sich das Gateway befindet.</span><span class="sxs-lookup"><span data-stu-id="c8890-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="c8890-180">In diesem Beispiel aktivieren wir standortbasiertes Routing für jedes Gateway, das PSTN-Gateways in den Websites Delhi und Hyderabad zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c8890-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="c8890-181">Aktivieren Sie das standortbasierte Routing nicht für Gateways, die keine Anrufe an das PSTN weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="c8890-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="c8890-182">Sie müssen das Gateway jedoch weiterhin der Netzwerk Website zuordnen, auf der sich das System befindet.</span><span class="sxs-lookup"><span data-stu-id="c8890-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="c8890-183">Dies liegt daran, dass standortbasierte Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die Endpunkte erreichen, die über dieses Gateway verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="c8890-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="c8890-184">In diesem Beispiel ist die standortbasierte Weiterleitung für jedes Gateway, das PBX-Systemen in den Websites Delhi und Hyderabad zugeordnet ist, nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8890-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="c8890-185">Aktivieren des standortbasierten Routings für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c8890-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="c8890-186">Wenn Sie ein standortbasiertes Routing für bestimmte Benutzer erzwingen möchten, richten Sie die VoIP-Richtlinie der Benutzer ein, um PTSN Gebühren Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c8890-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="c8890-187">Verwenden Sie das Cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) , um standortbasiertes Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.</span><span class="sxs-lookup"><span data-stu-id="c8890-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="c8890-188">In diesem Beispiel verhindern wir die PSTN-Maut Umgehung für von Benutzer1-Anruf Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="c8890-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="c8890-189">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c8890-189">Related topics</span></span>

- [<span data-ttu-id="c8890-190">Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams</span><span class="sxs-lookup"><span data-stu-id="c8890-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
