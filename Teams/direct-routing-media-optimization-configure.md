---
title: Direkte Weiterleitung der lokalen Medienoptimierung
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Konfigurieren der lokalen Medienoptimierung für das direkte Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3da3cf243b24d0f614c05e9d09eb68796a68545
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256490"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="e17e5-103">Konfigurieren der lokalen Medienoptimierung für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="e17e5-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="e17e5-104">Die Konfiguration für die lokale Medienoptimierung basiert auf Netzwerkeinstellungen, die anderen Cloud-Sprachfeatures, wie standortbasiertes Routing und dynamische Notrufe, gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="e17e5-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="e17e5-105">Weitere Informationen zu netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetzen und vertrauenswürdigen IP-Adressen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e17e5-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e17e5-106">Bevor Sie die lokale Medienoptimierung konfigurieren, lesen Sie [lokale Medienoptimierung für direktes Routing](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="e17e5-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="e17e5-107">Zum Konfigurieren der lokalen Medienoptimierung sind die folgenden Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e17e5-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="e17e5-108">Sie können das Team Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="e17e5-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="e17e5-109">Ausführliche Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="e17e5-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="e17e5-110">Konfigurieren Sie den Benutzer und die SBC-Websites (wie in diesem Artikel beschrieben).</span><span class="sxs-lookup"><span data-stu-id="e17e5-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="e17e5-111">Konfigurieren Sie die SBCS für die lokale Medienoptimierung (gemäß ihrer SBC-Herstellerspezifikation).</span><span class="sxs-lookup"><span data-stu-id="e17e5-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="e17e5-112">Das folgende Diagramm zeigt die Netzwerkeinrichtung, die in den Beispielen in diesem Artikel verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e17e5-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="e17e5-113">![Diagramm mit Netzwerk Setup für Beispiele](media/direct-routing-media-op-9.png "Netzwerk-Setup für Beispiele")</span><span class="sxs-lookup"><span data-stu-id="e17e5-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="e17e5-114">Konfigurieren des Benutzers und der SBC-Websites</span><span class="sxs-lookup"><span data-stu-id="e17e5-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="e17e5-115">Wenn Sie den Benutzer und die SBC-Websites konfigurieren möchten, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="e17e5-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="e17e5-116">[Verwalten externer vertrauenswürdiger IP-Adressen](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="e17e5-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="e17e5-117">[Definieren Sie die Netzwerktopologie](#define-the-network-topology) , indem Sie die netzwerkregionen, Netzwerkstandorte und Netzwerk-Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e17e5-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="e17e5-118">[Definieren Sie die virtuelle Netzwerktopologie](#define-the-virtual-network-topology) , indem Sie SBC (s) den Websites mit relevanten Modi und Proxy-SBC-Werten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e17e5-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="e17e5-119">Konfigurieren von SBC (s) für die lokale Medienoptimierung gemäß der SBC-Herstellerspezifikation</span><span class="sxs-lookup"><span data-stu-id="e17e5-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="e17e5-120">In diesem Artikel wird die Konfiguration für Microsoft-Komponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e17e5-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="e17e5-121">Informationen zur SBC-Konfiguration finden Sie in der Dokumentation Ihres SBC-Herstellers.</span><span class="sxs-lookup"><span data-stu-id="e17e5-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="e17e5-122">Die lokale Medienoptimierung wird von den folgenden SBC-Anbietern unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="e17e5-123">Anbieter</span><span class="sxs-lookup"><span data-stu-id="e17e5-123">Vendor</span></span> | <span data-ttu-id="e17e5-124">Produkt</span><span class="sxs-lookup"><span data-stu-id="e17e5-124">Product</span></span> |    <span data-ttu-id="e17e5-125">Software Version</span><span class="sxs-lookup"><span data-stu-id="e17e5-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="e17e5-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e17e5-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="e17e5-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="e17e5-128">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="e17e5-130">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="e17e5-132">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="e17e5-134">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-135">Mediant-1000B-SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="e17e5-136">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="e17e5-138">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="e17e5-140">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e17e5-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="e17e5-142">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e17e5-142">7.20A.256</span></span> |
| [<span data-ttu-id="e17e5-143">Menüband-SBC-Kern</span><span class="sxs-lookup"><span data-stu-id="e17e5-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="e17e5-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="e17e5-144">SBC 5110</span></span>         | <span data-ttu-id="e17e5-145">8,2</span><span class="sxs-lookup"><span data-stu-id="e17e5-145">8.2</span></span>  |
|            |  <span data-ttu-id="e17e5-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="e17e5-146">SBC 5210</span></span>         | <span data-ttu-id="e17e5-147">8,2</span><span class="sxs-lookup"><span data-stu-id="e17e5-147">8.2</span></span>  |
|            |  <span data-ttu-id="e17e5-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="e17e5-148">SBC 5400</span></span>         | <span data-ttu-id="e17e5-149">8,2</span><span class="sxs-lookup"><span data-stu-id="e17e5-149">8.2</span></span>  |
|            |  <span data-ttu-id="e17e5-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="e17e5-150">SBC 7000</span></span>         | <span data-ttu-id="e17e5-151">8,2</span><span class="sxs-lookup"><span data-stu-id="e17e5-151">8.2</span></span>  |
|            |  <span data-ttu-id="e17e5-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="e17e5-152">SBC SWe</span></span>          | <span data-ttu-id="e17e5-153">8,2</span><span class="sxs-lookup"><span data-stu-id="e17e5-153">8.2</span></span>  |
| [<span data-ttu-id="e17e5-154">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="e17e5-154">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="e17e5-155">anynode</span><span class="sxs-lookup"><span data-stu-id="e17e5-155">anynode</span></span>          | <span data-ttu-id="e17e5-156">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="e17e5-156">4.0.1+</span></span> |
| [<span data-ttu-id="e17e5-157">Oracle</span><span class="sxs-lookup"><span data-stu-id="e17e5-157">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="e17e5-158">AP 1100</span><span class="sxs-lookup"><span data-stu-id="e17e5-158">AP 1100</span></span> | <span data-ttu-id="e17e5-159">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e17e5-159">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="e17e5-160">AP 3900</span><span class="sxs-lookup"><span data-stu-id="e17e5-160">AP 3900</span></span> | <span data-ttu-id="e17e5-161">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e17e5-161">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="e17e5-162">AP 4600</span><span class="sxs-lookup"><span data-stu-id="e17e5-162">AP 4600</span></span> | <span data-ttu-id="e17e5-163">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e17e5-163">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="e17e5-164">AP 6300</span><span class="sxs-lookup"><span data-stu-id="e17e5-164">AP 6300</span></span> | <span data-ttu-id="e17e5-165">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e17e5-165">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="e17e5-166">AP 6350</span><span class="sxs-lookup"><span data-stu-id="e17e5-166">AP 6350</span></span> | <span data-ttu-id="e17e5-167">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e17e5-167">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="e17e5-168">VME</span><span class="sxs-lookup"><span data-stu-id="e17e5-168">VME</span></span>     | <span data-ttu-id="e17e5-169">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e17e5-169">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="e17e5-170">Verwalten externer vertrauenswürdiger IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="e17e5-170">Manage external trusted IP addresses</span></span>

<span data-ttu-id="e17e5-171">Externe vertrauenswürdige IPS sind die Internet externen IPS des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="e17e5-171">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="e17e5-172">Diese IP-Adressen sind die IP-Adressen, die von Microsoft Teams-Clients verwendet werden, wenn Sie eine Verbindung mit Microsoft 365 herstellen.</span><span class="sxs-lookup"><span data-stu-id="e17e5-172">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="e17e5-173">Sie müssen diese externen IPS für jede Website hinzufügen, auf der Benutzer die lokale Medienoptimierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e17e5-173">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="e17e5-174">Wenn Sie die öffentlichen IP-Adressen für jede Website hinzufügen möchten, verwenden Sie das Cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="e17e5-174">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="e17e5-175">Sie können eine unbegrenzte Anzahl von vertrauenswürdigen IP-Adressen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="e17e5-175">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="e17e5-176">Wenn die von Microsoft 365 gesehenen externen IPS sowohl IPv4-als auch IPv6-Adressen sind, müssen Sie beide Typen von IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e17e5-176">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="e17e5-177">Verwenden Sie für IPv4 Maske 32.</span><span class="sxs-lookup"><span data-stu-id="e17e5-177">For IPv4, use mask 32.</span></span> <span data-ttu-id="e17e5-178">Verwenden Sie für IPv6 die Maske 128.</span><span class="sxs-lookup"><span data-stu-id="e17e5-178">For IPv6, use mask 128.</span></span> <span data-ttu-id="e17e5-179">Sie können sowohl einzelne externe IP-Adressen als auch externe IP-Subnetze hinzufügen, indem Sie unterschiedliche MaskBits für das Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="e17e5-179">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="e17e5-180">Beispiel für das Hinzufügen von vertrauenswürdigen IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="e17e5-180">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="e17e5-181">Definieren der Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="e17e5-181">Define the network topology</span></span>

<span data-ttu-id="e17e5-182">In diesem Abschnitt wird beschrieben, wie Sie die netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze für Ihre Netzwerktopologie definieren.</span><span class="sxs-lookup"><span data-stu-id="e17e5-182">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="e17e5-183">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, daher müssen Sie sicherstellen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e17e5-183">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="e17e5-184">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="e17e5-184">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="e17e5-185">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="e17e5-185">Define network regions</span></span>

<span data-ttu-id="e17e5-186">Verwenden Sie zum Definieren von netzwerkregionen das Cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="e17e5-186">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="e17e5-187">Der Parameter Regions-Nr ist ein logischer Name, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="e17e5-187">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="e17e5-188">Der CentralSite <site ID> -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e17e5-188">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="e17e5-189">Im folgenden Beispiel wird eine netzwerkregion mit dem Namen APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-189">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="e17e5-190">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="e17e5-190">Define network sites</span></span>

<span data-ttu-id="e17e5-191">Verwenden Sie zum Definieren von Netzwerk Websites das Cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="e17e5-191">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="e17e5-192">Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="e17e5-192">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="e17e5-193">Im folgenden Beispiel werden drei neue Netzwerk Websites, Vietnam, Indonesien und Singapur, in der Region APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-193">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="e17e5-194">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="e17e5-194">Define network subnets</span></span>

<span data-ttu-id="e17e5-195">Verwenden Sie das Cmdlet New-CsTenantNetworkSubnet, um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e17e5-195">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="e17e5-196">Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e17e5-196">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="e17e5-197">Im folgenden Beispiel werden drei Netzwerk-Subnetze definiert und den drei Netzwerkstandorten zugeordnet: Vietnam, Indonesien und Singapur:</span><span class="sxs-lookup"><span data-stu-id="e17e5-197">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="e17e5-198">Definieren der virtuellen Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="e17e5-198">Define the virtual network topology</span></span> 

<span data-ttu-id="e17e5-199">Zunächst erstellt der mandantenadministrator mithilfe des Cmdlets New-CsOnlinePSTNGateway eine neue SBC-Konfiguration für jeden relevanten SBC.</span><span class="sxs-lookup"><span data-stu-id="e17e5-199">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="e17e5-200">Der mandantenadministrator definiert die virtuelle Netzwerktopologie, indem er die Netzwerk Websites für die PSTN-Gateway-Objekte mit dem Cmdlet "CsOnlinePSTNGateway" angibt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-200">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="e17e5-201">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e17e5-201">Note the following:</span></span> 
   - <span data-ttu-id="e17e5-202">Wenn der Kunde über einen einzelnen SBC verfügt, muss der-ProxySBC-Parameter entweder obligatorisch $NULL oder SBC-FQDN-Wert sein (zentrales SBC-Szenario mit zentralisierten Trunks).</span><span class="sxs-lookup"><span data-stu-id="e17e5-202">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="e17e5-203">Der-MediaBypass-Parameter muss auf $true eingestellt sein, um die lokale Medienoptimierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e17e5-203">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="e17e5-204">Wenn der SBC-BypassMode-Parametersatz nicht vorhanden ist, werden keine X-MS-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-204">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="e17e5-205">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie den gleichen Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e17e5-205">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="e17e5-206">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="e17e5-206">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="e17e5-207">Im folgenden Beispiel werden drei SBCS zu den Netzwerkstandorten Vietnam, Indonesien und Singapur im Bereich APAC mit dem Modus immer umgehen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-207">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="e17e5-208">Hinweis: um unterbrechungsfreie Vorgänge zu gewährleisten, wenn die lokale Medienoptimierung und standortbasiertes Routing (LBR) gleichzeitig konfiguriert sind, muss Downstream-SBCS für LBR aktiviert werden, indem der GatewaySiteLbrEnabled-Parameter für jeden Downstream-SBC auf $true festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e17e5-208">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="e17e5-209">(Diese Einstellung ist für den Proxy-SBC nicht zwingend erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="e17e5-209">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="e17e5-210">Basierend auf den oben aufgeführten Informationen umfasst das direkte Routing drei proprietäre SIP-Header für SIP-Einladungen und erneute Einladungen, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e17e5-210">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="e17e5-211">X-MS-Header, die beim direkten Routing bei Einladungen und erneuten Einladungen eingeführt werden, wenn BypassMode definiert ist:</span><span class="sxs-lookup"><span data-stu-id="e17e5-211">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="e17e5-212">Header Name</span><span class="sxs-lookup"><span data-stu-id="e17e5-212">Header name</span></span> | <span data-ttu-id="e17e5-213">Werte</span><span class="sxs-lookup"><span data-stu-id="e17e5-213">Values</span></span> | <span data-ttu-id="e17e5-214">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e17e5-214">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="e17e5-215">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="e17e5-215">X-MS-UserLocation</span></span> | <span data-ttu-id="e17e5-216">intern/extern</span><span class="sxs-lookup"><span data-stu-id="e17e5-216">internal/external</span></span> | <span data-ttu-id="e17e5-217">Gibt an, ob der Benutzer intern oder extern ist</span><span class="sxs-lookup"><span data-stu-id="e17e5-217">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="e17e5-218">Request-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="e17e5-218">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="e17e5-219">SBC-FQDN</span><span class="sxs-lookup"><span data-stu-id="e17e5-219">SBC FQDN</span></span> | <span data-ttu-id="e17e5-220">Der FQDN, der für den Anruf vorgesehen ist, auch wenn der SBC nicht direkt mit dem direkten Routing verbunden ist</span><span class="sxs-lookup"><span data-stu-id="e17e5-220">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="e17e5-221">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="e17e5-221">X-MS-MediaPath</span></span> | <span data-ttu-id="e17e5-222">Beispiel: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-222">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="e17e5-223">Die Reihenfolge der SBCS, die für den Medienpfad zwischen dem Benutzer und dem Ziel-SBC verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e17e5-223">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="e17e5-224">Der endgültige SBC ist immer der letzte.</span><span class="sxs-lookup"><span data-stu-id="e17e5-224">The final SBC is always last</span></span> |
| <span data-ttu-id="e17e5-225">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="e17e5-225">X-MS-UserSite</span></span> | <span data-ttu-id="e17e5-226">usersiteID</span><span class="sxs-lookup"><span data-stu-id="e17e5-226">usersiteID</span></span> | <span data-ttu-id="e17e5-227">Vom mandantenadministrator festgelegte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e17e5-227">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="e17e5-228">Anruf Flüsse</span><span class="sxs-lookup"><span data-stu-id="e17e5-228">Call flows</span></span> 

<span data-ttu-id="e17e5-229">Im folgenden werden die Anruf Flüsse für zwei Modi angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-229">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="e17e5-230">Immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e17e5-230">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="e17e5-231">Nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-231">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="e17e5-232">Modus immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e17e5-232">Always Bypass mode</span></span>

<span data-ttu-id="e17e5-233">Der Bypass-Modus ist immer die einfachste Option für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e17e5-233">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="e17e5-234">Der mandantenadministrator kann eine einzelne Website für alle Benutzer und SBCS konfigurieren, wenn alle SBCS von einer beliebigen Website aus erreichbar sind.</span><span class="sxs-lookup"><span data-stu-id="e17e5-234">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="e17e5-235">In den Beispielen wird der Modus "immer umgehen" für die folgenden Szenarien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-235">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="e17e5-236">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-236">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="e17e5-237">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-237">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="e17e5-238">Ausgehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="e17e5-238">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="e17e5-239">Eingehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="e17e5-239">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="e17e5-240">In der folgenden Tabelle sind die in den Beispielen verwendeten FQDN-und IP-Adressen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e17e5-240">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="e17e5-241">FQDN</span><span class="sxs-lookup"><span data-stu-id="e17e5-241">FQDN</span></span> | <span data-ttu-id="e17e5-242">Externe SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e17e5-242">SBC external IP address</span></span> | <span data-ttu-id="e17e5-243">Interne SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e17e5-243">SBC internal IP Address</span></span> | <span data-ttu-id="e17e5-244">Internes Subnetz</span><span class="sxs-lookup"><span data-stu-id="e17e5-244">Internal subnet</span></span> | <span data-ttu-id="e17e5-245">Ort</span><span class="sxs-lookup"><span data-stu-id="e17e5-245">Location</span></span> | <span data-ttu-id="e17e5-246">Externe NAT (vertrauenswürdige IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="e17e5-246">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-247">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-247">VNsbc.contoso.com</span></span> | <span data-ttu-id="e17e5-248">Keine</span><span class="sxs-lookup"><span data-stu-id="e17e5-248">None</span></span> | <span data-ttu-id="e17e5-249">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="e17e5-249">192.168.1.5</span></span> | <span data-ttu-id="e17e5-250">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="e17e5-250">192.168.1.0/24</span></span> | <span data-ttu-id="e17e5-251">Vietnam</span><span class="sxs-lookup"><span data-stu-id="e17e5-251">Vietnam</span></span> | <span data-ttu-id="e17e5-252">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="e17e5-252">172.16.240.110</span></span> |
| <span data-ttu-id="e17e5-253">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-253">IDsbc.contoso.com</span></span> | <span data-ttu-id="e17e5-254">Keine</span><span class="sxs-lookup"><span data-stu-id="e17e5-254">None</span></span> | <span data-ttu-id="e17e5-255">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="e17e5-255">192.168.2.5</span></span> | <span data-ttu-id="e17e5-256">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="e17e5-256">192.168.2.0/24</span></span> | <span data-ttu-id="e17e5-257">Indonesien</span><span class="sxs-lookup"><span data-stu-id="e17e5-257">Indonesia</span></span> | <span data-ttu-id="e17e5-258">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="e17e5-258">172.16.240.120</span></span> |
| <span data-ttu-id="e17e5-259">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-259">proxysbc.contoso.com</span></span> | <span data-ttu-id="e17e5-260">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="e17e5-260">172.16.240.133</span></span> | <span data-ttu-id="e17e5-261">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="e17e5-261">192.168.3.5</span></span> | <span data-ttu-id="e17e5-262">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="e17e5-262">192.168.3.0/24</span></span> | <span data-ttu-id="e17e5-263">Singapur</span><span class="sxs-lookup"><span data-stu-id="e17e5-263">Singapore</span></span> | <span data-ttu-id="e17e5-264">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="e17e5-264">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="e17e5-265">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-265">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="e17e5-266">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-266">Mode</span></span> |    <span data-ttu-id="e17e5-267">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-267">User</span></span> |  <span data-ttu-id="e17e5-268">Ort</span><span class="sxs-lookup"><span data-stu-id="e17e5-268">Location</span></span> |  <span data-ttu-id="e17e5-269">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-269">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="e17e5-270">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-270">AlwaysBypass</span></span> |    <span data-ttu-id="e17e5-271">Intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-271">Internal</span></span> |  <span data-ttu-id="e17e5-272">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-272">The same site as SBC</span></span> |  <span data-ttu-id="e17e5-273">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e17e5-273">Outbound</span></span> |

<span data-ttu-id="e17e5-274">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="e17e5-274">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="e17e5-275">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e17e5-275">User physical location</span></span>| <span data-ttu-id="e17e5-276">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="e17e5-276">User makes or receives a call to/from number</span></span> | <span data-ttu-id="e17e5-277">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e17e5-277">User phone number</span></span>  | <span data-ttu-id="e17e5-278">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e17e5-278">Online Voice Routing Policy</span></span> | <span data-ttu-id="e17e5-279">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-279">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-280">Vietnam</span><span class="sxs-lookup"><span data-stu-id="e17e5-280">Vietnam</span></span> | <span data-ttu-id="e17e5-281">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="e17e5-281">+84 4 3926 3000</span></span> | <span data-ttu-id="e17e5-282">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="e17e5-282">+84 4 5555 5555</span></span>   | <span data-ttu-id="e17e5-283">Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-283">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="e17e5-284">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-284">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="e17e5-285">VNsbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e17e5-285">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="e17e5-286">proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e17e5-286">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="e17e5-287">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit Always Bypass-Modus und den Benutzer am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e17e5-287">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="e17e5-288">![Diagramm mit ausgehenden Anrufen](media/direct-routing-media-op-10.png "Ausgehende Anrufe")</span><span class="sxs-lookup"><span data-stu-id="e17e5-288">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="e17e5-289">Die folgende Tabelle zeigt die X-MS-Kopfzeilen, die durch Direct Routing gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="e17e5-289">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="e17e5-290">Parameter</span><span class="sxs-lookup"><span data-stu-id="e17e5-290">Parameter</span></span> | <span data-ttu-id="e17e5-291">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e17e5-291">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="e17e5-292">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-292">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="e17e5-293">Der Ziel-FQDN des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet</span><span class="sxs-lookup"><span data-stu-id="e17e5-293">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="e17e5-294">X-MS-UserLocation: intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-294">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="e17e5-295">Das Feld hat angegeben, dass sich der Benutzer im Unternehmensnetzwerk befindet</span><span class="sxs-lookup"><span data-stu-id="e17e5-295">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="e17e5-296">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-296">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="e17e5-297">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="e17e5-297">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="e17e5-298">In diesem Fall, da wir immer Bypass haben und der Client intern ist, wird der Zielname als einziger Name im Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-298">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="e17e5-299">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="e17e5-299">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="e17e5-300">Das Feld, das auf der Website angegeben ist, in der sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-300">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="e17e5-301">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-301">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="e17e5-302">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-302">Mode</span></span> |    <span data-ttu-id="e17e5-303">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-303">User</span></span> |  <span data-ttu-id="e17e5-304">Ort</span><span class="sxs-lookup"><span data-stu-id="e17e5-304">Location</span></span> |  <span data-ttu-id="e17e5-305">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-305">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-306">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-306">AlwaysBypass</span></span> |    <span data-ttu-id="e17e5-307">Intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-307">Internal</span></span> | <span data-ttu-id="e17e5-308">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-308">The same site as SBC</span></span> | <span data-ttu-id="e17e5-309">Inbound</span><span class="sxs-lookup"><span data-stu-id="e17e5-309">Inbound</span></span> |


<span data-ttu-id="e17e5-310">Bei einem eingehenden Anruf ist der Standort des Benutzers unbekannt, und der SBC muss erraten, wo sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-310">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="e17e5-311">Wenn die Vermutung nicht korrekt ist, wird eine erneute Einladung benötigt.</span><span class="sxs-lookup"><span data-stu-id="e17e5-311">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="e17e5-312">In diesem Fall wird davon ausgegangen, dass der Benutzer intern ist, Medien direkt fließen können und keine weiteren Aktionen erforderlich sind (erneut einladen).</span><span class="sxs-lookup"><span data-stu-id="e17e5-312">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="e17e5-313">Der SBC, der mit dem Direct Routing-Dienst verbunden ist, meldet den ursprünglichen SBC-Standort durch Bereitstellen von Daten Satz Routen-und Kontaktfeldern.</span><span class="sxs-lookup"><span data-stu-id="e17e5-313">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="e17e5-314">Basierend auf diesen Feldern wird der Medienpfad durch direkte Weiterleitung berechnet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-314">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="e17e5-315">Hinweis: da ein Benutzer mehrere Endpunkte haben kann, ist die Unterstützung von 183 nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="e17e5-315">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="e17e5-316">Die direkte Weiterleitung wird in diesem Fall immer 180-Klingeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="e17e5-316">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="e17e5-317">Das folgende Diagramm zeigt die SIP-Leiter für eingehende Anrufe mit dem AlwaysBypass-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e17e5-317">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="e17e5-319">Ausgehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-319">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="e17e5-320">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-320">Mode</span></span> |    <span data-ttu-id="e17e5-321">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-321">User</span></span> |  <span data-ttu-id="e17e5-322">Standort</span><span class="sxs-lookup"><span data-stu-id="e17e5-322">Site</span></span> |  <span data-ttu-id="e17e5-323">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-323">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="e17e5-324">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-324">AlwaysBypass</span></span> |  <span data-ttu-id="e17e5-325">Extern</span><span class="sxs-lookup"><span data-stu-id="e17e5-325">External</span></span> |  <span data-ttu-id="e17e5-326">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e17e5-326">N/A</span></span> | <span data-ttu-id="e17e5-327">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e17e5-327">Outbound</span></span> |


<span data-ttu-id="e17e5-328">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern:</span><span class="sxs-lookup"><span data-stu-id="e17e5-328">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-12.png)

<span data-ttu-id="e17e5-330">Die folgende Tabelle zeigt die X-MS-Header, die vom Direct Routing-Dienst gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="e17e5-330">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="e17e5-331">Parameter</span><span class="sxs-lookup"><span data-stu-id="e17e5-331">Parameter</span></span> |   <span data-ttu-id="e17e5-332">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e17e5-332">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="e17e5-333">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-333">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="e17e5-334">Der Ziel-FQDN des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-334">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="e17e5-335">X-MS-UserLocation: Extern</span><span class="sxs-lookup"><span data-stu-id="e17e5-335">X-MS-UserLocation: external</span></span> | <span data-ttu-id="e17e5-336">Das Feld hat angegeben, dass der Benutzer sich außerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-336">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="e17e5-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="e17e5-338">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="e17e5-338">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="e17e5-339">In diesem Fall, da wir immer Bypass haben und der Client extern ist.</span><span class="sxs-lookup"><span data-stu-id="e17e5-339">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="e17e5-340">Eingehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-340">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="e17e5-341">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-341">Mode</span></span> | <span data-ttu-id="e17e5-342">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-342">User</span></span> | <span data-ttu-id="e17e5-343">Standort</span><span class="sxs-lookup"><span data-stu-id="e17e5-343">Site</span></span> |  <span data-ttu-id="e17e5-344">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-344">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="e17e5-345">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e17e5-345">AlwaysBypass</span></span> |  <span data-ttu-id="e17e5-346">Extern</span><span class="sxs-lookup"><span data-stu-id="e17e5-346">External</span></span> |  <span data-ttu-id="e17e5-347">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e17e5-347">N/A</span></span> |   <span data-ttu-id="e17e5-348">Inbound</span><span class="sxs-lookup"><span data-stu-id="e17e5-348">Inbound</span></span> |

<span data-ttu-id="e17e5-349">Bei einem eingehenden Anruf muss der SBC, der mit dem direkten Routing verbunden ist, eine erneute Einladung senden (Standardmäßig werden lokale Medien Kandidaten immer angeboten), wenn der Standort des Benutzers extern ist.</span><span class="sxs-lookup"><span data-stu-id="e17e5-349">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="e17e5-350">Die X-MediaPath wird basierend auf der Daten Satz Route und dem angegebenen SBC-Benutzer berechnet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-350">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="e17e5-351">Das folgende Diagramm zeigt die SIP-Leiter für einen eingehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern.</span><span class="sxs-lookup"><span data-stu-id="e17e5-351">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="e17e5-353">Nur für den lokalen Benutzermodus</span><span class="sxs-lookup"><span data-stu-id="e17e5-353">Only for local users mode</span></span>

<span data-ttu-id="e17e5-354">Lokale Medien Kandidaten des Ziel-SBC werden nur angeboten, wenn sich ein Benutzer am selben Ort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-354">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="e17e5-355">In allen anderen Fällen fließen Medien entweder über eine interne oder externe IP-Adresse des Proxy-SBC.</span><span class="sxs-lookup"><span data-stu-id="e17e5-355">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="e17e5-356">Die folgenden Szenarien werden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e17e5-356">The following scenarios are described:</span></span>

- [<span data-ttu-id="e17e5-357">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-357">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="e17e5-358">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-358">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="e17e5-359">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="e17e5-359">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="e17e5-360">Eingehende Anrufe und der Benutzer ist intern, aber nicht am selben Ort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-360">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="e17e5-361">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="e17e5-361">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="e17e5-362">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e17e5-362">User physical location</span></span> |  <span data-ttu-id="e17e5-363">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="e17e5-363">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="e17e5-364">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e17e5-364">User phone number</span></span> | <span data-ttu-id="e17e5-365">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e17e5-365">Online Voice Routing Policy</span></span> |   <span data-ttu-id="e17e5-366">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-366">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-367">Vietnam</span><span class="sxs-lookup"><span data-stu-id="e17e5-367">Vietnam</span></span> | <span data-ttu-id="e17e5-368">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="e17e5-368">+84 4 3926  3000</span></span> |  <span data-ttu-id="e17e5-369">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="e17e5-369">+84 4 5555 5555</span></span> | <span data-ttu-id="e17e5-370">Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-370">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="e17e5-371">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e17e5-371">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="e17e5-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e17e5-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="e17e5-373">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-373">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="e17e5-374">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-374">Mode</span></span> | <span data-ttu-id="e17e5-375">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-375">User</span></span> | <span data-ttu-id="e17e5-376">Standort</span><span class="sxs-lookup"><span data-stu-id="e17e5-376">Site</span></span> | <span data-ttu-id="e17e5-377">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-377">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-378">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e17e5-378">OnlyForLocalUsers</span></span> |   <span data-ttu-id="e17e5-379">Intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-379">Internal</span></span> |<span data-ttu-id="e17e5-380">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-380">Same as SBC</span></span>   | <span data-ttu-id="e17e5-381">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e17e5-381">Outbound</span></span> |

<span data-ttu-id="e17e5-382">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e17e5-382">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="e17e5-383">Dies ist derselbe Fluss, der bei [ausgehenden Anrufen angezeigt wird, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="e17e5-383">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="e17e5-385">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-385">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="e17e5-386">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-386">Mode</span></span> | <span data-ttu-id="e17e5-387">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-387">User</span></span> | <span data-ttu-id="e17e5-388">Standort</span><span class="sxs-lookup"><span data-stu-id="e17e5-388">Site</span></span> | <span data-ttu-id="e17e5-389">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-389">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-390">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e17e5-390">OnlyForLocalUsers</span></span> |   <span data-ttu-id="e17e5-391">Intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-391">Internal</span></span> | <span data-ttu-id="e17e5-392">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-392">Same as SBC</span></span> | <span data-ttu-id="e17e5-393">Inbound</span><span class="sxs-lookup"><span data-stu-id="e17e5-393">Inbound</span></span> |

<span data-ttu-id="e17e5-394">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e17e5-394">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="e17e5-395">Hierbei handelt es sich um denselben Fluss wie in [eingehenden Anrufen, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="e17e5-395">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="e17e5-397">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk mit nur für lokale Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e17e5-397">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="e17e5-398">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-398">Mode</span></span> | <span data-ttu-id="e17e5-399">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-399">User</span></span> | <span data-ttu-id="e17e5-400">Standort</span><span class="sxs-lookup"><span data-stu-id="e17e5-400">Site</span></span> |<span data-ttu-id="e17e5-401">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-401">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-402">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e17e5-402">OnlyForLocalUsers</span></span>  | <span data-ttu-id="e17e5-403">Intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-403">Internal</span></span> |   <span data-ttu-id="e17e5-404">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-404">Different from SBC</span></span> | <span data-ttu-id="e17e5-405">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e17e5-405">Outbound</span></span> |

<span data-ttu-id="e17e5-406">Das direkte Routing berechnet X-MediaPath basierend auf dem gemeldeten Speicherort des Benutzers und des Modus, der für den SBC konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="e17e5-406">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="e17e5-407">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-407">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="e17e5-409">Eingehender Anruf und der Benutzer ist intern, befindet sich aber nicht am gleichen Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-409">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="e17e5-410">Modus</span><span class="sxs-lookup"><span data-stu-id="e17e5-410">Mode</span></span> |    <span data-ttu-id="e17e5-411">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e17e5-411">User</span></span> |  <span data-ttu-id="e17e5-412">Standort</span><span class="sxs-lookup"><span data-stu-id="e17e5-412">Site</span></span> |  <span data-ttu-id="e17e5-413">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e17e5-413">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e17e5-414">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e17e5-414">OnlyForLocalUsers</span></span> | <span data-ttu-id="e17e5-415">Intern</span><span class="sxs-lookup"><span data-stu-id="e17e5-415">Internal</span></span> |    <span data-ttu-id="e17e5-416">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="e17e5-416">Different from SBC</span></span> |    <span data-ttu-id="e17e5-417">Inbound</span><span class="sxs-lookup"><span data-stu-id="e17e5-417">Inbound</span></span> |

<span data-ttu-id="e17e5-418">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="e17e5-418">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-17.png)









