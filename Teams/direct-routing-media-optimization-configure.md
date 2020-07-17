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
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121605"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="e591d-103">Konfigurieren der lokalen Medienoptimierung für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="e591d-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="e591d-104">Die Konfiguration für die lokale Medienoptimierung basiert auf Netzwerkeinstellungen, die anderen Cloud-Sprachfeatures, wie standortbasiertes Routing und dynamische Notrufe, gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="e591d-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="e591d-105">Weitere Informationen zu netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetzen und vertrauenswürdigen IP-Adressen finden Sie unter [Netzwerkeinstellungen für Cloud-Sprachfeatures](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e591d-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e591d-106">Bevor Sie die lokale Medienoptimierung konfigurieren, lesen Sie [lokale Medienoptimierung für direktes Routing](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="e591d-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="e591d-107">Zum Konfigurieren der lokalen Medienoptimierung sind die folgenden Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e591d-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="e591d-108">Sie können das Team Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="e591d-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="e591d-109">Ausführliche Informationen finden Sie unter [Verwalten der Netzwerktopologie](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="e591d-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="e591d-110">Konfigurieren Sie den Benutzer und die SBC-Websites (wie in diesem Artikel beschrieben).</span><span class="sxs-lookup"><span data-stu-id="e591d-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="e591d-111">Konfigurieren Sie die SBCS für die lokale Medienoptimierung (gemäß ihrer SBC-Herstellerspezifikation).</span><span class="sxs-lookup"><span data-stu-id="e591d-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="e591d-112">Das folgende Diagramm zeigt die Netzwerkeinrichtung, die in den Beispielen in diesem Artikel verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e591d-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="e591d-113">![Diagramm mit Netzwerk Setup für Beispiele](media/direct-routing-media-op-9.png "Netzwerk-Setup für Beispiele")</span><span class="sxs-lookup"><span data-stu-id="e591d-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="e591d-114">Konfigurieren des Benutzers und der SBC-Websites</span><span class="sxs-lookup"><span data-stu-id="e591d-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="e591d-115">Wenn Sie den Benutzer und die SBC-Websites konfigurieren möchten, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="e591d-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="e591d-116">[Verwalten externer vertrauenswürdiger IP-Adressen](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="e591d-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="e591d-117">[Definieren Sie die Netzwerktopologie](#define-the-network-topology) , indem Sie die netzwerkregionen, Netzwerkstandorte und Netzwerk-Subnetze konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e591d-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="e591d-118">[Definieren Sie die virtuelle Netzwerktopologie](#define-the-virtual-network-topology) , indem Sie SBC (s) den Websites mit relevanten Modi und Proxy-SBC-Werten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e591d-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="e591d-119">Konfigurieren von SBC (s) für die lokale Medienoptimierung gemäß der SBC-Herstellerspezifikation</span><span class="sxs-lookup"><span data-stu-id="e591d-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="e591d-120">In diesem Artikel wird die Konfiguration für Microsoft-Komponenten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e591d-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="e591d-121">Informationen zur SBC-Konfiguration finden Sie in der Dokumentation Ihres SBC-Herstellers.</span><span class="sxs-lookup"><span data-stu-id="e591d-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="e591d-122">Die lokale Medienoptimierung wird von den folgenden SBC-Anbietern unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e591d-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="e591d-123">Anbieter</span><span class="sxs-lookup"><span data-stu-id="e591d-123">Vendor</span></span> | <span data-ttu-id="e591d-124">Produkt</span><span class="sxs-lookup"><span data-stu-id="e591d-124">Product</span></span> |    <span data-ttu-id="e591d-125">Software Version</span><span class="sxs-lookup"><span data-stu-id="e591d-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="e591d-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e591d-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="e591d-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="e591d-128">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="e591d-130">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="e591d-132">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="e591d-134">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-135">Mediant-1000B-SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="e591d-136">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="e591d-138">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="e591d-140">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="e591d-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="e591d-142">7,2 a. 256</span><span class="sxs-lookup"><span data-stu-id="e591d-142">7.20A.256</span></span> |
| [<span data-ttu-id="e591d-143">Menüband-SBC-Kern</span><span class="sxs-lookup"><span data-stu-id="e591d-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="e591d-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="e591d-144">SBC 5110</span></span>         | <span data-ttu-id="e591d-145">8,2</span><span class="sxs-lookup"><span data-stu-id="e591d-145">8.2</span></span>  |
|            |  <span data-ttu-id="e591d-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="e591d-146">SBC 5210</span></span>         | <span data-ttu-id="e591d-147">8,2</span><span class="sxs-lookup"><span data-stu-id="e591d-147">8.2</span></span>  |
|            |  <span data-ttu-id="e591d-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="e591d-148">SBC 5400</span></span>         | <span data-ttu-id="e591d-149">8,2</span><span class="sxs-lookup"><span data-stu-id="e591d-149">8.2</span></span>  |
|            |  <span data-ttu-id="e591d-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="e591d-150">SBC 7000</span></span>         | <span data-ttu-id="e591d-151">8,2</span><span class="sxs-lookup"><span data-stu-id="e591d-151">8.2</span></span>  |
|            |  <span data-ttu-id="e591d-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="e591d-152">SBC SWe</span></span>          | <span data-ttu-id="e591d-153">8,2</span><span class="sxs-lookup"><span data-stu-id="e591d-153">8.2</span></span>  |
| [<span data-ttu-id="e591d-154">Menüband SBC-Kante</span><span class="sxs-lookup"><span data-stu-id="e591d-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="e591d-155">Lite SBC Schwedisch</span><span class="sxs-lookup"><span data-stu-id="e591d-155">SBC SWe Lite</span></span> | <span data-ttu-id="e591d-156">8.1.5 (Build 239)</span><span class="sxs-lookup"><span data-stu-id="e591d-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="e591d-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="e591d-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="e591d-158">anynode</span><span class="sxs-lookup"><span data-stu-id="e591d-158">anynode</span></span>          | <span data-ttu-id="e591d-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="e591d-159">4.0.1+</span></span> |
| [<span data-ttu-id="e591d-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="e591d-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="e591d-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="e591d-161">AP 1100</span></span> | <span data-ttu-id="e591d-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e591d-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="e591d-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="e591d-163">AP 3900</span></span> | <span data-ttu-id="e591d-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e591d-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="e591d-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="e591d-165">AP 4600</span></span> | <span data-ttu-id="e591d-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e591d-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="e591d-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="e591d-167">AP 6300</span></span> | <span data-ttu-id="e591d-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e591d-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="e591d-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="e591d-169">AP 6350</span></span> | <span data-ttu-id="e591d-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e591d-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="e591d-171">VME</span><span class="sxs-lookup"><span data-stu-id="e591d-171">VME</span></span>     | <span data-ttu-id="e591d-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="e591d-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="e591d-173">Verwalten externer vertrauenswürdiger IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="e591d-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="e591d-174">Externe vertrauenswürdige IPS sind die Internet externen IPS des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="e591d-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="e591d-175">Diese IP-Adressen sind die IP-Adressen, die von Microsoft Teams-Clients verwendet werden, wenn Sie eine Verbindung mit Microsoft 365 herstellen.</span><span class="sxs-lookup"><span data-stu-id="e591d-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="e591d-176">Sie müssen diese externen IPS für jede Website hinzufügen, auf der Benutzer die lokale Medienoptimierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e591d-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="e591d-177">Wenn Sie die öffentlichen IP-Adressen für jede Website hinzufügen möchten, verwenden Sie das Cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="e591d-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="e591d-178">Sie können eine unbegrenzte Anzahl von vertrauenswürdigen IP-Adressen für einen Mandanten definieren.</span><span class="sxs-lookup"><span data-stu-id="e591d-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="e591d-179">Wenn die von Microsoft 365 gesehenen externen IPS sowohl IPv4-als auch IPv6-Adressen sind, müssen Sie beide Typen von IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e591d-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="e591d-180">Verwenden Sie für IPv4 Maske 32.</span><span class="sxs-lookup"><span data-stu-id="e591d-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="e591d-181">Verwenden Sie für IPv6 die Maske 128.</span><span class="sxs-lookup"><span data-stu-id="e591d-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="e591d-182">Sie können sowohl einzelne externe IP-Adressen als auch externe IP-Subnetze hinzufügen, indem Sie unterschiedliche MaskBits für das Cmdlet angeben.</span><span class="sxs-lookup"><span data-stu-id="e591d-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="e591d-183">Beispiel für das Hinzufügen von vertrauenswürdigen IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="e591d-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="e591d-184">Definieren der Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="e591d-184">Define the network topology</span></span>

<span data-ttu-id="e591d-185">In diesem Abschnitt wird beschrieben, wie Sie die netzwerkregionen, Netzwerk Websites und Netzwerk-Subnetze für Ihre Netzwerktopologie definieren.</span><span class="sxs-lookup"><span data-stu-id="e591d-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="e591d-186">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, daher müssen Sie sicherstellen, dass Sie denselben Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e591d-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="e591d-187">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="e591d-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="e591d-188">Definieren von netzwerkregionen</span><span class="sxs-lookup"><span data-stu-id="e591d-188">Define network regions</span></span>

<span data-ttu-id="e591d-189">Verwenden Sie zum Definieren von netzwerkregionen das Cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="e591d-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="e591d-190">Der Parameter Regions-Nr ist ein logischer Name, der die Geographie des Bereichs darstellt und keine Abhängigkeiten oder Einschränkungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="e591d-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="e591d-191">Der CentralSite <site ID> -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="e591d-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="e591d-192">Im folgenden Beispiel wird eine netzwerkregion mit dem Namen APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="e591d-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="e591d-193">Definieren von Netzwerk Websites</span><span class="sxs-lookup"><span data-stu-id="e591d-193">Define network sites</span></span>

<span data-ttu-id="e591d-194">Verwenden Sie zum Definieren von Netzwerk Websites das Cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="e591d-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="e591d-195">Jede Netzwerk Website muss einem Netzwerkbereich zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="e591d-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="e591d-196">Im folgenden Beispiel werden drei neue Netzwerk Websites, Vietnam, Indonesien und Singapur, in der Region APAC erstellt:</span><span class="sxs-lookup"><span data-stu-id="e591d-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="e591d-197">Definieren von Netzwerk-Subnetzen</span><span class="sxs-lookup"><span data-stu-id="e591d-197">Define network subnets</span></span>

<span data-ttu-id="e591d-198">Verwenden Sie das Cmdlet New-CsTenantNetworkSubnet, um Netzwerk-Subnetze zu definieren und Sie den Netzwerkstandorten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e591d-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="e591d-199">Jedes Netzwerk Subnetz kann nur einer Website zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e591d-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="e591d-200">Im folgenden Beispiel werden drei Netzwerk-Subnetze definiert und den drei Netzwerkstandorten zugeordnet: Vietnam, Indonesien und Singapur:</span><span class="sxs-lookup"><span data-stu-id="e591d-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="e591d-201">Definieren der virtuellen Netzwerktopologie</span><span class="sxs-lookup"><span data-stu-id="e591d-201">Define the virtual network topology</span></span> 

<span data-ttu-id="e591d-202">Zunächst erstellt der mandantenadministrator mithilfe des Cmdlets New-CsOnlinePSTNGateway eine neue SBC-Konfiguration für jeden relevanten SBC.</span><span class="sxs-lookup"><span data-stu-id="e591d-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="e591d-203">Der mandantenadministrator definiert die virtuelle Netzwerktopologie, indem er die Netzwerk Websites für die PSTN-Gateway-Objekte mit dem Cmdlet "CsOnlinePSTNGateway" angibt:</span><span class="sxs-lookup"><span data-stu-id="e591d-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="e591d-204">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e591d-204">Note the following:</span></span> 
   - <span data-ttu-id="e591d-205">Wenn der Kunde über einen einzelnen SBC verfügt, muss der-ProxySBC-Parameter entweder obligatorisch $NULL oder SBC-FQDN-Wert sein (zentrales SBC-Szenario mit zentralisierten Trunks).</span><span class="sxs-lookup"><span data-stu-id="e591d-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="e591d-206">Der-MediaBypass-Parameter muss auf $true eingestellt sein, um die lokale Medienoptimierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e591d-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="e591d-207">Wenn der SBC-BypassMode-Parametersatz nicht vorhanden ist, werden keine X-MS-Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="e591d-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="e591d-208">Bei allen Parametern wird die Groß-/Kleinschreibung beachtet, sodass Sie sicherstellen müssen, dass Sie den gleichen Fall verwenden, der während des Setups verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e591d-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="e591d-209">(Beispiel: GatewaySiteID-Werte "Vietnam" und "Vietnam" werden als unterschiedliche Websites behandelt.)</span><span class="sxs-lookup"><span data-stu-id="e591d-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="e591d-210">Im folgenden Beispiel werden drei SBCS zu den Netzwerkstandorten Vietnam, Indonesien und Singapur im Bereich APAC mit dem Modus immer umgehen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e591d-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="e591d-211">Hinweis: um unterbrechungsfreie Vorgänge zu gewährleisten, wenn die lokale Medienoptimierung und standortbasiertes Routing (LBR) gleichzeitig konfiguriert sind, muss Downstream-SBCS für LBR aktiviert werden, indem der GatewaySiteLbrEnabled-Parameter für jeden Downstream-SBC auf $true festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e591d-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="e591d-212">(Diese Einstellung ist für den Proxy-SBC nicht zwingend erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="e591d-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="e591d-213">Basierend auf den oben aufgeführten Informationen umfasst das direkte Routing drei proprietäre SIP-Header für SIP-Einladungen und erneute Einladungen, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e591d-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="e591d-214">X-MS-Header, die beim direkten Routing bei Einladungen und erneuten Einladungen eingeführt werden, wenn BypassMode definiert ist:</span><span class="sxs-lookup"><span data-stu-id="e591d-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="e591d-215">Header Name</span><span class="sxs-lookup"><span data-stu-id="e591d-215">Header name</span></span> | <span data-ttu-id="e591d-216">Werte</span><span class="sxs-lookup"><span data-stu-id="e591d-216">Values</span></span> | <span data-ttu-id="e591d-217">Kommentare</span><span class="sxs-lookup"><span data-stu-id="e591d-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="e591d-218">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="e591d-218">X-MS-UserLocation</span></span> | <span data-ttu-id="e591d-219">intern/extern</span><span class="sxs-lookup"><span data-stu-id="e591d-219">internal/external</span></span> | <span data-ttu-id="e591d-220">Gibt an, ob der Benutzer intern oder extern ist</span><span class="sxs-lookup"><span data-stu-id="e591d-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="e591d-221">Request-URI INVITE SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="e591d-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="e591d-222">SBC-FQDN</span><span class="sxs-lookup"><span data-stu-id="e591d-222">SBC FQDN</span></span> | <span data-ttu-id="e591d-223">Der FQDN, der für den Anruf vorgesehen ist, auch wenn der SBC nicht direkt mit dem direkten Routing verbunden ist</span><span class="sxs-lookup"><span data-stu-id="e591d-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="e591d-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="e591d-224">X-MS-MediaPath</span></span> | <span data-ttu-id="e591d-225">Beispiel: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="e591d-226">Die Reihenfolge der SBCS, die für den Medienpfad zwischen dem Benutzer und dem Ziel-SBC verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e591d-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="e591d-227">Der endgültige SBC ist immer der letzte.</span><span class="sxs-lookup"><span data-stu-id="e591d-227">The final SBC is always last</span></span> |
| <span data-ttu-id="e591d-228">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="e591d-228">X-MS-UserSite</span></span> | <span data-ttu-id="e591d-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="e591d-229">usersiteID</span></span> | <span data-ttu-id="e591d-230">Vom mandantenadministrator festgelegte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e591d-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="e591d-231">Anruf Flüsse</span><span class="sxs-lookup"><span data-stu-id="e591d-231">Call flows</span></span> 

<span data-ttu-id="e591d-232">Im folgenden werden die Anruf Flüsse für zwei Modi angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e591d-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="e591d-233">Immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e591d-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="e591d-234">Nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="e591d-235">Modus immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e591d-235">Always Bypass mode</span></span>

<span data-ttu-id="e591d-236">Der Bypass-Modus ist immer die einfachste Option für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e591d-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="e591d-237">Der mandantenadministrator kann eine einzelne Website für alle Benutzer und SBCS konfigurieren, wenn alle SBCS von einer beliebigen Website aus erreichbar sind.</span><span class="sxs-lookup"><span data-stu-id="e591d-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="e591d-238">In den Beispielen wird der Modus "immer umgehen" für die folgenden Szenarien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e591d-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="e591d-239">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="e591d-240">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="e591d-241">Ausgehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="e591d-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="e591d-242">Eingehende Anrufe und der Benutzer ist extern</span><span class="sxs-lookup"><span data-stu-id="e591d-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="e591d-243">In der folgenden Tabelle sind die in den Beispielen verwendeten FQDN-und IP-Adressen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="e591d-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="e591d-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="e591d-244">FQDN</span></span> | <span data-ttu-id="e591d-245">Externe SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e591d-245">SBC external IP address</span></span> | <span data-ttu-id="e591d-246">Interne SBC-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e591d-246">SBC internal IP Address</span></span> | <span data-ttu-id="e591d-247">Internes Subnetz</span><span class="sxs-lookup"><span data-stu-id="e591d-247">Internal subnet</span></span> | <span data-ttu-id="e591d-248">Ort</span><span class="sxs-lookup"><span data-stu-id="e591d-248">Location</span></span> | <span data-ttu-id="e591d-249">Externe NAT (vertrauenswürdige IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="e591d-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="e591d-251">Keine</span><span class="sxs-lookup"><span data-stu-id="e591d-251">None</span></span> | <span data-ttu-id="e591d-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="e591d-252">192.168.1.5</span></span> | <span data-ttu-id="e591d-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="e591d-253">192.168.1.0/24</span></span> | <span data-ttu-id="e591d-254">Vietnam</span><span class="sxs-lookup"><span data-stu-id="e591d-254">Vietnam</span></span> | <span data-ttu-id="e591d-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="e591d-255">172.16.240.110</span></span> |
| <span data-ttu-id="e591d-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="e591d-257">Keine</span><span class="sxs-lookup"><span data-stu-id="e591d-257">None</span></span> | <span data-ttu-id="e591d-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="e591d-258">192.168.2.5</span></span> | <span data-ttu-id="e591d-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="e591d-259">192.168.2.0/24</span></span> | <span data-ttu-id="e591d-260">Indonesien</span><span class="sxs-lookup"><span data-stu-id="e591d-260">Indonesia</span></span> | <span data-ttu-id="e591d-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="e591d-261">172.16.240.120</span></span> |
| <span data-ttu-id="e591d-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="e591d-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="e591d-263">172.16.240.133</span></span> | <span data-ttu-id="e591d-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="e591d-264">192.168.3.5</span></span> | <span data-ttu-id="e591d-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="e591d-265">192.168.3.0/24</span></span> | <span data-ttu-id="e591d-266">Singapur</span><span class="sxs-lookup"><span data-stu-id="e591d-266">Singapore</span></span> | <span data-ttu-id="e591d-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="e591d-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="e591d-268">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e591d-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="e591d-269">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-269">Mode</span></span> |    <span data-ttu-id="e591d-270">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-270">User</span></span> |  <span data-ttu-id="e591d-271">Ort</span><span class="sxs-lookup"><span data-stu-id="e591d-271">Location</span></span> |  <span data-ttu-id="e591d-272">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="e591d-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e591d-273">AlwaysBypass</span></span> |    <span data-ttu-id="e591d-274">Intern</span><span class="sxs-lookup"><span data-stu-id="e591d-274">Internal</span></span> |  <span data-ttu-id="e591d-275">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-275">The same site as SBC</span></span> |  <span data-ttu-id="e591d-276">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e591d-276">Outbound</span></span> |

<span data-ttu-id="e591d-277">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="e591d-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="e591d-278">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e591d-278">User physical location</span></span>| <span data-ttu-id="e591d-279">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="e591d-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="e591d-280">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e591d-280">User phone number</span></span>  | <span data-ttu-id="e591d-281">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e591d-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="e591d-282">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-283">Vietnam</span><span class="sxs-lookup"><span data-stu-id="e591d-283">Vietnam</span></span> | <span data-ttu-id="e591d-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="e591d-284">+84 4 3926 3000</span></span> | <span data-ttu-id="e591d-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="e591d-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="e591d-286">Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="e591d-287">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="e591d-288">VNsbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e591d-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="e591d-289">proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e591d-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="e591d-290">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit Always Bypass-Modus und den Benutzer am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e591d-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="e591d-291">![Diagramm mit ausgehenden Anrufen](media/direct-routing-media-op-10.png "Ausgehende Anrufe")</span><span class="sxs-lookup"><span data-stu-id="e591d-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="e591d-292">Die folgende Tabelle zeigt die X-MS-Kopfzeilen, die durch Direct Routing gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="e591d-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="e591d-293">Parameter</span><span class="sxs-lookup"><span data-stu-id="e591d-293">Parameter</span></span> | <span data-ttu-id="e591d-294">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e591d-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="e591d-295">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="e591d-296">Der Ziel-FQDN des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet</span><span class="sxs-lookup"><span data-stu-id="e591d-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="e591d-297">X-MS-UserLocation: intern</span><span class="sxs-lookup"><span data-stu-id="e591d-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="e591d-298">Das Feld hat angegeben, dass sich der Benutzer im Unternehmensnetzwerk befindet</span><span class="sxs-lookup"><span data-stu-id="e591d-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="e591d-299">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="e591d-300">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="e591d-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="e591d-301">In diesem Fall, da wir immer Bypass haben und der Client intern ist, wird der Zielname als einziger Name im Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="e591d-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="e591d-302">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="e591d-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="e591d-303">Das Feld, das auf der Website angegeben ist, in der sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="e591d-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="e591d-304">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e591d-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="e591d-305">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-305">Mode</span></span> |    <span data-ttu-id="e591d-306">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-306">User</span></span> |  <span data-ttu-id="e591d-307">Ort</span><span class="sxs-lookup"><span data-stu-id="e591d-307">Location</span></span> |  <span data-ttu-id="e591d-308">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e591d-309">AlwaysBypass</span></span> |    <span data-ttu-id="e591d-310">Intern</span><span class="sxs-lookup"><span data-stu-id="e591d-310">Internal</span></span> | <span data-ttu-id="e591d-311">Dieselbe Website wie SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-311">The same site as SBC</span></span> | <span data-ttu-id="e591d-312">Inbound</span><span class="sxs-lookup"><span data-stu-id="e591d-312">Inbound</span></span> |


<span data-ttu-id="e591d-313">Bei einem eingehenden Anruf ist der Standort des Benutzers unbekannt, und der SBC muss erraten, wo sich der Benutzer befindet.</span><span class="sxs-lookup"><span data-stu-id="e591d-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="e591d-314">Wenn die Vermutung nicht korrekt ist, wird eine erneute Einladung benötigt.</span><span class="sxs-lookup"><span data-stu-id="e591d-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="e591d-315">In diesem Fall wird davon ausgegangen, dass der Benutzer intern ist, Medien direkt fließen können und keine weiteren Aktionen erforderlich sind (erneut einladen).</span><span class="sxs-lookup"><span data-stu-id="e591d-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="e591d-316">Der SBC, der mit dem Direct Routing-Dienst verbunden ist, meldet den ursprünglichen SBC-Standort durch Bereitstellen von Daten Satz Routen-und Kontaktfeldern.</span><span class="sxs-lookup"><span data-stu-id="e591d-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="e591d-317">Basierend auf diesen Feldern wird der Medienpfad durch direkte Weiterleitung berechnet.</span><span class="sxs-lookup"><span data-stu-id="e591d-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="e591d-318">Hinweis: da ein Benutzer mehrere Endpunkte haben kann, ist die Unterstützung von 183 nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="e591d-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="e591d-319">Die direkte Weiterleitung wird in diesem Fall immer 180-Klingeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="e591d-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="e591d-320">Das folgende Diagramm zeigt die SIP-Leiter für eingehende Anrufe mit dem AlwaysBypass-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e591d-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="e591d-322">Ausgehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e591d-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="e591d-323">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-323">Mode</span></span> |    <span data-ttu-id="e591d-324">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-324">User</span></span> |  <span data-ttu-id="e591d-325">Standort</span><span class="sxs-lookup"><span data-stu-id="e591d-325">Site</span></span> |  <span data-ttu-id="e591d-326">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="e591d-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e591d-327">AlwaysBypass</span></span> |  <span data-ttu-id="e591d-328">Extern</span><span class="sxs-lookup"><span data-stu-id="e591d-328">External</span></span> |  <span data-ttu-id="e591d-329">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e591d-329">N/A</span></span> | <span data-ttu-id="e591d-330">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e591d-330">Outbound</span></span> |


<span data-ttu-id="e591d-331">Das folgende Diagramm zeigt die SIP-Leiter für einen ausgehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern:</span><span class="sxs-lookup"><span data-stu-id="e591d-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-12.png)

<span data-ttu-id="e591d-333">Die folgende Tabelle zeigt die X-MS-Header, die vom Direct Routing-Dienst gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="e591d-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="e591d-334">Parameter</span><span class="sxs-lookup"><span data-stu-id="e591d-334">Parameter</span></span> |   <span data-ttu-id="e591d-335">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e591d-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="e591d-336">Einladen + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="e591d-337">Der Ziel-FQDN des SBC, wie er in der Online-VoIP-Routing Richtlinie definiert ist, wird im Anforderungs-URI gesendet.</span><span class="sxs-lookup"><span data-stu-id="e591d-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="e591d-338">X-MS-UserLocation: Extern</span><span class="sxs-lookup"><span data-stu-id="e591d-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="e591d-339">Das Feld hat angegeben, dass der Benutzer sich außerhalb des Unternehmensnetzwerks befindet.</span><span class="sxs-lookup"><span data-stu-id="e591d-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="e591d-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="e591d-341">Gibt an, welche SBC der Client zum Ziel-SBC durchlaufen muss.</span><span class="sxs-lookup"><span data-stu-id="e591d-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="e591d-342">In diesem Fall, da wir immer Bypass haben und der Client extern ist.</span><span class="sxs-lookup"><span data-stu-id="e591d-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="e591d-343">Eingehende Anrufe und der Benutzer ist extern mit Always Bypass</span><span class="sxs-lookup"><span data-stu-id="e591d-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="e591d-344">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-344">Mode</span></span> | <span data-ttu-id="e591d-345">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-345">User</span></span> | <span data-ttu-id="e591d-346">Standort</span><span class="sxs-lookup"><span data-stu-id="e591d-346">Site</span></span> |  <span data-ttu-id="e591d-347">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="e591d-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="e591d-348">AlwaysBypass</span></span> |  <span data-ttu-id="e591d-349">Extern</span><span class="sxs-lookup"><span data-stu-id="e591d-349">External</span></span> |  <span data-ttu-id="e591d-350">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="e591d-350">N/A</span></span> |   <span data-ttu-id="e591d-351">Inbound</span><span class="sxs-lookup"><span data-stu-id="e591d-351">Inbound</span></span> |

<span data-ttu-id="e591d-352">Bei einem eingehenden Anruf muss der SBC, der mit dem direkten Routing verbunden ist, eine erneute Einladung senden (Standardmäßig werden lokale Medien Kandidaten immer angeboten), wenn der Standort des Benutzers extern ist.</span><span class="sxs-lookup"><span data-stu-id="e591d-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="e591d-353">Die X-MediaPath wird basierend auf der Daten Satz Route und dem angegebenen SBC-Benutzer berechnet.</span><span class="sxs-lookup"><span data-stu-id="e591d-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="e591d-354">Das folgende Diagramm zeigt die SIP-Leiter für einen eingehenden Anruf mit dem AlwaysBypass-Modus, und der Benutzer ist extern.</span><span class="sxs-lookup"><span data-stu-id="e591d-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="e591d-356">Nur für den lokalen Benutzermodus</span><span class="sxs-lookup"><span data-stu-id="e591d-356">Only for local users mode</span></span>

<span data-ttu-id="e591d-357">Lokale Medien Kandidaten des Ziel-SBC werden nur angeboten, wenn sich ein Benutzer am selben Ort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="e591d-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="e591d-358">In allen anderen Fällen fließen Medien entweder über eine interne oder externe IP-Adresse des Proxy-SBC.</span><span class="sxs-lookup"><span data-stu-id="e591d-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="e591d-359">Die folgenden Szenarien werden beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e591d-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="e591d-360">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="e591d-361">Eingehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="e591d-362">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="e591d-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="e591d-363">Eingehende Anrufe und der Benutzer ist intern, aber nicht am selben Ort wie der SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="e591d-364">Die folgende Tabelle zeigt die Konfiguration und Aktion des Endbenutzers:</span><span class="sxs-lookup"><span data-stu-id="e591d-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="e591d-365">Physischer Standort des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e591d-365">User physical location</span></span> |  <span data-ttu-id="e591d-366">Der Benutzer macht oder empfängt einen Anruf an/von der Nummer</span><span class="sxs-lookup"><span data-stu-id="e591d-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="e591d-367">Telefonnummer des Benutzers</span><span class="sxs-lookup"><span data-stu-id="e591d-367">User phone number</span></span> | <span data-ttu-id="e591d-368">Online-VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e591d-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="e591d-369">Für SBC konfigurierter Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-370">Vietnam</span><span class="sxs-lookup"><span data-stu-id="e591d-370">Vietnam</span></span> | <span data-ttu-id="e591d-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="e591d-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="e591d-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="e591d-372">+84 4 5555 5555</span></span> | <span data-ttu-id="e591d-373">Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="e591d-374">Priorität 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e591d-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="e591d-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – immer umgehen</span><span class="sxs-lookup"><span data-stu-id="e591d-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="e591d-376">Ausgehende Anrufe und der Benutzer befindet sich am gleichen Speicherort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="e591d-377">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-377">Mode</span></span> | <span data-ttu-id="e591d-378">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-378">User</span></span> | <span data-ttu-id="e591d-379">Standort</span><span class="sxs-lookup"><span data-stu-id="e591d-379">Site</span></span> | <span data-ttu-id="e591d-380">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e591d-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="e591d-382">Intern</span><span class="sxs-lookup"><span data-stu-id="e591d-382">Internal</span></span> |<span data-ttu-id="e591d-383">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-383">Same as SBC</span></span>   | <span data-ttu-id="e591d-384">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e591d-384">Outbound</span></span> |

<span data-ttu-id="e591d-385">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e591d-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="e591d-386">Dies ist derselbe Fluss, der bei [ausgehenden Anrufen angezeigt wird, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="e591d-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="e591d-388">Eingehende Anrufe und der Benutzer befindet sich am selben Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="e591d-389">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-389">Mode</span></span> | <span data-ttu-id="e591d-390">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-390">User</span></span> | <span data-ttu-id="e591d-391">Standort</span><span class="sxs-lookup"><span data-stu-id="e591d-391">Site</span></span> | <span data-ttu-id="e591d-392">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e591d-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="e591d-394">Intern</span><span class="sxs-lookup"><span data-stu-id="e591d-394">Internal</span></span> | <span data-ttu-id="e591d-395">Identisch mit SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-395">Same as SBC</span></span> | <span data-ttu-id="e591d-396">Inbound</span><span class="sxs-lookup"><span data-stu-id="e591d-396">Inbound</span></span> |

<span data-ttu-id="e591d-397">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus, und der Benutzer befindet sich am gleichen Speicherort wie der SBC.</span><span class="sxs-lookup"><span data-stu-id="e591d-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="e591d-398">Hierbei handelt es sich um denselben Fluss wie in [eingehenden Anrufen, wenn sich der Benutzer am gleichen Speicherort wie der SBC befindet](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="e591d-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="e591d-400">Der Benutzer befindet sich nicht am gleichen Speicherort wie der SBC, befindet sich aber im Unternehmensnetzwerk mit nur für lokale Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e591d-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="e591d-401">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-401">Mode</span></span> | <span data-ttu-id="e591d-402">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-402">User</span></span> | <span data-ttu-id="e591d-403">Standort</span><span class="sxs-lookup"><span data-stu-id="e591d-403">Site</span></span> |<span data-ttu-id="e591d-404">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e591d-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="e591d-406">Intern</span><span class="sxs-lookup"><span data-stu-id="e591d-406">Internal</span></span> |   <span data-ttu-id="e591d-407">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-407">Different from SBC</span></span> | <span data-ttu-id="e591d-408">Ausgehend</span><span class="sxs-lookup"><span data-stu-id="e591d-408">Outbound</span></span> |

<span data-ttu-id="e591d-409">Das direkte Routing berechnet X-MediaPath basierend auf dem gemeldeten Speicherort des Benutzers und des Modus, der für den SBC konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="e591d-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="e591d-410">Das folgende Diagramm zeigt einen ausgehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="e591d-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="e591d-412">Eingehender Anruf und der Benutzer ist intern, befindet sich aber nicht am gleichen Ort wie der SBC mit nur für lokale Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="e591d-413">Modus</span><span class="sxs-lookup"><span data-stu-id="e591d-413">Mode</span></span> |    <span data-ttu-id="e591d-414">Benutzer</span><span class="sxs-lookup"><span data-stu-id="e591d-414">User</span></span> |  <span data-ttu-id="e591d-415">Standort</span><span class="sxs-lookup"><span data-stu-id="e591d-415">Site</span></span> |  <span data-ttu-id="e591d-416">Anrufrichtung</span><span class="sxs-lookup"><span data-stu-id="e591d-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="e591d-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="e591d-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="e591d-418">Intern</span><span class="sxs-lookup"><span data-stu-id="e591d-418">Internal</span></span> |    <span data-ttu-id="e591d-419">Anders als SBC</span><span class="sxs-lookup"><span data-stu-id="e591d-419">Different from SBC</span></span> |    <span data-ttu-id="e591d-420">Inbound</span><span class="sxs-lookup"><span data-stu-id="e591d-420">Inbound</span></span> |

<span data-ttu-id="e591d-421">Das folgende Diagramm zeigt einen eingehenden Anruf mit dem OnlyForLocalUsers-Modus und einen internen Benutzer, der sich nicht am gleichen Speicherort wie der SBC befindet.</span><span class="sxs-lookup"><span data-stu-id="e591d-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramm mit SIP-Leiter](media/direct-routing-media-op-17.png)









