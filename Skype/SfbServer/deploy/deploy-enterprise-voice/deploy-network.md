---
title: Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Sie können netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze in Skype for Business Server erstellen oder ändern. Alle diese Funktionen werden für die erweiterten Enterprise-VoIP-Features verwendet: medienumgehung, Anrufsteuerung und standortbasiertes Routing.'
ms.openlocfilehash: 237720373c78bcb4a3cb3ad0aed376f2dc136a71
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245410"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="d4a9e-104">Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d4a9e-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="d4a9e-105">Sie können netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze in Skype for Business Server erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="d4a9e-106">Alle diese Funktionen werden für die erweiterten Enterprise-VoIP-Features verwendet: medienumgehung, Anrufsteuerung und standortbasiertes Routing.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="d4a9e-107">Zu den erweiterten Enterprise-VoIP-Features gehören [Anrufsteuerung](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [medienumgehung](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [Orts basiertes Routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)und [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4a9e-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="d4a9e-108">Für alle diese Funktionen müssen Sie Netzwerkregionen, Netzwerkstandorte und Subnetze erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="d4a9e-109">Beispiel: Für alle diese Funktionen ist es erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten Netzwerkstandort und jeder Netzwerkstandort einer Netzwerkregion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="d4a9e-110">Weitere Informationen zu diesen Begriffen finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="d4a9e-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="d4a9e-111">Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="d4a9e-112">Die Anrufsteuerung erfordert, dass ein Bandbreitenrichtlinienprofil für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="d4a9e-113">Wenn Sie beabsichtigen, die Anrufsteuerung bereitzustellen, müssen Sie [in Skype for Business Server bandbreitenrichtlinienprofile erstellen](create-bandwidth-policy-profiles.md) , bevor Sie Ihre Netzwerk Websites konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="d4a9e-114">Für E9-1-1 ist es erforderlich, dass für jeden Standort eine Standortrichtlinie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="d4a9e-115">Wenn Sie die Bereitstellung von E9-1-1 planen, müssen Sie [in Skype for Business Server Standortrichtlinien erstellen](create-location-policies.md) , bevor Sie Ihre Netzwerk Websites konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="d4a9e-116">Erstellen oder Ändern einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="d4a9e-116">Create or modify a Network Region</span></span>

<span data-ttu-id="d4a9e-117">Wenn Sie bereits netzwerkregionen für eines dieser Funktionen erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="d4a9e-p106">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4a9e-120">So erstellen Sie einen Netzwerkbereich mit der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d4a9e-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d4a9e-121">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d4a9e-122">Führen Sie das Cmdlet New-CsNetworkRegion aus, um Netzwerkregionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="d4a9e-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-123">For example:</span></span>

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="d4a9e-124">In diesem Beispiel haben Sie einen Netzwerkbereich mit dem Namen "Northamerica" erstellt, der einem zentralen Standort mit der Website-ID Chicago zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="d4a9e-125">Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4a9e-126">So erstellen Sie einen Netzwerkbereich mit der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d4a9e-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4a9e-127">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4a9e-128">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d4a9e-129">Klicken Sie auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-129">Click **Region**.</span></span>

4. <span data-ttu-id="d4a9e-130">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-130">Click **New**.</span></span>

5. <span data-ttu-id="d4a9e-131">Klicken Sie auf der Seite **Neue Region** auf **Name** und geben Sie einen Namen für die Netzwerkregion ein.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="d4a9e-132">Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="d4a9e-133">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="d4a9e-134">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-134">Click **Commit**.</span></span>

9. <span data-ttu-id="d4a9e-135">Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4a9e-136">So ändern Sie einen Netzwerkbereich mit der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d4a9e-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d4a9e-137">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d4a9e-138">Führen Sie das Cmdlet Set-CsNetworkRegion aus, um eine vorhandene Netzwerkregion zu ändern:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="d4a9e-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-139">For example:</span></span>

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="d4a9e-140">In diesem Beispiel haben Sie eine vorhandene netzwerkregion mit dem Namen "Northamerica" (erstellt mit den Verfahren weiter oben in diesem Thema) geändert, indem Sie die Beschreibung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="d4a9e-141">Wenn für den Bereich "Northamerica" eine Beschreibung vorhanden ist, wird dieser durch diesen Befehl mit diesem Wert überschrieben. Wenn keine Beschreibung festgelegt wurde, wird Sie durch diesen Befehl festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="d4a9e-142">Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4a9e-143">So ändern Sie einen Netzwerkbereich mit der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d4a9e-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4a9e-144">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4a9e-145">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d4a9e-146">Klicken Sie auf die Navigationsschaltfläche **Region**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="d4a9e-147">Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="d4a9e-148">Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="d4a9e-149">Ändern Sie auf der Seite " **Bereich bearbeiten** " die Werte für die Einstellungen dieses Netzwerkbereichs entsprechend.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="d4a9e-150">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-150">Click **Commit**.</span></span>

8. <span data-ttu-id="d4a9e-151">Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="d4a9e-152">Erstellen oder Ändern eines Netzwerkstandorts</span><span class="sxs-lookup"><span data-stu-id="d4a9e-152">Create or modify a network site</span></span>

<span data-ttu-id="d4a9e-153">Wenn Sie bereits Netzwerk Websites für eines dieser Funktionen erstellt haben, müssen Sie keine neuen Netzwerk Websites erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben Netzwerk Websites verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="d4a9e-154">Sie müssen jedoch möglicherweise eine vorhandene Definition eines Netzwerkstandorts ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="d4a9e-155">Wenn Sie z. B. einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4a9e-156">So erstellen Sie eine Netzwerk Website mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d4a9e-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d4a9e-157">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d4a9e-158">Führen Sie das Cmdlet New-CsNetworkSite aus, um Netzwerkstandorte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="d4a9e-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-159">For example:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="d4a9e-160">In diesem Beispiel haben Sie eine Netzwerk Website mit dem Namen "Chicago" erstellt, die sich in der netzwerkregion "Northamerica" befindet.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a9e-161">Die Netzwerkregion „NorthAmerica“ muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="d4a9e-162">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4a9e-163">So erstellen Sie eine Netzwerk Website mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d4a9e-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4a9e-164">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4a9e-165">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d4a9e-166">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="d4a9e-167">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-167">Click **New**.</span></span>

5. <span data-ttu-id="d4a9e-168">Klicken Sie auf der Seite **Neuer Standort** auf **Name** und geben Sie einen Namen für den Netzwerkstandort ein.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="d4a9e-169">Klicken Sie auf **Region** und klicken Sie dann auf eine Region in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="d4a9e-170">Klicken Sie optional auf **Bandbreitenrichtlinie** und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a9e-171">Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="d4a9e-172">Klicken Sie optional auf **Ortungsrichtlinie** und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a9e-173">Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="d4a9e-174">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="d4a9e-175">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-175">Click **Commit**.</span></span>

11. <span data-ttu-id="d4a9e-176">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4a9e-177">So ändern Sie eine Netzwerk Website mithilfe der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d4a9e-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d4a9e-178">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d4a9e-179">Führen Sie das Cmdlet Set-CsNetworkSite aus, um Netzwerkstandorte zu ändern:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="d4a9e-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-180">For example:</span></span>

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="d4a9e-181">In diesem Beispiel wird die Website mit dem Namen "Albuquerque" in die netzwerkregion "Northamerica" verschoben.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="d4a9e-182">Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet Set-CsNetworkSite mit dem Parameter BWPolicyProfileID oder LocationPolicy ausführen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a9e-p110">Wenngleich der Parameter BypassID für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="d4a9e-185">Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4a9e-186">So ändern Sie eine Netzwerk Website mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="d4a9e-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4a9e-187">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4a9e-188">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d4a9e-189">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="d4a9e-190">Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="d4a9e-191">Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="d4a9e-192">Ändern Sie auf der Seite " **Website bearbeiten** " die Werte für die Einstellungen dieser Netzwerk Website entsprechend.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="d4a9e-193">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-193">Click **Commit**.</span></span>

8. <span data-ttu-id="d4a9e-194">Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="d4a9e-195">Zuordnen eines Subnetzes zu einem Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="d4a9e-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="d4a9e-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a9e-196"></span></span>

<span data-ttu-id="d4a9e-197">Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="d4a9e-198">Wenn die Position jeder Partei in einer Sitzung bekannt ist, können erweiterte Enterprise-VoIP-Features diese Informationen anwenden, um festzulegen, wie die Anrufeinrichtung oder das Routing gehandhabt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="d4a9e-199">Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="d4a9e-200">Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="d4a9e-201">Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="d4a9e-202">Beispielsweise wäre die öffentliche IP-Adresse, die dem A/V-Edgedienst auf dem zentralen Standort Chicago entspricht, NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d4a9e-203">So ordnen Sie ein Subnetz mithilfe der Skype for Business Server-Verwaltungsshell einer Netzwerk Website zu</span><span class="sxs-lookup"><span data-stu-id="d4a9e-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d4a9e-204">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d4a9e-205">Führen Sie das Cmdlet **New-CsNetworkSubnet** aus, um ein Subnetz einem Netzwerkstandort zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="d4a9e-206">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-206">For example:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="d4a9e-207">In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und der Netzwerk Website "Chicago" erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="d4a9e-208">Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="d4a9e-209">So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu</span><span class="sxs-lookup"><span data-stu-id="d4a9e-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="d4a9e-p113">Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="d4a9e-212">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d4a9e-213">Führen Sie das folgende Cmdlet aus, um **Subnet. CSV**zu importieren, und speichern Sie dann den Inhalt im lync Server-Verwaltungsspeicher:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d4a9e-214">So ordnen Sie ein Subnetz mithilfe der Skype for Business Server-Systemsteuerung einer Netzwerk Website zu</span><span class="sxs-lookup"><span data-stu-id="d4a9e-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d4a9e-215">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4a9e-216">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d4a9e-217">Klicken Sie auf die Navigationsschaltfläche **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="d4a9e-218">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-218">Click **New**.</span></span>

5. <span data-ttu-id="d4a9e-219">Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID** und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="d4a9e-220">Klicken Sie auf **Maske** und geben Sie die Bitmaske für das Subnetz ein.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="d4a9e-221">Klicken Sie auf **Netzwerkstandort-ID** und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4a9e-222">Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="d4a9e-223">Ausführliche Informationen zu dem Verfahren finden Sie unter [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4a9e-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="d4a9e-224">Sie können auch Standort-IDs für Ihre Bereitstellung abrufen, indem Sie das Cmdlet **Get-CsNetworkSite** ausführen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="d4a9e-225">Ausführliche Informationen finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="d4a9e-226">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="d4a9e-227">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-227">Click **Commit**.</span></span>

<span data-ttu-id="d4a9e-228">Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="d4a9e-229">Es wird eine Warnung zur Schlüssel Integritäts Anzeige (Khi) ausgelöst, die eine Liste der IP-Adressen angibt, die in Ihrem Netzwerk vorhanden sind, aber keinem Subnetz zugeordnet sind, oder das Subnetz, das die IP-Adressen enthält, nicht mit einer Netzwerk Website verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="d4a9e-230">Diese Benachrichtigung wird innerhalb eines Zeitraums von 8 Stunden nicht mehrmals ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="d4a9e-231">Die relevanten Warnungsinformationen und ein Beispiel lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="d4a9e-232">**Quelle**: CS-Bandbreitenrichtliniendienst (Core)</span><span class="sxs-lookup"><span data-stu-id="d4a9e-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="d4a9e-233">**Ereignisnummer**: 36034</span><span class="sxs-lookup"><span data-stu-id="d4a9e-233">**Event number**: 36034</span></span>

 <span data-ttu-id="d4a9e-234">**Ebene**: 2</span><span class="sxs-lookup"><span data-stu-id="d4a9e-234">**Level**: 2</span></span>

 <span data-ttu-id="d4a9e-235">**Beschreibung**: die Subnetze für die folgenden IP- \<Adressen: die Liste\> der IP-Adressen ist entweder nicht konfiguriert, oder die Subnetze sind nicht mit einer Netzwerk Website verbunden.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="d4a9e-236">**Ursache**: Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="d4a9e-237">**Lösung**: Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="d4a9e-p116">Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:</span><span class="sxs-lookup"><span data-stu-id="d4a9e-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="d4a9e-240">Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="d4a9e-241">Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d4a9e-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a9e-242">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4a9e-242">See also</span></span>
<span data-ttu-id="d4a9e-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a9e-243"></span></span>


[<span data-ttu-id="d4a9e-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4a9e-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d4a9e-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4a9e-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d4a9e-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4a9e-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d4a9e-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4a9e-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d4a9e-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d4a9e-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="d4a9e-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d4a9e-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="d4a9e-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d4a9e-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="d4a9e-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d4a9e-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

