---
title: Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams konfigurieren.
ms.openlocfilehash: 03eaeac1bce07cffa7dc000f964f080361a37d40
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539625"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="7f172-103">Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f172-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="7f172-104">Wenn in Ihrer Organisation [standortbasiertes Routing für direktes Routing](location-based-routing-plan.md) oder [dynamische Notrufe](configure-dynamic-emergency-calling.md)bereitgestellt wird, müssen Sie die Netzwerkeinstellungen für die Verwendung dieser Cloud-Sprachfeatures in Microsoft Teams konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7f172-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="7f172-105">Netzwerkeinstellungen werden verwendet, um den Standort eines Teams-Clients zu ermitteln und netzwerkregionen, Netzwerk Websites, Subnetze und vertrauenswürdige IP-Adressen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="7f172-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="7f172-106">Je nach der von Ihnen bereitgestellten Cloud-Sprachfunktion und-Funktion konfigurieren Sie einige oder alle dieser Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7f172-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="7f172-107">Weitere Informationen zu diesen Begriffen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7f172-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="7f172-108">Sie konfigurieren die Netzwerkeinstellungen auf der Seite **Netzwerktopologie** des Microsoft Teams admin Centers oder mithilfe von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f172-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7f172-109">Konfigurieren von Netzwerkeinstellungen im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="7f172-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="7f172-110">Sie definieren netzwerkregionen, Netzwerk Websites und Subnetze auf der Registerkarte **Netzwerk Websites** auf der Seite **Netzwerktopologie** .</span><span class="sxs-lookup"><span data-stu-id="7f172-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="7f172-111">Hier können Sie eine Netzwerk Website erstellen oder ändern, eine Website mit einem Netzwerkbereich verknüpfen, der Website ein Subnetz zuordnen, standortbasiertes Routing aktivieren und der Website Notfall Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f172-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="7f172-112">Sie können auch netzwerkregionen hinzufügen, die für alle Websites Global verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7f172-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="7f172-113">Hinzufügen und Konfigurieren einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="7f172-113">Add and configure a network site</span></span>

1. <span data-ttu-id="7f172-114">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Netzwerk Websites** .</span><span class="sxs-lookup"><span data-stu-id="7f172-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="7f172-115">Klicken Sie auf **Hinzufügen**, und geben Sie dann einen Namen und eine Beschreibung für die Website ein.</span><span class="sxs-lookup"><span data-stu-id="7f172-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Screenshot der Seite "Netzwerk Website hinzufügen"](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="7f172-117">Wenn Sie die Website einem Netzwerkbereich zuordnen möchten, klicken Sie auf **Netzwerkbereich hinzufügen**, wählen Sie einen vorhandenen Bereich aus, oder klicken Sie auf **hinzu** fügen, um einen Bereich hinzuzufügen, und klicken Sie dann auf **Verknüpfen**.</span><span class="sxs-lookup"><span data-stu-id="7f172-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="7f172-118">Um standortbasiertes Routing für die Website zu aktivieren, aktivieren Sie **standortbasiertes Routing**.</span><span class="sxs-lookup"><span data-stu-id="7f172-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="7f172-119">Führen Sie eine oder beide der folgenden Aktionen aus, um der Website Notfalldienst Richtlinien zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="7f172-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="7f172-120">Wenn in Ihrer Organisation Anrufpläne oder ein direktes Routing für das Telefon System verwendet wird, wählen Sie unter **Notruf Richtlinie**die gewünschte Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="7f172-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="7f172-121">Wenn Ihre Organisation ein direktes Routing für Telefonsysteme bereitgestellt hat, wählen Sie unter **Notfall Routing Richtlinie**die gewünschte Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="7f172-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="7f172-122">Wenn Sie der Website ein Subnetz zuordnen möchten, klicken Sie unter **Subnetze**auf **Subnets hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7f172-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="7f172-123">Geben Sie die IP-Version, die IP-Adresse, den Netzwerkbereich an, fügen Sie eine Beschreibung hinzu, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="7f172-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="7f172-124">Jedes Subnetz muss einer bestimmten Website zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="7f172-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="7f172-125">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f172-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="7f172-126">Ändern einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="7f172-126">Modify a network site</span></span>

1. <span data-ttu-id="7f172-127">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Netzwerk Websites** .</span><span class="sxs-lookup"><span data-stu-id="7f172-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="7f172-128">Wählen Sie die Website aus, indem Sie links neben dem Websitenamen klicken, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f172-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="7f172-129">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **speichern.**</span><span class="sxs-lookup"><span data-stu-id="7f172-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="7f172-130">Verwalten externer vertrauenswürdiger IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="7f172-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="7f172-131">Sie verwalten externe vertrauenswürdige IP-Adressen auf der Registerkarte **Vertrauenswürdige IPS** auf der Seite **Netzwerktopologie** des Microsoft Teams admin Centers.</span><span class="sxs-lookup"><span data-stu-id="7f172-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="7f172-132">Sie können eine unbegrenzte Anzahl externer vertrauenswürdiger IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7f172-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="7f172-133">Hinzufügen einer vertrauenswürdigen IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="7f172-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="7f172-134">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Vertrauenswürdige IPS** .</span><span class="sxs-lookup"><span data-stu-id="7f172-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="7f172-135">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="7f172-135">Click **New**.</span></span>
3. <span data-ttu-id="7f172-136">Geben Sie im Bereich **Vertrauenswürdige IP-Adresse hinzufügen** die IP-Version, die IP-Adresse, den Netzwerkbereich und eine Beschreibung ein, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="7f172-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Screenshot des Bereichs "Vertrauenswürdige IP-Adresse hinzufügen"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="7f172-138">Bearbeiten einer vertrauenswürdigen IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="7f172-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="7f172-139">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Standorte**-  >  **Netzwerktopologie**, und klicken Sie dann auf die Registerkarte **Vertrauenswürdige IPS** .</span><span class="sxs-lookup"><span data-stu-id="7f172-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="7f172-140">Wählen Sie die IP-Adresse aus, indem Sie links davon klicken, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7f172-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="7f172-141">Nehmen Sie im Bereich **Vertrauenswürdige IP-Adresse bearbeiten** die gewünschten Änderungen vor, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="7f172-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="7f172-142">Konfigurieren von Netzwerkeinstellungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f172-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="7f172-143">Zum Ausführen der Schritte in diesem Abschnitt benötigen Sie einige Vertrautheit mit PowerShell-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="7f172-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="7f172-144">Weitere Informationen finden Sie unter [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7f172-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="7f172-145">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="7f172-145">Define network regions</span></span>

 <span data-ttu-id="7f172-146">Verwenden Sie das Cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) , um netzwerkregionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7f172-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="7f172-147">Beachten Sie, dass der Parameter "Regions-ID" ein logischer Name ist, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist, und der CentralSite- &lt; Parameter der Website-ID &gt; optional ist.</span><span class="sxs-lookup"><span data-stu-id="7f172-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="7f172-148">In diesem Beispiel erstellen wir eine netzwerkregion mit dem Namen Indien.</span><span class="sxs-lookup"><span data-stu-id="7f172-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="7f172-149">Siehe auch [Satz-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span><span class="sxs-lookup"><span data-stu-id="7f172-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="7f172-150">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="7f172-150">Define network sites</span></span>

<span data-ttu-id="7f172-151">Verwenden Sie das Cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) , um Netzwerk Websites zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7f172-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="7f172-152">Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="7f172-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="7f172-153">In diesem Beispiel erstellen wir zwei neue Netzwerkstandorte, Delhi und Hyderabad, in der Region Indien.</span><span class="sxs-lookup"><span data-stu-id="7f172-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="7f172-154">In der folgenden Tabelle sind die Netzwerk Websites aufgeführt, die in diesem Beispiel definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7f172-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="7f172-155">Website 1</span><span class="sxs-lookup"><span data-stu-id="7f172-155">Site 1</span></span> |<span data-ttu-id="7f172-156">Website 2</span><span class="sxs-lookup"><span data-stu-id="7f172-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="7f172-157">Website-ID</span><span class="sxs-lookup"><span data-stu-id="7f172-157">Site ID</span></span>    |    <span data-ttu-id="7f172-158">Website 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="7f172-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="7f172-159">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="7f172-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="7f172-160">Regions-ID</span><span class="sxs-lookup"><span data-stu-id="7f172-160">Region ID</span></span>  |     <span data-ttu-id="7f172-161">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="7f172-161">Region 1 (India)</span></span>    |   <span data-ttu-id="7f172-162">Region 1 (Indien)</span><span class="sxs-lookup"><span data-stu-id="7f172-162">Region 1 (India)</span></span>      |

<span data-ttu-id="7f172-163">Siehe auch [Satz-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span><span class="sxs-lookup"><span data-stu-id="7f172-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="7f172-164">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="7f172-164">Define network subnets</span></span>

<span data-ttu-id="7f172-165">Verwenden Sie das Cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) , um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="7f172-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="7f172-166">Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="7f172-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="7f172-167">In diesem Beispiel erstellen wir eine Zuordnung zwischen Subnetz-192.168.0.0 und der Delhi-Netzwerk Website und zwischen Subnetz 2001:4898: E8:25:844E: 926f: 85ad: dd8e und der Hyderabad-Netzwerk Website.</span><span class="sxs-lookup"><span data-stu-id="7f172-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="7f172-168">In der folgenden Tabelle sind die in diesem Beispiel definierten Subnets aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f172-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="7f172-169">Website 1</span><span class="sxs-lookup"><span data-stu-id="7f172-169">Site 1</span></span> |<span data-ttu-id="7f172-170">Website 2</span><span class="sxs-lookup"><span data-stu-id="7f172-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="7f172-171">Subnet-ID</span><span class="sxs-lookup"><span data-stu-id="7f172-171">Subnet ID</span></span>   |    <span data-ttu-id="7f172-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="7f172-172">192.168.0.0</span></span>     |  <span data-ttu-id="7f172-173">2001:4898: E8:25:844E: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="7f172-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="7f172-174">Format</span><span class="sxs-lookup"><span data-stu-id="7f172-174">Mask</span></span>  |     <span data-ttu-id="7f172-175">24</span><span class="sxs-lookup"><span data-stu-id="7f172-175">24</span></span>    |   <span data-ttu-id="7f172-176">120</span><span class="sxs-lookup"><span data-stu-id="7f172-176">120</span></span>      |
|<span data-ttu-id="7f172-177">Website-ID</span><span class="sxs-lookup"><span data-stu-id="7f172-177">Site ID</span></span>  | <span data-ttu-id="7f172-178">Website (Delhi)</span><span class="sxs-lookup"><span data-stu-id="7f172-178">Site (Delhi)</span></span> | <span data-ttu-id="7f172-179">Website 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="7f172-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="7f172-180">Bei mehreren Subnetzen können Sie eine CSV-Datei mit einem Skript wie dem folgenden importieren.</span><span class="sxs-lookup"><span data-stu-id="7f172-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="7f172-181">In diesem Beispiel sieht die CSV-Datei etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7f172-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="7f172-182">Siehe auch [Satz-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span><span class="sxs-lookup"><span data-stu-id="7f172-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="7f172-183">Definieren externer Subnetze (externe vertrauenswürdige IP-Adressen)</span><span class="sxs-lookup"><span data-stu-id="7f172-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="7f172-184">Verwenden Sie das Cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) , um externe Subnetze zu definieren und dem Mandanten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7f172-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="7f172-185">Sie können eine unbegrenzte Anzahl von externen Subnetzen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="7f172-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="7f172-186">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7f172-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="7f172-187">Siehe auch [Satz-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span><span class="sxs-lookup"><span data-stu-id="7f172-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f172-188">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7f172-188">Related topics</span></span>

- [<span data-ttu-id="7f172-189">Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams</span><span class="sxs-lookup"><span data-stu-id="7f172-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
