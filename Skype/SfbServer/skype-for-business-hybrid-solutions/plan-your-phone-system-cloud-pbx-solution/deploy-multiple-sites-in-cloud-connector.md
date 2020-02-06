---
title: Bereitstellen mehrerer Standorte in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informationen zum Bereitstellen mehrerer PSTN-Websites in Cloud Connector Edition.
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799695"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="39b3c-103">Bereitstellen mehrerer Standorte in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="39b3c-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="39b3c-104">Informationen zum Bereitstellen mehrerer PSTN-Websites in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="39b3c-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="39b3c-p101">In diesem Abschnitt wird die Bereitstellung mehrerer PSTN-Standorte (Public Switched Telephone Network, Telefonfestnetz) erläutert. Standorte werden jeweils nacheinander wie bei der Bereitstellung eines einzelnen Standorts bereitgestellt. In diesem Thema werden Überlegungen zu Standorten und Unterschiede zwischen Standorten in einer Bereitstellung mit mehreren Standorten beschrieben. </span><span class="sxs-lookup"><span data-stu-id="39b3c-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="39b3c-108">Mehrere PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="39b3c-109">Die folgende Abbildung zeigt eine Beispielkonfiguration für die Bereitstellung von Skype for Business Cloud Connector Edition für verschiedene PSTN-Websites.</span><span class="sxs-lookup"><span data-stu-id="39b3c-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="39b3c-110">Stellen Sie vor dem Starten der Bereitstellung sicher, dass Ihre Konfigurationseinstellungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="39b3c-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="39b3c-111">PSTN-Standort 1</span><span class="sxs-lookup"><span data-stu-id="39b3c-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="39b3c-112">PSTN-Standort 2</span><span class="sxs-lookup"><span data-stu-id="39b3c-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="39b3c-113">Führen Sie für jede PSTN-Website, die Sie hinzufügen möchten, die Schritte unter [Bereitstelleneiner einzelnen Website in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)aus.</span><span class="sxs-lookup"><span data-stu-id="39b3c-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39b3c-114">Der freigegebene Ordner für die Vorbereitung hoher Verfügbarkeit wird pro PSTN-Standort erstellt.</span><span class="sxs-lookup"><span data-stu-id="39b3c-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="39b3c-115">Der freigegebene Ordner **muss** sich zwischen den PSTN-Standorten unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="39b3c-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="39b3c-116">Verwenden Sie nicht denselben freigegebenen Ordner für mehrere Websites. #a0</span><span class="sxs-lookup"><span data-stu-id="39b3c-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="39b3c-117">Bereitstellung eines einzelnen Standorts mit hoher Verfügbarkeit im Vergleich zur Bereitstellung mehrerer Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="39b3c-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="39b3c-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="39b3c-119">In der folgenden Tabelle sind die Unterschiede zwischen der Bereitstellung an einem einzelnen Standort mit hoher Verfügbarkeit und der Bereitstellung an mehreren Standorten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="39b3c-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="39b3c-120">**Kategorie**</span><span class="sxs-lookup"><span data-stu-id="39b3c-120">**Category**</span></span>|<span data-ttu-id="39b3c-121">**Element**</span><span class="sxs-lookup"><span data-stu-id="39b3c-121">**Item**</span></span>|<span data-ttu-id="39b3c-122">**Einzelner Standort mit hoher Verfügbarkeit**</span><span class="sxs-lookup"><span data-stu-id="39b3c-122">**Single-Site with HA**</span></span>|<span data-ttu-id="39b3c-123">**Mehrere Standorte**</span><span class="sxs-lookup"><span data-stu-id="39b3c-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39b3c-124">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-124">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-125">Appliance-Hostname</span><span class="sxs-lookup"><span data-stu-id="39b3c-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="39b3c-126">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-127">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-128">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="39b3c-128">Setup</span></span>  <br/> |<span data-ttu-id="39b3c-129">Freigegebener Ordner</span><span class="sxs-lookup"><span data-stu-id="39b3c-129">Shared folder</span></span>  <br/> |<span data-ttu-id="39b3c-130">Erfordert **denselben** freigegebenen Ordner für Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="39b3c-131">Benötigt für jede Appliance einen **unterschiedlichen** freigegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="39b3c-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="39b3c-132">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-132">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="39b3c-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="39b3c-134">Benötigt für alle Appliances **dieselbe** Domäne.</span><span class="sxs-lookup"><span data-stu-id="39b3c-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="39b3c-135">Benötigt **dieselbe** Domäne für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-136">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-136">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-137">SIP-Domänen</span><span class="sxs-lookup"><span data-stu-id="39b3c-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="39b3c-138">Domänennamen und Reihenfolge sollten für Appliances **identisch** sein.</span><span class="sxs-lookup"><span data-stu-id="39b3c-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-139">Domänennamen und Reihenfolge sollten für PSTN-Websites **identisch** sein.</span><span class="sxs-lookup"><span data-stu-id="39b3c-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-140">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-140">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-141">Standortname</span><span class="sxs-lookup"><span data-stu-id="39b3c-141">Site name</span></span>  <br/> |<span data-ttu-id="39b3c-142">**Identischer** Standortname für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="39b3c-143">**Unterschiedlicher** Standortname für jeden einzelnen PSTN-Standort</span><span class="sxs-lookup"><span data-stu-id="39b3c-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-144">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-144">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-145">Servernamen</span><span class="sxs-lookup"><span data-stu-id="39b3c-145">Server names</span></span>  <br/> |<span data-ttu-id="39b3c-146">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-147">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-148">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-148">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-149">FQDNs interner Pools</span><span class="sxs-lookup"><span data-stu-id="39b3c-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="39b3c-150">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-151">**Identisch** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-152">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-152">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-153">Interne IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="39b3c-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="39b3c-154">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-155">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-156">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-156">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-157">Externer FQDN</span><span class="sxs-lookup"><span data-stu-id="39b3c-157">External FQDN</span></span>  <br/> |<span data-ttu-id="39b3c-158">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-159">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-160">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-160">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-161">Externe IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="39b3c-161">External IPs</span></span>  <br/> |<span data-ttu-id="39b3c-162">**Unterschiedlich** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-163">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-164">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-164">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-165">Einstellungen für PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="39b3c-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="39b3c-166">**Identisch** für alle Appliances</span><span class="sxs-lookup"><span data-stu-id="39b3c-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="39b3c-167">**Unterschiedlich** für alle PSTN-Standorte</span><span class="sxs-lookup"><span data-stu-id="39b3c-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="39b3c-168">Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39b3c-168">Configure</span></span>  <br/> |<span data-ttu-id="39b3c-169">DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="39b3c-169">DNS record</span></span>  <br/> |<span data-ttu-id="39b3c-170">Hinzufügen von Datensätzen mit **denselben** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="39b3c-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="39b3c-171">Datensätze mit **unterschiedlichen** FQDNs für externen Zugriff und **unterschiedlichen** IP-Adressen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="39b3c-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="39b3c-172">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="39b3c-172">Setup</span></span>  <br/> |<span data-ttu-id="39b3c-173">Hybrid Mandant</span><span class="sxs-lookup"><span data-stu-id="39b3c-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="39b3c-174">„HybridPSTNSite“ festlegen</span><span class="sxs-lookup"><span data-stu-id="39b3c-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="39b3c-175">Peer-Ziel für Fallback einrichten</span><span class="sxs-lookup"><span data-stu-id="39b3c-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="39b3c-176">„HybridPSTNSite“ festlegen</span><span class="sxs-lookup"><span data-stu-id="39b3c-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="39b3c-177">Peer-Ziel für Fallback einrichten</span><span class="sxs-lookup"><span data-stu-id="39b3c-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="39b3c-178">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="39b3c-178">Setup</span></span>  <br/> |<span data-ttu-id="39b3c-179">Gateway</span><span class="sxs-lookup"><span data-stu-id="39b3c-179">Gateway</span></span>  <br/> |<span data-ttu-id="39b3c-180">Vermittlungsserver-Gateway **M:N**-Zuordnung an diesem Standort</span><span class="sxs-lookup"><span data-stu-id="39b3c-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="39b3c-181">PSTN-Gateways an den einzelnen PSTN-Standorten sollten nur Verbindungen mit Vermittlungsservern am gleichen Standort herstellen.</span><span class="sxs-lookup"><span data-stu-id="39b3c-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="39b3c-182">Installationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="39b3c-182">Setup</span></span>  <br/> |<span data-ttu-id="39b3c-183">Benutzer</span><span class="sxs-lookup"><span data-stu-id="39b3c-183">User</span></span>  <br/> |<span data-ttu-id="39b3c-184">„UserPSTNSettings“ festlegen</span><span class="sxs-lookup"><span data-stu-id="39b3c-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="39b3c-185">„UserPSTNSettings“ festlegen</span><span class="sxs-lookup"><span data-stu-id="39b3c-185">Set UserPSTNSettings</span></span>  <br/> |
   

