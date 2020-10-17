---
title: 'Lync Server 2013: Bestimmen der Anforderungen für externe A/V-Firewalls und Ports'
description: 'Lync Server 2013: Bestimmen der externen A/V-Firewall-und Portanforderungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550931"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="bed0c-103">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed0c-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed0c-104">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bed0c-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bed0c-105">Kommunikation mit Audio/Video (a/V) kann komplex sein.</span><span class="sxs-lookup"><span data-stu-id="bed0c-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="bed0c-106">Aufgrund der Art der in A/V verwendeten Protokolle und der Verwendung der Protokolle durch Clients und Server wird ein spezieller Abschnitt gerechtfertigt, um die Unterschiede zwischen Client-und Server Versionen zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="bed0c-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="bed0c-107">Verwenden Sie die folgende A/V-Firewall und Port Tabelle, um die Firewall-Anforderungen zu ermitteln und welche Ports geöffnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bed0c-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="bed0c-108">Lesen Sie anschließend die Hinweise zur Netzwerkadressenübersetzung (Network Address Translation, NAT), da NAT auf viele verschiedene Arten implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bed0c-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="bed0c-109">Ein ausführliches Beispiel für Firewall-Porteinstellungen finden Sie in den Referenzarchitekturen in [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="bed0c-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="bed0c-110">Allgemeine Protokollnutzung für UDP und TCP im Audio/Video-und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="bed0c-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed0c-111">Audio/Video-Transport</span><span class="sxs-lookup"><span data-stu-id="bed0c-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="bed0c-112">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bed0c-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed0c-113">UDP</span><span class="sxs-lookup"><span data-stu-id="bed0c-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="bed0c-114">Bevorzugtes Transportschichtprotokoll für Audio und Video</span><span class="sxs-lookup"><span data-stu-id="bed0c-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed0c-115">TCP</span><span class="sxs-lookup"><span data-stu-id="bed0c-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="bed0c-116">Fallback-Transportschichtprotokoll für Audio und Video</span><span class="sxs-lookup"><span data-stu-id="bed0c-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="bed0c-117">Erforderliches Transportschichtprotokoll für die Anwendungsfreigabe für Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed0c-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="bed0c-118">Erforderliches Transportschichtprotokoll für die Dateiübertragung an lync Server 2010 und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed0c-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="bed0c-119">Portanforderungen für die externe A/V-Firewall für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="bed0c-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="bed0c-120">Die Firewall-Portanforderungen für externe (und interne) SIP-und Konferenz Schnittstellen sind unabhängig von der Version des Clients oder der Version des Partnerverbund Partners konsistent.</span><span class="sxs-lookup"><span data-stu-id="bed0c-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="bed0c-121">Das gleiche gilt nicht für die externe Audio/Video-Edge-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bed0c-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="bed0c-122">Für den Verbund mit Office Communications Server 2007 erfordert der A/V-Edgedienst, dass externe Firewallregeln den RTP/TCP-und RTP/UDP-Datenverkehr im 50.000-bis 59.999-Portbereich in beide Richtungen fließen lassen.</span><span class="sxs-lookup"><span data-stu-id="bed0c-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="bed0c-123">In der vorherigen Tabelle wird davon ausgegangen, dass lync Server 2013 der primäre Verbundpartner ist und für die Kommunikation mit einem der aufgeführten Partnerverbund Partnertypen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bed0c-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="bed0c-124">Bei der Konfiguration des Audio/Video-Portbereichs von 50000-59.999 muss berücksichtigt werden, dass der Portbereich die Quell Ports für die Kommunikation mit Partnerverbund Partnern enthält.</span><span class="sxs-lookup"><span data-stu-id="bed0c-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="bed0c-125">Im einzelnen ist zu prüfen, ob eine Kommunikation von einem Partnerverbund initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="bed0c-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="bed0c-126">Die Kommunikation von den A/V-Edgedienst Ports im 50000-59.999-Bereich stellt eine Verbindung mit dem erwarteten Port TCP 443 der A/V-Edgedienst des Partners her.</span><span class="sxs-lookup"><span data-stu-id="bed0c-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="bed0c-127">Umgekehrt verfügt der eingehende Datenverkehr zu Ihrem A/V-Edgedienst Port TCP 443 über einen Quell Port im Bereich von 50000-59.999.</span><span class="sxs-lookup"><span data-stu-id="bed0c-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="bed0c-128">Für unterschiedliche Firewalls und Richtlinien für die Firewallverwaltung müssen möglicherweise nur die Zielregeln konfiguriert werden, oder es ist möglicherweise erforderlich, dass Quelle und Ziel konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="bed0c-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="bed0c-129">Wenn Ihre Anforderungen nur für Zielports gelten, sind die Anforderungen an Audio/Video:</span><span class="sxs-lookup"><span data-stu-id="bed0c-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed0c-130">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="bed0c-130">Source IP</span></span></th>
<th><span data-ttu-id="bed0c-131">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="bed0c-131">Destination IP</span></span></th>
<th><span data-ttu-id="bed0c-132">Zielport</span><span class="sxs-lookup"><span data-stu-id="bed0c-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed0c-133">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-134">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="bed0c-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed0c-136">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-137">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-137">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="bed0c-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed0c-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-139">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-140">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="bed0c-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed0c-142">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-142">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-143">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="bed0c-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bed0c-145">Wenn Ihre Richtlinien sowohl eingehende als auch ausgehende Firewall-Regeldefinitionen erfordern, sind die Anforderungen an Audio/Video:</span><span class="sxs-lookup"><span data-stu-id="bed0c-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed0c-146">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="bed0c-146">Source IP</span></span></th>
<th><span data-ttu-id="bed0c-147">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="bed0c-147">Destination IP</span></span></th>
<th><span data-ttu-id="bed0c-148">Quellport</span><span class="sxs-lookup"><span data-stu-id="bed0c-148">Source Port</span></span></th>
<th><span data-ttu-id="bed0c-149">Zielport</span><span class="sxs-lookup"><span data-stu-id="bed0c-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed0c-150">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-151">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-151">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-152">TCP 50000-59.999</span><span class="sxs-lookup"><span data-stu-id="bed0c-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="bed0c-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="bed0c-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed0c-154">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-155">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-155">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="bed0c-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="bed0c-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="bed0c-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bed0c-158">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-158">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-159">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-160">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-160">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="bed0c-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed0c-162">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-162">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-163">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bed0c-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="bed0c-164">Beliebig</span><span class="sxs-lookup"><span data-stu-id="bed0c-164">Any</span></span></p></td>
<td><p><span data-ttu-id="bed0c-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="bed0c-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="bed0c-166">Microsoft Office Communications Server 2007 erfordert eine etwas andere Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bed0c-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="bed0c-167">Der TCP-und UDP-Portbereich von 50000-59.999 muss Open eingehend und Outbound sein.</span><span class="sxs-lookup"><span data-stu-id="bed0c-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="bed0c-168">Diese Anforderung gilt nur für Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="bed0c-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="bed0c-169">Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 benötigen nur den TCP-Bereich 50000-59.999 Open Outbound.</span><span class="sxs-lookup"><span data-stu-id="bed0c-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="bed0c-170">NAT-Anforderungen für den Edgedienst</span><span class="sxs-lookup"><span data-stu-id="bed0c-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="bed0c-171">Die folgenden NAT-Anforderungen gelten, wenn Sie nicht routingfähige private IP-Adressen für den Edgedienst konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="bed0c-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="bed0c-172">NAT kann nur mit dem DNS-Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed0c-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="bed0c-173">NAT wird mit einer HLB-Edge-Topologie (Hardware Lastenausgleich) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bed0c-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="bed0c-174">NAT kann nur für die externe Edge-Schnittstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed0c-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="bed0c-175">NAT wird auf der internen Edge-Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bed0c-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="bed0c-176">NAT muss für einen eingehenden und ausgehenden Datenverkehr symmetrisch sein.</span><span class="sxs-lookup"><span data-stu-id="bed0c-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="bed0c-177">Für Datenverkehr aus dem Internet muss NAT die Ziel-IP-Adresse von der NAT-fähigen öffentlichen IP-Adresse des A/V-Edgedienst in die externe IP-Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="bed0c-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="bed0c-178">Die Quell-IP-Adresse muss intakt bleiben, damit der A/V-Edgedienst den optimalen Medienpfad finden kann.</span><span class="sxs-lookup"><span data-stu-id="bed0c-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="bed0c-179">In der folgenden Abbildung wurde beispielsweise die öffentliche IP-Adresse 131.107.155.30 in die externe IP-Adresse 10.45.16.10 (privat) geändert.</span><span class="sxs-lookup"><span data-stu-id="bed0c-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="bed0c-180">Die Quell-IP-Adresse blieb unverändert.</span><span class="sxs-lookup"><span data-stu-id="bed0c-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="bed0c-181">Für den Datenverkehr vom A/V-Edgedienst zum Internet muss NAT die Quell-IP-Adresse von der externen IP-Adresse des A/V-Edgedienst in die NAT-fähige öffentliche IP-Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="bed0c-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="bed0c-182">Beispiel: in der ausgehenden Richtung in der Abbildung unten wurde die externe IP-Adresse (privat) 10.45.16.10 in die öffentliche IP-Adresse 131.107.155.30 geändert.</span><span class="sxs-lookup"><span data-stu-id="bed0c-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="bed0c-183">**Die folgende Abbildung zeigt, wie NAT die Ziel-IP-Adresse für eingehenden Datenverkehr und die Quell-IP-Adresse für ausgehenden Datenverkehr ändert.**</span><span class="sxs-lookup"><span data-stu-id="bed0c-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="bed0c-184">![Ändern von Ziel-/Quell-IP-Adressen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Ändern von Ziel-/Quell-IP-Adressen")</span><span class="sxs-lookup"><span data-stu-id="bed0c-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="bed0c-185">Die wichtigsten Punkte hierbei sind:</span><span class="sxs-lookup"><span data-stu-id="bed0c-185">The key points are:</span></span>

  - <span data-ttu-id="bed0c-186">Datenverkehr, der auf dem Server mit dem A/V-Edgedienst eingehenden wird, ändert sich die Quell-IP-Adresse nicht, aber die IP-Zieladresse wird von 131.107.155.30 in die übersetzte IP-Adresse von 10.45.16.10 geändert.</span><span class="sxs-lookup"><span data-stu-id="bed0c-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="bed0c-187">Datenverkehr, der vom Server ausgeht, auf dem der A/V-Edgedienst zurück zur Arbeitsstation führt, ändert sich die Quell-IP-Adresse von der öffentlichen IP-Adresse des Servers zur öffentlichen IP-Adresse des Servers, auf dem der A/V-Edgedienst läuft.</span><span class="sxs-lookup"><span data-stu-id="bed0c-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="bed0c-188">Die Ziel-IP bleibt die öffentliche IP-Adresse der Arbeitsstation.</span><span class="sxs-lookup"><span data-stu-id="bed0c-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="bed0c-189">Nachdem das Paket das erste NAT-Gerät ausgehend verlassen hat, ändert die Regel auf dem NAT-Gerät die Quell-IP-Adresse des Servers, auf dem die A/V-Edgedienst-IP-Adresse der externen Schnittstelle (10.45.16.10) angegeben wird, in die öffentliche IP-Adresse (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="bed0c-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

