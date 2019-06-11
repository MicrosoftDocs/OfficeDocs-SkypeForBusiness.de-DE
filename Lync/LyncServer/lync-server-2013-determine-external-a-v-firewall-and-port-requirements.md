---
title: 'Lync Server 2013: Ermitteln der Anforderungen für externe A/V-Firewalls und Ports'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="e0c2e-102">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0c2e-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0c2e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e0c2e-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e0c2e-104">Die Kommunikation zwischen Audio und Video (a/V) kann komplex sein.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="e0c2e-105">Aufgrund der Art der in A/V verwendeten Protokolle und der Verwendung der Protokolle durch Clients und Server wird ein spezieller Abschnitt für die Erläuterung der Unterschiede zwischen Client-und Server Versionen gerechtfertigt.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="e0c2e-106">Verwenden Sie die folgende A/V-Firewall und Port Tabelle, um die Firewall-Anforderungen und die zu öffnenden Ports zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="e0c2e-107">Überprüfen Sie dann die NAT-Terminologie (Network Address Translation), da NAT auf viele verschiedene Arten implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="e0c2e-108">Ein detailliertes Beispiel für Firewall-Porteinstellungen finden Sie in den Referenzarchitekturen in [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e0c2e-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="e0c2e-109">Allgemeine Protokollverwendung für UDP und TCP im Audio/Video-und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="e0c2e-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0c2e-110">Audio/Video-Transport</span><span class="sxs-lookup"><span data-stu-id="e0c2e-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="e0c2e-111">Verwendung</span><span class="sxs-lookup"><span data-stu-id="e0c2e-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0c2e-112">UDP</span><span class="sxs-lookup"><span data-stu-id="e0c2e-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-113">Bevorzugtes Transportschichtprotokoll für Audio und Video</span><span class="sxs-lookup"><span data-stu-id="e0c2e-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0c2e-114">TCP</span><span class="sxs-lookup"><span data-stu-id="e0c2e-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-115">Fall Back Transport-Layer-Protokoll für Audio und Video</span><span class="sxs-lookup"><span data-stu-id="e0c2e-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="e0c2e-116">Erforderliches Transportschichtprotokoll für die Anwendungsfreigabe für Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0c2e-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="e0c2e-117">Erforderliches Transportschichtprotokoll für die Dateiübertragung an lync Server 2010 und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0c2e-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="e0c2e-118">Externe A/V-Firewall-Port Anforderungen für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="e0c2e-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="e0c2e-119">Die Firewall-Portanforderungen für externe (und interne) SIP-und Konferenz Schnittstellen sind unabhängig von der Version des Clients oder der Version des Verbundpartners konsistent.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="e0c2e-120">Dies gilt nicht für die externe Schnittstelle Audio/Video Edge.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="e0c2e-121">Für den Verbund mit Office Communications Server 2007 erfordert der A/V-Edgedienst, dass externe Firewallregeln den RTP/TCP-und RTP/UDP-Datenverkehr im 50.000 bis 59.999-Portbereich in beide Richtungen fließen lassen.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="e0c2e-122">In der vorhergehenden Tabelle wird davon ausgegangen, dass lync Server 2013 der primäre Föderationspartner ist und für die Kommunikation mit einem der anderen Föderationspartner Typen konfiguriert ist, die aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="e0c2e-123">Bei der Konfiguration des Audio/Video-Portbereichs von 50000-59.999 muss berücksichtigt werden, dass der Portbereich die Quell Anschlüsse für die Kommunikation mit Verbundpartnern enthält.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="e0c2e-124">Bedenken Sie im Detail, dass eine Kommunikation von einem Föderationspartner initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="e0c2e-125">Die Kommunikation der a/v-Edgedienst-Ports im Bereich 50000-59.999 stellt eine Verbindung mit dem erwarteten Port TCP 443 des a/v-Edgedienst des Partners her.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="e0c2e-126">Umgekehrt hat der eingehende Datenverkehr zu Ihrem A/V Edge Service Port TCP 443 einen Quell Port im Bereich von 50000-59.999.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="e0c2e-127">Bei unterschiedlichen Firewalls und Richtlinien für die Firewall-Verwaltung müssen möglicherweise nur Zielregeln konfiguriert werden, oder es ist möglich, dass Quelle und Ziel konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="e0c2e-128">Wenn Ihre Anforderungen nur für Zielanschlüsse gelten, gelten die Anforderungen für Audio/Video:</span><span class="sxs-lookup"><span data-stu-id="e0c2e-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0c2e-129">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="e0c2e-129">Source IP</span></span></th>
<th><span data-ttu-id="e0c2e-130">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="e0c2e-130">Destination IP</span></span></th>
<th><span data-ttu-id="e0c2e-131">Zielport</span><span class="sxs-lookup"><span data-stu-id="e0c2e-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0c2e-132">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-133">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-133">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e0c2e-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0c2e-135">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-136">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-136">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e0c2e-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0c2e-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-139">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e0c2e-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0c2e-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-142">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e0c2e-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0c2e-144">Wenn für Ihre Richtlinien sowohl eingehende als auch ausgehende Firewall-Regeldefinitionen erforderlich sind, gelten die Anforderungen für Audio/Video:</span><span class="sxs-lookup"><span data-stu-id="e0c2e-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0c2e-145">Quell-IP</span><span class="sxs-lookup"><span data-stu-id="e0c2e-145">Source IP</span></span></th>
<th><span data-ttu-id="e0c2e-146">Ziel-IP</span><span class="sxs-lookup"><span data-stu-id="e0c2e-146">Destination IP</span></span></th>
<th><span data-ttu-id="e0c2e-147">Quellport</span><span class="sxs-lookup"><span data-stu-id="e0c2e-147">Source Port</span></span></th>
<th><span data-ttu-id="e0c2e-148">Zielport</span><span class="sxs-lookup"><span data-stu-id="e0c2e-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0c2e-149">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-150">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-151">TCP 50.000-59.999</span><span class="sxs-lookup"><span data-stu-id="e0c2e-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e0c2e-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0c2e-153">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e0c2e-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e0c2e-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0c2e-157">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-157">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-158">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-159">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-159">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e0c2e-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0c2e-161">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-161">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-162">A/V-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0c2e-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-163">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e0c2e-163">Any</span></span></p></td>
<td><p><span data-ttu-id="e0c2e-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e0c2e-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0c2e-165">Microsoft Office Communications Server 2007 erfordert eine etwas andere Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="e0c2e-166">Der TCP-und UDP-Portbereich von 50000-59.999 muss ein-und ausgehendes öffnen sein.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="e0c2e-167">Diese Anforderung gilt nur für Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="e0c2e-168">Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 erfordern nur den TCP-Bereich 50000-59.999 Open Outbound.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="e0c2e-169">NAT-Anforderungen für den Edgedienst</span><span class="sxs-lookup"><span data-stu-id="e0c2e-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="e0c2e-170">Die folgenden NAT-Anforderungen gelten, wenn Sie sich entscheiden, nicht routingfähige private IP-Adressen für den Edgedienst zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e0c2e-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="e0c2e-171">NAT kann nur mit dem DNS-Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="e0c2e-172">NAT wird von einer Edge-Topologie (Hardware Load Balancing) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="e0c2e-173">NAT kann nur auf der Schnittstelle des externen Edge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="e0c2e-174">NAT wird auf der Schnittstelle für den internen Edge nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="e0c2e-175">NAT muss für eingehenden und ausgehenden Datenverkehr symmetrisch sein.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="e0c2e-176">Für Datenverkehr aus dem Internet muss NAT die Ziel-IP-Adresse von der NAT-aktivierten öffentlichen IP-Adresse des A/V-Edge-Diensts in die externe IP-Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="e0c2e-177">Die Quell-IP-Adresse muss intakt bleiben, damit der A/V-Edgedienst den optimalen Medienpfad finden kann.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="e0c2e-178">In der folgenden Abbildung wird beispielsweise in der eingehenden Richtung die öffentliche IP-Adresse 131.107.155.30 in die externe IP-Adresse 10.45.16.10 (privat) geändert.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="e0c2e-179">Die Quell-IP-Adresse blieb unverändert.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="e0c2e-180">Für Datenverkehr vom a/v-Edgedienst zum Internet muss NAT die Quell-IP-Adresse von der externen IP-Adresse des a/v-Edgedienst in die NAT-fähige öffentliche IP-Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="e0c2e-181">In der folgenden Abbildung wird beispielsweise die externe (private) IP-Adresse 10.45.16.10 in die öffentliche IP-Adresse 131.107.155.30 geändert.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="e0c2e-182">**Die folgende Abbildung zeigt, wie NAT die Ziel-IP-Adresse für eingehenden Datenverkehr und die Quell-IP-Adresse für ausgehenden Datenverkehr ändert.**</span><span class="sxs-lookup"><span data-stu-id="e0c2e-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="e0c2e-183">![Ändern von Ziel-/Quell-IP-Adressen] (images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Ändern von Ziel-/Quell-IP-Adressen")</span><span class="sxs-lookup"><span data-stu-id="e0c2e-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="e0c2e-184">Die wichtigsten Punkte sind:</span><span class="sxs-lookup"><span data-stu-id="e0c2e-184">The key points are:</span></span>

  - <span data-ttu-id="e0c2e-185">Datenverkehr, der sich auf dem Server mit dem A/V-Edgedienst befindet, ändert sich die Quell-IP-Adresse nicht, aber die Ziel-IP-Adresse wird von 131.107.155.30 in die übersetzte IP-Adresse von 10.45.16.10 geändert.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="e0c2e-186">Datenverkehr von dem Server, auf dem der a/v-Edgedienst zurück zur Workstation läuft, ändert sich die Quell-IP-Adresse von der öffentlichen IP-Adresse des Servers zur öffentlichen IP-Adresse des Servers, auf dem der a/v-Edgedienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="e0c2e-187">Die Ziel-IP-Adresse bleibt die öffentliche IP-Adresse der Workstation.</span><span class="sxs-lookup"><span data-stu-id="e0c2e-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="e0c2e-188">Nachdem das Paket das erste NAT-Gerät ausgehoben hat, ändert die Regel auf dem NAT-Gerät die Quell-IP-Adresse des Servers, auf dem die externe Schnittstellen-IP-Adresse (10.45.16.10) des Edge-Diensts ausgeführt wird, in die öffentliche IP-Adresse (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="e0c2e-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

