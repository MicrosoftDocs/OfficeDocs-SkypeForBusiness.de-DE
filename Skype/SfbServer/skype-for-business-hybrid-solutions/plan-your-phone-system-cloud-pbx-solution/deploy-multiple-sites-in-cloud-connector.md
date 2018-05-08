---
title: Bereitstellen mehrerer Standorte in Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informationen Sie zu mehreren PSTN-Websites in der Cloud Connector Edition bereitstellen.
ms.openlocfilehash: 2bc56f2cdff3f852bf2557fc3ae98e1a2f8fa854
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="eab9c-103">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="eab9c-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="eab9c-104">Informationen Sie zu mehreren PSTN-Websites in der Cloud Connector Edition bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="eab9c-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="eab9c-p101">In diesem Abschnitt wird die Bereitstellung mehrerer PSTN-Standorte (Public Switched Telephone Network, Telefonfestnetz) erläutert. Standorte werden jeweils nacheinander wie bei der Bereitstellung eines einzelnen Standorts bereitgestellt. In diesem Thema werden Überlegungen zu Standorten und Unterschiede zwischen Standorten in einer Bereitstellung mit mehreren Standorten beschrieben. </span><span class="sxs-lookup"><span data-stu-id="eab9c-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="eab9c-108">Mehrere PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="eab9c-109">Die folgende Abbildung zeigt eine Beispielkonfiguration Skype für Business Cloud Connector Edition für andere PSTN-Websites bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="eab9c-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="eab9c-110">Stellen Sie vor dem Starten der Bereitstellung sicher, dass Ihre Konfigurationseinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="eab9c-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="eab9c-111">PSTN-Standort 1</span><span class="sxs-lookup"><span data-stu-id="eab9c-111">PSTN Site 1</span></span>
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35

```

<span data-ttu-id="eab9c-112">PSTN-Standort 2</span><span class="sxs-lookup"><span data-stu-id="eab9c-112">PSTN Site 2</span></span>
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134

```

<span data-ttu-id="eab9c-113">Führen Sie für jede PSTN-Website, die Sie hinzufügen möchten die Schritte unter [Deploy einer einzelnen Website in der Cloud-Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="eab9c-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eab9c-114">Der freigegebene Ordner für die Vorbereitung hoher Verfügbarkeit wird pro PSTN-Standort erstellt.</span><span class="sxs-lookup"><span data-stu-id="eab9c-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="eab9c-115">Der freigegebene Ordner **muss** sich zwischen den PSTN-Standorten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="eab9c-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="eab9c-116">Verwenden Sie nicht den gleichen freigegebenen Ordner für mehrere Websites. ></span><span class="sxs-lookup"><span data-stu-id="eab9c-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="eab9c-117">Bereitstellung eines einzelnen Standorts mit hoher Verfügbarkeit im Vergleich zur Bereitstellung mehrerer Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="eab9c-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="eab9c-118"></span></span>

<span data-ttu-id="eab9c-119">Die folgende Tabelle listet die Unterschiede zwischen einem einzelnen Standort mit HA-Unterstützung und einer Bereitstellung mit mehreren Standorten auf.</span><span class="sxs-lookup"><span data-stu-id="eab9c-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="eab9c-120">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="eab9c-120">**Category**</span></span>|<span data-ttu-id="eab9c-121">**Element**</span><span class="sxs-lookup"><span data-stu-id="eab9c-121">**Item**</span></span>|<span data-ttu-id="eab9c-122">**Einzelnen Standort mit HA**</span><span class="sxs-lookup"><span data-stu-id="eab9c-122">**Single-Site with HA**</span></span>|<span data-ttu-id="eab9c-123">**Mehrere Standorte**</span><span class="sxs-lookup"><span data-stu-id="eab9c-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eab9c-124">Einrichtung</span><span class="sxs-lookup"><span data-stu-id="eab9c-124">Setup</span></span>  <br/> |<span data-ttu-id="eab9c-125">Freigegebener Ordner</span><span class="sxs-lookup"><span data-stu-id="eab9c-125">Shared folder</span></span>  <br/> |<span data-ttu-id="eab9c-126">Erfordert den **gleiche** freigegebenen Ordner mehreren appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="eab9c-127">Benötigt für jede Appliance einen **unterschiedlichen** freigegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="eab9c-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="eab9c-128">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-128">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="eab9c-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="eab9c-130">Benötigt für alle Appliances **dieselbe** Domäne.</span><span class="sxs-lookup"><span data-stu-id="eab9c-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="eab9c-131">Benötigt **dieselbe** Domäne für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-132">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-132">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-133">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="eab9c-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="eab9c-134">Domänennamen und der Reihenfolge sollte sein die **gleichen** mehreren appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-135">Domänennamen und der Reihenfolge sollte sein die **gleichen** PSTN-websiteübergreifenden</span><span class="sxs-lookup"><span data-stu-id="eab9c-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-136">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-136">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-137">Standortname</span><span class="sxs-lookup"><span data-stu-id="eab9c-137">Site name</span></span>  <br/> |<span data-ttu-id="eab9c-138">**Identischer** Standortname für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="eab9c-139">**Unterschiedlicher** Standortname für jeden einzelnen PSTN-Standort</span><span class="sxs-lookup"><span data-stu-id="eab9c-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-140">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-140">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-141">Servernamen</span><span class="sxs-lookup"><span data-stu-id="eab9c-141">Server names</span></span>  <br/> |<span data-ttu-id="eab9c-142">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-143">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-144">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-144">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-145">FQDNs interner Pools</span><span class="sxs-lookup"><span data-stu-id="eab9c-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="eab9c-146">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-147">**Identisch** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-148">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-148">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-149">Interne IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="eab9c-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="eab9c-150">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-151">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-152">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-152">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-153">Externer FQDN</span><span class="sxs-lookup"><span data-stu-id="eab9c-153">External FQDN</span></span>  <br/> |<span data-ttu-id="eab9c-154">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-155">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-156">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-156">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-157">Externe IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="eab9c-157">External IPs</span></span>  <br/> |<span data-ttu-id="eab9c-158">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-159">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-160">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-160">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-161">Einstellungen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="eab9c-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="eab9c-162">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="eab9c-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="eab9c-163">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="eab9c-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eab9c-164">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="eab9c-164">Configure</span></span>  <br/> |<span data-ttu-id="eab9c-165">DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="eab9c-165">DNS record</span></span>  <br/> |<span data-ttu-id="eab9c-166">Hinzufügen von Datensätzen mit der **gleichen** externen Zugriff FQDNs und **verschiedene** IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="eab9c-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="eab9c-167">Einträge mit **unterschiedlichen** externen Zugriffs-FQDNs und **unterschiedlichen** IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="eab9c-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="eab9c-168">Einrichtung</span><span class="sxs-lookup"><span data-stu-id="eab9c-168">Setup</span></span>  <br/> |<span data-ttu-id="eab9c-169">Hybrid-Mandanten</span><span class="sxs-lookup"><span data-stu-id="eab9c-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="eab9c-170">„HybridPSTNSite“ festlegen</span><span class="sxs-lookup"><span data-stu-id="eab9c-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="eab9c-171">Peer-Ziel für Fallback einrichten</span><span class="sxs-lookup"><span data-stu-id="eab9c-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="eab9c-172">„HybridPSTNSite“ festlegen</span><span class="sxs-lookup"><span data-stu-id="eab9c-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="eab9c-173">Peer-Ziel für Fallback einrichten</span><span class="sxs-lookup"><span data-stu-id="eab9c-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="eab9c-174">Einrichtung</span><span class="sxs-lookup"><span data-stu-id="eab9c-174">Setup</span></span>  <br/> |<span data-ttu-id="eab9c-175">Gateway</span><span class="sxs-lookup"><span data-stu-id="eab9c-175">Gateway</span></span>  <br/> |<span data-ttu-id="eab9c-176">Vermittlungsserver-Gateway **M:N**-Zuordnung an diesem Standort</span><span class="sxs-lookup"><span data-stu-id="eab9c-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="eab9c-177">PSTN-Gateways an den einzelnen PSTN-Standorten sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.</span><span class="sxs-lookup"><span data-stu-id="eab9c-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="eab9c-178">Einrichtung</span><span class="sxs-lookup"><span data-stu-id="eab9c-178">Setup</span></span>  <br/> |<span data-ttu-id="eab9c-179">Benutzer</span><span class="sxs-lookup"><span data-stu-id="eab9c-179">User</span></span>  <br/> |<span data-ttu-id="eab9c-180">„UserPSTNSettings“ festlegen</span><span class="sxs-lookup"><span data-stu-id="eab9c-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="eab9c-181">„UserPSTNSettings“ festlegen</span><span class="sxs-lookup"><span data-stu-id="eab9c-181">Set UserPSTNSettings</span></span>  <br/> |
   

