---
title: 'Lync Server 2013: Bestimmen der Anforderungen für externe A/V-Firewalls und Ports'
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
ms.openlocfilehash: 3c7b117f68719230151fd19050dbb080f6acde14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522582"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="31abe-102">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31abe-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31abe-103">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="31abe-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="31abe-104">Kommunikation mit Audio/Video (a/V) kann komplex sein.</span><span class="sxs-lookup"><span data-stu-id="31abe-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="31abe-105">Aufgrund der Art der in A/V verwendeten Protokolle und der Verwendung der Protokolle durch Clients und Server wird ein spezieller Abschnitt gerechtfertigt, um die Unterschiede zwischen Client-und Server Versionen zu erläutern.</span><span class="sxs-lookup"><span data-stu-id="31abe-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="31abe-106">Verwenden Sie die folgende A/V-Firewall und Port Tabelle, um die Firewall-Anforderungen zu ermitteln und welche Ports geöffnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31abe-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="31abe-107">Lesen Sie anschließend die Hinweise zur Netzwerkadressenübersetzung (Network Address Translation, NAT), da NAT auf viele verschiedene Arten implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="31abe-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="31abe-108">Ein ausführliches Beispiel für Firewall-Porteinstellungen finden Sie in den Referenzarchitekturen in [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="31abe-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="31abe-109">Allgemeine Protokollnutzung für UDP und TCP im Audio/Video-und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="31abe-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31abe-110">Audio/Video-Transport</span><span class="sxs-lookup"><span data-stu-id="31abe-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="31abe-111">Verwendung</span><span class="sxs-lookup"><span data-stu-id="31abe-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31abe-112">UDP</span><span class="sxs-lookup"><span data-stu-id="31abe-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="31abe-113">Bevorzugtes Transportschichtprotokoll für Audio und Video</span><span class="sxs-lookup"><span data-stu-id="31abe-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31abe-114">TCP</span><span class="sxs-lookup"><span data-stu-id="31abe-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="31abe-115">Fallback-Transportschichtprotokoll für Audio und Video</span><span class="sxs-lookup"><span data-stu-id="31abe-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="31abe-116">Erforderliches Transportschichtprotokoll für die Anwendungsfreigabe für Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31abe-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="31abe-117">Erforderliches Transportschichtprotokoll für die Dateiübertragung an lync Server 2010 und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31abe-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="31abe-118">Portanforderungen für die externe A/V-Firewall für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="31abe-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="31abe-119">Die Firewall-Portanforderungen für externe (und interne) SIP-und Konferenz Schnittstellen sind unabhängig von der Version des Clients oder der Version des Partnerverbund Partners konsistent.</span><span class="sxs-lookup"><span data-stu-id="31abe-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="31abe-120">Das gleiche gilt nicht für die externe Audio/Video-Edge-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="31abe-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="31abe-121">Für den Verbund mit Office Communications Server 2007 erfordert der A/V-Edgedienst, dass externe Firewallregeln den RTP/TCP-und RTP/UDP-Datenverkehr im 50.000-bis 59.999-Portbereich in beide Richtungen fließen lassen.</span><span class="sxs-lookup"><span data-stu-id="31abe-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="31abe-122">In der vorherigen Tabelle wird davon ausgegangen, dass lync Server 2013 der primäre Verbundpartner ist und für die Kommunikation mit einem der aufgeführten Partnerverbund Partnertypen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="31abe-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="31abe-123">Bei der Konfiguration des Audio/Video-Portbereichs von 50000-59.999 muss berücksichtigt werden, dass der Portbereich die Quell Ports für die Kommunikation mit Partnerverbund Partnern enthält.</span><span class="sxs-lookup"><span data-stu-id="31abe-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="31abe-124">Im einzelnen ist zu prüfen, ob eine Kommunikation von einem Partnerverbund initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="31abe-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="31abe-125">Die Kommunikation von den A/V-Edgedienst Ports im 50000-59.999-Bereich stellt eine Verbindung mit dem erwarteten Port TCP 443 der A/V-Edgedienst des Partners her.</span><span class="sxs-lookup"><span data-stu-id="31abe-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="31abe-126">Umgekehrt verfügt der eingehende Datenverkehr zu Ihrem A/V-Edgedienst Port TCP 443 über einen Quell Port im Bereich von 50000-59.999.</span><span class="sxs-lookup"><span data-stu-id="31abe-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="31abe-127">Für unterschiedliche Firewalls und Richtlinien für die Firewallverwaltung müssen möglicherweise nur die Zielregeln konfiguriert werden, oder es ist möglicherweise erforderlich, dass Quelle und Ziel konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="31abe-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="31abe-128">Wenn Ihre Anforderungen nur für Zielports gelten, sind die Anforderungen an Audio/Video:</span><span class="sxs-lookup"><span data-stu-id="31abe-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31abe-129">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="31abe-129">Source IP</span></span></th>
<th><span data-ttu-id="31abe-130">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="31abe-130">Destination IP</span></span></th>
<th><span data-ttu-id="31abe-131">Zielport</span><span class="sxs-lookup"><span data-stu-id="31abe-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31abe-132">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-133">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-133">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="31abe-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31abe-135">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-136">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-136">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="31abe-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31abe-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-138">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-139">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="31abe-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31abe-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-141">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-142">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="31abe-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="31abe-144">Wenn Ihre Richtlinien sowohl eingehende als auch ausgehende Firewall-Regeldefinitionen erfordern, sind die Anforderungen an Audio/Video:</span><span class="sxs-lookup"><span data-stu-id="31abe-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31abe-145">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="31abe-145">Source IP</span></span></th>
<th><span data-ttu-id="31abe-146">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="31abe-146">Destination IP</span></span></th>
<th><span data-ttu-id="31abe-147">Quellport</span><span class="sxs-lookup"><span data-stu-id="31abe-147">Source Port</span></span></th>
<th><span data-ttu-id="31abe-148">Zielport</span><span class="sxs-lookup"><span data-stu-id="31abe-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31abe-149">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-150">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-151">TCP 50000-59.999</span><span class="sxs-lookup"><span data-stu-id="31abe-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="31abe-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="31abe-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31abe-153">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-154">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="31abe-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="31abe-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="31abe-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31abe-157">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-157">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-158">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-159">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-159">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="31abe-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31abe-161">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-161">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-162">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31abe-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="31abe-163">Beliebig</span><span class="sxs-lookup"><span data-stu-id="31abe-163">Any</span></span></p></td>
<td><p><span data-ttu-id="31abe-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="31abe-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="31abe-165">Microsoft Office Communications Server 2007 erfordert eine etwas andere Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="31abe-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="31abe-166">Der TCP-und UDP-Portbereich von 50000-59.999 muss Open eingehend und Outbound sein.</span><span class="sxs-lookup"><span data-stu-id="31abe-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="31abe-167">Diese Anforderung gilt nur für Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="31abe-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="31abe-168">Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 benötigen nur den TCP-Bereich 50000-59.999 Open Outbound.</span><span class="sxs-lookup"><span data-stu-id="31abe-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="31abe-169">NAT-Anforderungen für den Edgedienst</span><span class="sxs-lookup"><span data-stu-id="31abe-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="31abe-170">Die folgenden NAT-Anforderungen gelten, wenn Sie nicht routingfähige private IP-Adressen für den Edgedienst konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="31abe-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="31abe-171">NAT kann nur mit dem DNS-Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31abe-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="31abe-172">NAT wird mit einer HLB-Edge-Topologie (Hardware Lastenausgleich) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31abe-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="31abe-173">NAT kann nur für die externe Edge-Schnittstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31abe-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="31abe-174">NAT wird auf der internen Edge-Schnittstelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31abe-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="31abe-175">NAT muss für einen eingehenden und ausgehenden Datenverkehr symmetrisch sein.</span><span class="sxs-lookup"><span data-stu-id="31abe-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="31abe-176">Für Datenverkehr aus dem Internet muss NAT die Ziel-IP-Adresse von der NAT-fähigen öffentlichen IP-Adresse des A/V-Edgedienst in die externe IP-Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="31abe-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="31abe-177">Die Quell-IP-Adresse muss intakt bleiben, damit der A/V-Edgedienst den optimalen Medienpfad finden kann.</span><span class="sxs-lookup"><span data-stu-id="31abe-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="31abe-178">In der folgenden Abbildung wurde beispielsweise die öffentliche IP-Adresse 131.107.155.30 in die externe IP-Adresse 10.45.16.10 (privat) geändert.</span><span class="sxs-lookup"><span data-stu-id="31abe-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="31abe-179">Die Quell-IP-Adresse blieb unverändert.</span><span class="sxs-lookup"><span data-stu-id="31abe-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="31abe-180">Für den Datenverkehr vom A/V-Edgedienst zum Internet muss NAT die Quell-IP-Adresse von der externen IP-Adresse des A/V-Edgedienst in die NAT-fähige öffentliche IP-Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="31abe-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="31abe-181">Beispiel: in der ausgehenden Richtung in der Abbildung unten wurde die externe IP-Adresse (privat) 10.45.16.10 in die öffentliche IP-Adresse 131.107.155.30 geändert.</span><span class="sxs-lookup"><span data-stu-id="31abe-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="31abe-182">**Die folgende Abbildung zeigt, wie NAT die Ziel-IP-Adresse für eingehenden Datenverkehr und die Quell-IP-Adresse für ausgehenden Datenverkehr ändert.**</span><span class="sxs-lookup"><span data-stu-id="31abe-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="31abe-183">![Ändern von Ziel-/Quell-IP-Adressen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Ändern von Ziel-/Quell-IP-Adressen")</span><span class="sxs-lookup"><span data-stu-id="31abe-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="31abe-184">Die wichtigsten Punkte hierbei sind:</span><span class="sxs-lookup"><span data-stu-id="31abe-184">The key points are:</span></span>

  - <span data-ttu-id="31abe-185">Datenverkehr, der auf dem Server mit dem A/V-Edgedienst eingehenden wird, ändert sich die Quell-IP-Adresse nicht, aber die IP-Zieladresse wird von 131.107.155.30 in die übersetzte IP-Adresse von 10.45.16.10 geändert.</span><span class="sxs-lookup"><span data-stu-id="31abe-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="31abe-186">Datenverkehr, der vom Server ausgeht, auf dem der A/V-Edgedienst zurück zur Arbeitsstation führt, ändert sich die Quell-IP-Adresse von der öffentlichen IP-Adresse des Servers zur öffentlichen IP-Adresse des Servers, auf dem der A/V-Edgedienst läuft.</span><span class="sxs-lookup"><span data-stu-id="31abe-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="31abe-187">Die Ziel-IP bleibt die öffentliche IP-Adresse der Arbeitsstation.</span><span class="sxs-lookup"><span data-stu-id="31abe-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="31abe-188">Nachdem das Paket das erste NAT-Gerät ausgehend verlassen hat, ändert die Regel auf dem NAT-Gerät die Quell-IP-Adresse des Servers, auf dem die A/V-Edgedienst-IP-Adresse der externen Schnittstelle (10.45.16.10) angegeben wird, in die öffentliche IP-Adresse (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="31abe-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

