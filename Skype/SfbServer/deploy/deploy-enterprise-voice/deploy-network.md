---
title: Bereitstellen von netzwerkregionen, Standorten und Subnetzen in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Erstellen oder Ändern von netzwerkregionen, Netzwerkstandorten, und ordnen Sie Subnetze in Skype Netzwerk für Business Server. Alle diese für den erweiterten Enterprise-VoIP-Funktionen verwendet werden: Medien umgehen, call Admission Control und Standortbasierte Weiterleitung.'
ms.openlocfilehash: 427ab9102fe7a840aee68e0dbc2c372b908930e8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20980774"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="6cf2f-104">Bereitstellen von netzwerkregionen, Standorten und Subnetzen in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="6cf2f-104">Deploy network regions, sites and subnets in Skype for Business</span></span>
 
<span data-ttu-id="6cf2f-105">Erstellen oder Ändern von netzwerkregionen, Netzwerkstandorten, und ordnen Sie Subnetze in Skype Netzwerk für Business Server.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="6cf2f-106">Alle diese für den erweiterten Enterprise-VoIP-Funktionen verwendet werden: Medien umgehen, call Admission Control und Standortbasierte Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>
  
<span data-ttu-id="6cf2f-107">Die erweiterten Enterprise-VoIP-Funktionen sind [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) und [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="6cf2f-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="6cf2f-108">Für alle diese Funktionen müssen Sie Netzwerkregionen, Netzwerkstandorte und Subnetze erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="6cf2f-109">Beispiel: Für alle diese Funktionen ist es erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten Netzwerkstandort und jeder Netzwerkstandort einer Netzwerkregion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="6cf2f-110">Weitere Informationen zu dieser Begriffe finden Sie unter [Netzwerkeinstellungen für den erweiterten Enterprise-VoIP-Funktionen in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="6cf2f-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span></span>
  
<span data-ttu-id="6cf2f-111">Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>
  
- <span data-ttu-id="6cf2f-112">Die Anrufsteuerung erfordert, dass ein Bandbreitenrichtlinienprofil für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="6cf2f-113">Wenn Sie die anrufsteuerung bereitstellen möchten, müssen Sie vor dem Konfigurieren von Netzwerkstandorten [bandbreitenrichtlinienprofile in Skype für Business Server erstellen](create-bandwidth-policy-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="6cf2f-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>
    
- <span data-ttu-id="6cf2f-114">Für E9-1-1 ist es erforderlich, dass für jeden Standort eine Standortrichtlinie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="6cf2f-115">Wenn Sie E9-1-1 bereitstellen möchten, müssen Sie vor dem Konfigurieren von Netzwerkstandorten [Standortrichtlinien in Skype für Business Server erstellen](create-location-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="6cf2f-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>
    
## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="6cf2f-116">Erstellen oder Ändern einer Netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="6cf2f-116">Create or modify a Network Region</span></span>

<span data-ttu-id="6cf2f-117">Wenn Sie bereits von netzwerkregionen für eines der folgenden Features erstellt haben, müssen Sie keine neuen netzwerkregionen zu erstellen; andere erweiterten Enterprise-VoIP-Funktionen werden die gleichen netzwerkregionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> 
  
<span data-ttu-id="6cf2f-p106">Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 
  
### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cf2f-120">So erstellen Sie eine netzwerkregion mithilfe der Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6cf2f-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6cf2f-121">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6cf2f-122">Führen Sie das Cmdlet New-CsNetworkRegion aus, um Netzwerkregionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="6cf2f-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-123">For example:</span></span>
    
   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="6cf2f-124">In diesem Beispiel wird eine netzwerkregion namens "NorthAmerica" erstellt haben, einer zentralen Website mit Website-ID "Chicago" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>
    
3. <span data-ttu-id="6cf2f-125">Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>
    
### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cf2f-126">So erstellen Sie eine netzwerkregion mithilfe der Skype für Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6cf2f-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6cf2f-127">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-127">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6cf2f-128">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-128">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cf2f-129">Klicken Sie auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-129">Click **Region**.</span></span>
    
4. <span data-ttu-id="6cf2f-130">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-130">Click **New**.</span></span>
    
5. <span data-ttu-id="6cf2f-131">Klicken Sie auf der Seite **Neue Region** auf **Name** und geben Sie einen Namen für die Netzwerkregion ein.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>
    
6. <span data-ttu-id="6cf2f-132">Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-132">Click **Central site**, and then click a central site in the list.</span></span>
    
7. <span data-ttu-id="6cf2f-133">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>
    
8. <span data-ttu-id="6cf2f-134">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-134">Click **Commit**.</span></span>
    
9. <span data-ttu-id="6cf2f-135">Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>
    
### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cf2f-136">So ändern Sie eine netzwerkregion mithilfe der Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6cf2f-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6cf2f-137">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6cf2f-138">Führen Sie das Cmdlet Set-CsNetworkRegion aus, um eine vorhandene Netzwerkregion zu ändern:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="6cf2f-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-139">For example:</span></span>
    
   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="6cf2f-140">In diesem Beispiel können Sie durch Ändern der Beschreibung eine vorhandenen netzwerkregion namens "NorthAmerica" (mit den Verfahren in diesem Thema erstellt) geändert.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="6cf2f-141">Wenn eine Beschreibung für die Region "Nordamerika" vorhanden ist, überschreibt dieser Befehl es mit diesem Wert. Wenn keine Beschreibung festgelegt wurde hatte, wird mit diesem Befehl es aus.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>
    
3. <span data-ttu-id="6cf2f-142">Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>
    
### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cf2f-143">So ändern Sie eine netzwerkregion mithilfe der Skype für Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6cf2f-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6cf2f-144">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-144">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6cf2f-145">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-145">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cf2f-146">Klicken Sie auf die Navigationsschaltfläche **Region**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-146">Click the **Region** navigation button.</span></span>
    
4. <span data-ttu-id="6cf2f-147">Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-147">In the table, click the network region that you want to modify.</span></span>
    
5. <span data-ttu-id="6cf2f-148">Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-148">Click **Edit**, and then click **Show details…**.</span></span>
    
6. <span data-ttu-id="6cf2f-149">Ändern Sie auf der Seite **Region bearbeiten** die Werte für diese netzwerkregion Einstellungen wie gewünscht ab.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>
    
7. <span data-ttu-id="6cf2f-150">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-150">Click **Commit**.</span></span>
    
8. <span data-ttu-id="6cf2f-151">Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>
    
## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="6cf2f-152">Erstellen oder Ändern eines Netzwerkstandorts</span><span class="sxs-lookup"><span data-stu-id="6cf2f-152">Create or modify a network site</span></span>

<span data-ttu-id="6cf2f-153">Wenn Sie Netzwerkstandorte für eines der folgenden Features bereits erstellt haben, müssen Sie keine neuen Netzwerkstandorten erstellen; andere erweiterten Enterprise-VoIP-Funktionen werden die gleichen Netzwerkstandorten verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="6cf2f-154">Sie müssen jedoch möglicherweise eine vorhandene Definition eines Netzwerkstandorts ändern, um funktionsspezifische Einstellungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="6cf2f-155">Wenn Sie z. B. einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span> 
  
### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cf2f-156">Erstellen Sie einen Netzwerkstandort mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6cf2f-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6cf2f-157">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6cf2f-158">Führen Sie das Cmdlet New-CsNetworkSite aus, um Netzwerkstandorte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="6cf2f-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-159">For example:</span></span>
    
   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="6cf2f-160">In diesem Beispiel wird einen Netzwerkstandort namens "Chicago" erstellt haben, ist in der netzwerkregion "NorthAmerica befindet".</span><span class="sxs-lookup"><span data-stu-id="6cf2f-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cf2f-161">Die Netzwerkregion „NorthAmerica“ muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span> 
  
3. <span data-ttu-id="6cf2f-162">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>
    
### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cf2f-163">Einen Netzwerkstandort mithilfe von Skype Business Server-Systemsteuerung erstellen</span><span class="sxs-lookup"><span data-stu-id="6cf2f-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6cf2f-164">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-164">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6cf2f-165">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-165">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cf2f-166">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-166">Click the **Site** navigation button.</span></span>
    
4. <span data-ttu-id="6cf2f-167">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-167">Click **New**.</span></span>
    
5. <span data-ttu-id="6cf2f-168">Klicken Sie auf der Seite **Neuer Standort** auf **Name** und geben Sie einen Namen für den Netzwerkstandort ein.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>
    
6. <span data-ttu-id="6cf2f-169">Klicken Sie auf **Region** und klicken Sie dann auf eine Region in der Liste.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-169">Click **Region**, and then click a region in the list.</span></span>
    
7. <span data-ttu-id="6cf2f-170">Klicken Sie optional auf **Bandbreitenrichtlinie** und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cf2f-171">Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span> 
  
8. <span data-ttu-id="6cf2f-172">Klicken Sie optional auf **Ortungsrichtlinie** und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cf2f-173">Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span> 
  
9. <span data-ttu-id="6cf2f-174">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>
    
10. <span data-ttu-id="6cf2f-175">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-175">Click **Commit**.</span></span>
    
11. <span data-ttu-id="6cf2f-176">Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>
    
### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cf2f-177">So ändern Sie einen Netzwerkstandort mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6cf2f-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6cf2f-178">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6cf2f-179">Führen Sie das Cmdlet Set-CsNetworkSite aus, um Netzwerkstandorte zu ändern:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="6cf2f-180">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-180">For example:</span></span>
    
   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="6cf2f-181">In diesem Beispiel wird die Website aufgerufen "Albuquerque" in der netzwerkregion "NorthAmerica" verschoben.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="6cf2f-182">Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet Set-CsNetworkSite mit dem Parameter BWPolicyProfileID oder LocationPolicy ausführen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cf2f-p110">Wenngleich der Parameter BypassID für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span> 
  
3. <span data-ttu-id="6cf2f-185">Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>
    
### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cf2f-186">So ändern Sie einen Netzwerkstandort mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6cf2f-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6cf2f-187">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-187">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6cf2f-188">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-188">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cf2f-189">Klicken Sie auf die Navigationsschaltfläche **Standort**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-189">Click the **Site** navigation button.</span></span>
    
4. <span data-ttu-id="6cf2f-190">Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-190">In the table, click the network site that you want to modify.</span></span>
    
5. <span data-ttu-id="6cf2f-191">Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-191">Click **Edit**, and then click **Show details…**.</span></span>
    
6. <span data-ttu-id="6cf2f-192">Ändern Sie auf der Seite **Standort bearbeiten** die Werte für dieses Netzwerkstandorts Einstellungen wie gewünscht ab.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>
    
7. <span data-ttu-id="6cf2f-193">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-193">Click **Commit**.</span></span>
    
8. <span data-ttu-id="6cf2f-194">Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>
    
## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="6cf2f-195">Zuordnen eines Subnetzes zu einem Netzwerkstandort</span><span class="sxs-lookup"><span data-stu-id="6cf2f-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="6cf2f-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="6cf2f-196"></span></span>

<span data-ttu-id="6cf2f-197">Jedes Subnetz in Ihrem Netzwerk muss einem bestimmten Netzwerkstandort zugeordnet sein, da mithilfe von Subnetzinformationen der Netzwerkstandort ermittelt wird, an dem sich ein Endpunkt befindet, während eine neuen Sitzung initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="6cf2f-198">Wenn Sie der Speicherort der einzelnen Parteien in einer Sitzung bekannt ist, routing oder erweiterte Enterprise-VoIP-Funktionen können anwenden, Informationen zur Bestimmung der Einrichtung des Anrufs Behandlung von.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>
  
<span data-ttu-id="6cf2f-199">Alle konfigurierten öffentlichen IP-Adressen der Audio-Video-Edgeserver in Ihrer Bereitstellung müssen den Netzwerkkonfigurationseinstellungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="6cf2f-200">Diese IP-Adressen werden als Subnetze mit der Maske 32 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="6cf2f-201">Der zugeordnete Netzwerkstandort muss dem jeweiligen konfigurierten Netzwerkstandort entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="6cf2f-202">Angenommen, die öffentliche IP-Adresse, die dem A entspricht / V-edgedienst im zentralen Standort Chicago wäre NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>
  
### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cf2f-203">Um ein Subnetz einem Netzwerkstandort zuzuordnen mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="6cf2f-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6cf2f-204">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6cf2f-205">Führen Sie das Cmdlet **New-csnetworksubnet aus** , um ein Subnetz einem Netzwerkstandort zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="6cf2f-206">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-206">For example:</span></span>
     
   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="6cf2f-207">In diesem Beispiel haben Sie eine Zuordnung zwischen dem Subnetz 172.11.12.13 und dem Netzwerkstandort "Chicago" erstellt.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>
    
3. <span data-ttu-id="6cf2f-208">Wiederholen Sie Schritt 2 für alle Subnetze in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-208">Repeat step 2 for all subnets in your topology.</span></span>
    
### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="6cf2f-209">So ordnen Sie Subnetze durch Importieren einer CSV-Datei Netzwerkstandorten zu</span><span class="sxs-lookup"><span data-stu-id="6cf2f-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="6cf2f-p113">Erstellen Sie eine CSV-Datei, die alle Subnetze enthält, die Sie hinzufügen möchten. Erstellen Sie beispielsweise die Datei **Subnetz.csv** mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
     `IPAddress, mask, description, NetworkSiteID`
    
     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`
    
2. <span data-ttu-id="6cf2f-212">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6cf2f-213">Führen Sie zum Importieren der **Datei Subnetz.csv**das folgende Cmdlet aus, und speichern Sie ihren Inhalt im Verwaltungsspeicher von Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cf2f-214">Um ein Subnetz mithilfe von Skype Business Server-Systemsteuerung einem Netzwerkstandort zuzuordnen</span><span class="sxs-lookup"><span data-stu-id="6cf2f-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6cf2f-215">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-215">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="6cf2f-216">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-216">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cf2f-217">Klicken Sie auf die Navigationsschaltfläche **Subnetz**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-217">Click the **Subnet** navigation button.</span></span>
    
4. <span data-ttu-id="6cf2f-218">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-218">Click **New**.</span></span>
    
5. <span data-ttu-id="6cf2f-219">Klicken Sie auf der Seite **Neues Subnetz** auf **Subnetz-ID** und geben Sie dann die erste Adresse in den IP-Adressbereich ein, der von dem Subnetz definiert wird, das Sie einem Netzwerkstandort zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>
    
6. <span data-ttu-id="6cf2f-220">Klicken Sie auf **Maske** und geben Sie die Bitmaske für das Subnetz ein.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>
    
7. <span data-ttu-id="6cf2f-221">Klicken Sie auf **Netzwerkstandort-ID** und wählen Sie die Standort-ID des Standorts aus, dem Sie dieses Subnetz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cf2f-222">Wenn Sie noch keine Netzwerkstandorte erstellt haben, ist diese Liste leer.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="6cf2f-223">Ausführliche Informationen über das Verfahren finden Sie unter [Erstellen oder Ändern eines Netzwerkstandorts](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="6cf2f-223">For details about the procedure, see [Create or Modify a Network Site](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="6cf2f-224">Sie können auch Site-IDs für Ihre Bereitstellung durch Ausführen des Cmdlets **Get-CsNetworkSite** abrufen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="6cf2f-225">Weitere Informationen hierzu finden Sie unter der Skype Business Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>
  
8. <span data-ttu-id="6cf2f-226">Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Subnetzes ein.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>
    
9. <span data-ttu-id="6cf2f-227">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-227">Click **Commit**.</span></span>
    
<span data-ttu-id="6cf2f-228">Wiederholen Sie diese Schritte, um einem Netzwerkstandort weitere Subnetze hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="6cf2f-229">Eine Warnung Key Health Indicator (KHI) wird ausgelöst, Angeben einer Liste von IP-Adressen, die in Ihrem Netzwerk vorhanden sind, aber entweder nicht zugeordnet sind ein Subnetz, oder das Subnetz, das die IP-Adressen ist keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="6cf2f-230">Diese Warnung wird innerhalb einer 8-Stunden-Zeitraum nicht mehr als einmal ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-230">This alert will not be raised more than once within an 8-hour period.</span></span> 
  
<span data-ttu-id="6cf2f-231">Die entsprechenden alert Informationen und ein Beispiel lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-231">The relevant alert information and an example are as follows:</span></span>
  
 <span data-ttu-id="6cf2f-232">**Quelle**: CS-Bandbreitenrichtliniendienst (Core)</span><span class="sxs-lookup"><span data-stu-id="6cf2f-232">**Source**: CS Bandwidth Policy Service (Core)</span></span> 
  
 <span data-ttu-id="6cf2f-233">**Ereignisnummer**: 36034</span><span class="sxs-lookup"><span data-stu-id="6cf2f-233">**Event number**: 36034</span></span>
  
 <span data-ttu-id="6cf2f-234">**Ebene**: 2</span><span class="sxs-lookup"><span data-stu-id="6cf2f-234">**Level**: 2</span></span>
  
 <span data-ttu-id="6cf2f-235">**Beschreibung**: die Subnetze für die folgenden IP-Adressen: \<Liste der IP-Adressen\> ist entweder nicht konfiguriert oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span> 
  
 <span data-ttu-id="6cf2f-236">**Ursache**: Die Subnetze für die zugehörigen IP-Adressen fehlen in den Netzwerkkonfigurationseinstellungen oder die Subnetze sind keinem Netzwerkstandort zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span> 
  
 <span data-ttu-id="6cf2f-237">**Lösung**: Fügen Sie gemäß der IP-Adressenliste den Netzwerkkonfigurationseinstellungen Subnetze hinzu und ordnen Sie jedes Subnetz einem Netzwerkstandort zu.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>
  
<span data-ttu-id="6cf2f-p116">Wenn die Liste der IP-Adressen beispielsweise die Einträge 10.121.248.226 und 10.121.249.20 enthält, sind diese IP-Adressen entweder keinem Subnetz zugeordnet oder das zugeordnete Subnetz gehört keinem Netzwerkstandort an. Wenn die zugehörigen Subnetze für diese Adressen 10.121.248.0/24 und 10.121.249.0/24 lauten, können Sie das Problem wie folgt lösen:</span><span class="sxs-lookup"><span data-stu-id="6cf2f-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>
  
1. <span data-ttu-id="6cf2f-240">Stellen Sie sicher, dass die IP-Adresse 10.121.248.226 dem Subnetz 10.121.248.0/24 und die IP-Adresse 10.121.249.20 dem Subnetz 10.121.249.0/24 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>
    
2. <span data-ttu-id="6cf2f-241">Stellen Sie sicher, dass die Subnetze 10.121.248.0/24 und 10.121.249.0/24 jeweils einem Netzwerkstandort zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6cf2f-242">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6cf2f-242">See also</span></span>
<span data-ttu-id="6cf2f-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="6cf2f-243"></span></span>


[<span data-ttu-id="6cf2f-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6cf2f-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="6cf2f-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6cf2f-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="6cf2f-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6cf2f-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="6cf2f-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6cf2f-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)
  
[<span data-ttu-id="6cf2f-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6cf2f-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)
  
[<span data-ttu-id="6cf2f-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6cf2f-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)
  
[<span data-ttu-id="6cf2f-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6cf2f-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)
  
[<span data-ttu-id="6cf2f-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6cf2f-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

