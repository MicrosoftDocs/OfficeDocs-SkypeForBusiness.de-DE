---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="5977f-102">Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5977f-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5977f-103">_**Letztes Änderungsdatum des Themas:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="5977f-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="5977f-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013-Edgeserver-Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5977f-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="5977f-105">Die bemerkenswerteste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="5977f-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="5977f-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edge-Server oder Edge-Pool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="5977f-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="5977f-107">Neben IPv4 unterstützt der Edgeserver nun IPv6.</span><span class="sxs-lookup"><span data-stu-id="5977f-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="5977f-108">Aus Gründen der Übersichtlichkeit wird in den Szenarien nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="5977f-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="5977f-109">**Unternehmens Umkreisnetzwerk für skalierten konsolidierten Edge mit privaten IP-Adressen mithilfe von NAT**</span><span class="sxs-lookup"><span data-stu-id="5977f-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="5977f-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead] (images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="5977f-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="5977f-111">Port- und Protokolldetails</span><span class="sxs-lookup"><span data-stu-id="5977f-111">Port and Protocol Details</span></span>

<span data-ttu-id="5977f-112">Es wird empfohlen, nur die Ports zu öffnen, die erforderlich sind, um die Funktionalität zu unterstützen, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5977f-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="5977f-113">Damit der Remotezugriff für jeden Edgedienst funktionieren kann, ist es zwingend erforderlich, dass der SIP-Datenverkehr bidirektional wie in der Abbildung des eingehenden/ausgehenden Edge-Traffics durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="5977f-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="5977f-114">Anders ausgedrückt: das SIP-Messaging zum und vom Access-Edgedienst ist an Instant Messaging (im), Anwesenheitsinformationen, Webkonferenzen, Audio/Video (A/V) und Föderation beteiligt.</span><span class="sxs-lookup"><span data-stu-id="5977f-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="5977f-115">Zusammenfassung der Firewall für den konsolidierten skalierten Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="5977f-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5977f-116">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5977f-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5977f-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-117">Source IP address</span></span></th>
<th><span data-ttu-id="5977f-118">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-118">Destination IP address</span></span></th>
<th><span data-ttu-id="5977f-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5977f-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5977f-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5977f-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5977f-121">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-121">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-122">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</span><span class="sxs-lookup"><span data-stu-id="5977f-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="5977f-123">Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen</span><span class="sxs-lookup"><span data-stu-id="5977f-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5977f-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5977f-125">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</span><span class="sxs-lookup"><span data-stu-id="5977f-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="5977f-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-126">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-127">Der XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-Föderationen</span><span class="sxs-lookup"><span data-stu-id="5977f-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-128">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="5977f-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="5977f-129">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-130">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-130">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-131">Zertifikatsperrung/CRL-Prüfung und-Abruf</span><span class="sxs-lookup"><span data-stu-id="5977f-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="5977f-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="5977f-133">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-134">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-135">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="5977f-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="5977f-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="5977f-137">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-138">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-139">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="5977f-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-140">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5977f-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-141">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-142">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-143">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="5977f-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-144">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-145">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-145">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-146">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-147">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="5977f-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-148">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-149">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-150">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-151">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="5977f-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-152">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5977f-153">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-153">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-154">Edge-Server-Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-155">Web-Konferenzmedien</span><span class="sxs-lookup"><span data-stu-id="5977f-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-156">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5977f-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5977f-157">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-158">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-158">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-159">Erforderlich für die Föderation mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 ausführen.</span><span class="sxs-lookup"><span data-stu-id="5977f-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5977f-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5977f-161">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-162">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-162">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-163">Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5977f-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-164">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5977f-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5977f-165">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-165">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-166">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-167">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="5977f-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5977f-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5977f-169">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-169">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-170">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-171">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="5977f-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-172">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5977f-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5977f-173">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-174">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-174">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-175">3478 Outbound wird verwendet, um die Version von Edgeserver zu ermitteln, mit der lync Server kommuniziert, sowie für Mediendatenverkehr vom Edge-Server-zu-Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="5977f-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="5977f-176">Erforderlich für den Verbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5977f-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-177">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5977f-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5977f-178">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-178">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-179">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-180">Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5977f-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-181">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5977f-182">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-182">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-183">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-184">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-185">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5977f-186">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-187">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-187">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-188">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="5977f-189">Zusammenfassung der Firewall für den konsolidierten skalierten Edge, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: interne Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="5977f-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5977f-190">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5977f-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5977f-191">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-191">Source IP address</span></span></th>
<th><span data-ttu-id="5977f-192">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-192">Destination IP address</span></span></th>
<th><span data-ttu-id="5977f-193">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5977f-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5977f-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="5977f-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="5977f-195">Any (kann als Front-End-Server Adresse oder IP-Adresse des Front-End-Pools definiert werden, auf der der XMPP-Gatewayserver ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="5977f-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="5977f-196">IP-Adresse des Edge-Server-internen Interfaces</span><span class="sxs-lookup"><span data-stu-id="5977f-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5977f-197">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="5977f-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-199">Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="5977f-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="5977f-200">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-201">Ausgehender SIP-Datenverkehr (von Director, Director-Pool-IP-Adresse, Front-End-Server oder IP-Adresse des Front-End-Pools) zu einer internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-203">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-204">Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="5977f-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="5977f-205">Eingehende SIP-Datenverkehr (an Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools) aus der internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="5977f-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="5977f-207">Any (kann als Front-End-Server-IP-Adresse oder jede IP-Adresse eines Front-End-Servers in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="5977f-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="5977f-208">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-209">Webkonferenzen-Datenverkehr vom Front-End-Server oder jedem Front-End-Server, falls in einem Pool, zu einer internen Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="5977f-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="5977f-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="5977f-211">Any (kann als Front-End-Server-IP-Adresse oder IP-Adresse des Front-End-Pools oder einer überlebensfähigen Branch-Appliance oder eines Überlebenden Branch-Servers mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="5977f-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="5977f-212">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-213">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) vom Front-End-Server oder der IP-Adresse des Front-End-Pools oder von einer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mit diesem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5977f-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-214">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5977f-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5977f-215">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-215">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-216">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-217">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="5977f-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-218">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5977f-219">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-219">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-220">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-221">Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survival-Branch-Appliance oder einem Überlebenden Branch-Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5977f-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="5977f-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="5977f-223">Any (kann als die IP-Adresse des Front-End-Servers oder-Pools definiert werden, der den zentralen Verwaltungsspeicher enthält)</span><span class="sxs-lookup"><span data-stu-id="5977f-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="5977f-224">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-225">Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5977f-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="5977f-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="5977f-227">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-227">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-228">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-229">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="5977f-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="5977f-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="5977f-231">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-231">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-232">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-233">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="5977f-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="5977f-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="5977f-235">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-235">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-236">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5977f-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5977f-237">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="5977f-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="5977f-238">Zusammenfassung der Firewall für den Verbund</span><span class="sxs-lookup"><span data-stu-id="5977f-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5977f-239">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5977f-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5977f-240">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-240">Source IP address</span></span></th>
<th><span data-ttu-id="5977f-241">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-241">Destination IP address</span></span></th>
<th><span data-ttu-id="5977f-242">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5977f-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5977f-243">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-244">Access Edge Service (öffentliche IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5977f-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="5977f-245">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-245">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-246">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="5977f-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5977f-247">Zusammenfassung der Firewall – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="5977f-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5977f-248">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5977f-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5977f-249">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-249">Source IP address</span></span></th>
<th><span data-ttu-id="5977f-250">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="5977f-250">Destination IP address</span></span></th>
<th><span data-ttu-id="5977f-251">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5977f-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5977f-252">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-253">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="5977f-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="5977f-254">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-255">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="5977f-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-256">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5977f-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5977f-257">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-258">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="5977f-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="5977f-259">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="5977f-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-260">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5977f-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5977f-261">Clients</span><span class="sxs-lookup"><span data-stu-id="5977f-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="5977f-262">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-263">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="5977f-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-264">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="5977f-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5977f-265">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-266">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="5977f-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5977f-267">Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn die Konnektivität für öffentliche Chats konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="5977f-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-268">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5977f-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5977f-269">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-270">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="5977f-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5977f-271">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="5977f-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-272">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5977f-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5977f-273">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="5977f-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5977f-274">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="5977f-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5977f-275">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="5977f-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="5977f-276">Zusammenfassung der Firewall für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="5977f-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5977f-277">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="5977f-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5977f-278">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5977f-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="5977f-279">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="5977f-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="5977f-280">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5977f-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5977f-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5977f-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5977f-282">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-282">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-283">IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</span><span class="sxs-lookup"><span data-stu-id="5977f-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5977f-284">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="5977f-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5977f-285">Ermöglicht die Kommunikation mit dem Edge-Server-XMPP-Proxy von Federated XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="5977f-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5977f-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5977f-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5977f-287">IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</span><span class="sxs-lookup"><span data-stu-id="5977f-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5977f-288">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-288">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-289">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="5977f-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5977f-290">Ermöglicht die Kommunikation vom Edge Server XMPP-Proxy an Federated XMPP-Partner</span><span class="sxs-lookup"><span data-stu-id="5977f-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5977f-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="5977f-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="5977f-292">Beliebig</span><span class="sxs-lookup"><span data-stu-id="5977f-292">Any</span></span></p></td>
<td><p><span data-ttu-id="5977f-293">Jede interne Edge-Server-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="5977f-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="5977f-294">Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zur internen IP-Adresse des Edge-Servers oder zur internen IP-Adresse jedes Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="5977f-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

