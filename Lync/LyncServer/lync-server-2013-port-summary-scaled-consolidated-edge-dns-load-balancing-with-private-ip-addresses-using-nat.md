---
title: 'Lync Server 2013: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c26dfe63e468d7b8d6f4ae557c0b84af2ffceaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="11485-102">Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11485-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11485-103">_**Letztes Änderungsstand des Themas:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="11485-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="11485-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="11485-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="11485-105">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="11485-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="11485-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="11485-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="11485-107">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="11485-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="11485-108">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="11485-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="11485-109">**Unternehmens Umkreisnetzwerk für einen skalierten konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT**</span><span class="sxs-lookup"><span data-stu-id="11485-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="11485-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="11485-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="11485-111">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="11485-111">Port and Protocol Details</span></span>

<span data-ttu-id="11485-112">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="11485-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="11485-113">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt).</span><span class="sxs-lookup"><span data-stu-id="11485-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="11485-114">Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11485-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="11485-115">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="11485-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11485-116">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="11485-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11485-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-117">Source IP address</span></span></th>
<th><span data-ttu-id="11485-118">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-118">Destination IP address</span></span></th>
<th><span data-ttu-id="11485-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11485-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11485-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11485-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11485-121">Any</span><span class="sxs-lookup"><span data-stu-id="11485-121">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-122">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="11485-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="11485-123">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="11485-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11485-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11485-125">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="11485-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="11485-126">Any</span><span class="sxs-lookup"><span data-stu-id="11485-126">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-127">XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-verbünden</span><span class="sxs-lookup"><span data-stu-id="11485-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-128">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="11485-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="11485-129">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-130">Any</span><span class="sxs-lookup"><span data-stu-id="11485-130">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-131">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="11485-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="11485-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="11485-133">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-134">Any</span><span class="sxs-lookup"><span data-stu-id="11485-134">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-135">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="11485-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="11485-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="11485-137">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-138">Any</span><span class="sxs-lookup"><span data-stu-id="11485-138">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-139">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="11485-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-140">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11485-141">Any</span><span class="sxs-lookup"><span data-stu-id="11485-141">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-142">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-143">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="11485-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-144">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-145">Any</span><span class="sxs-lookup"><span data-stu-id="11485-145">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-146">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-147">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="11485-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-148">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-149">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-150">Any</span><span class="sxs-lookup"><span data-stu-id="11485-150">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-151">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="11485-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-152">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11485-153">Any</span><span class="sxs-lookup"><span data-stu-id="11485-153">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-154">Edgeserver Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-155">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="11485-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-156">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="11485-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11485-157">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-158">Any</span><span class="sxs-lookup"><span data-stu-id="11485-158">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-159">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="11485-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="11485-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11485-161">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-162">Any</span><span class="sxs-lookup"><span data-stu-id="11485-162">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-163">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="11485-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-164">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="11485-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11485-165">Any</span><span class="sxs-lookup"><span data-stu-id="11485-165">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-166">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-167">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="11485-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="11485-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11485-169">Any</span><span class="sxs-lookup"><span data-stu-id="11485-169">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-170">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-171">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="11485-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-172">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11485-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11485-173">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-174">Any</span><span class="sxs-lookup"><span data-stu-id="11485-174">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-175">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="11485-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="11485-176">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="11485-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-177">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11485-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11485-178">Any</span><span class="sxs-lookup"><span data-stu-id="11485-178">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-179">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-180">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11485-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-181">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11485-182">Any</span><span class="sxs-lookup"><span data-stu-id="11485-182">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-183">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-184">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-185">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11485-186">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-187">Any</span><span class="sxs-lookup"><span data-stu-id="11485-187">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-188">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="11485-189">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: interne Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="11485-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11485-190">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="11485-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11485-191">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-191">Source IP address</span></span></th>
<th><span data-ttu-id="11485-192">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-192">Destination IP address</span></span></th>
<th><span data-ttu-id="11485-193">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="11485-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11485-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="11485-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="11485-195">Any (kann als Front-End-Server Adresse definiert werden oder Front-End-Pool IP-Adresse, die den XMPP-Gatewaydienst ausführt)</span><span class="sxs-lookup"><span data-stu-id="11485-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="11485-196">IP-Adresse Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="11485-197">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="11485-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-199">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="11485-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="11485-200">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-201">Ausgehender SIP-Datenverkehr (von Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) zu Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-203">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-204">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="11485-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="11485-205">Eingehender SIP-Datenverkehr (an Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="11485-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="11485-207">Any (kann als Front-End-Server IP-Adresse oder jede Front-End-Server IP-Adresse in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="11485-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="11485-208">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-209">Webkonferenz Datenverkehr von Front-End-Server oder jeder Front-End-Server in einem Pool an Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="11485-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="11485-211">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="11485-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="11485-212">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-213">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="11485-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-214">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11485-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11485-215">Any</span><span class="sxs-lookup"><span data-stu-id="11485-215">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-216">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-217">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="11485-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-218">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11485-219">Any</span><span class="sxs-lookup"><span data-stu-id="11485-219">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-220">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-221">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="11485-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="11485-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="11485-223">Any (kann als Front-End-Server-IP-Adresse oder als Pool mit dem zentralen Verwaltungsspeicher definiert werden)</span><span class="sxs-lookup"><span data-stu-id="11485-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="11485-224">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-225">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="11485-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="11485-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="11485-227">Any</span><span class="sxs-lookup"><span data-stu-id="11485-227">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-228">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-229">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="11485-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="11485-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="11485-231">Any</span><span class="sxs-lookup"><span data-stu-id="11485-231">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-232">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-233">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="11485-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="11485-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="11485-235">Any</span><span class="sxs-lookup"><span data-stu-id="11485-235">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-236">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11485-237">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="11485-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="11485-238">Firewallzusammenfassung für Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="11485-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11485-239">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="11485-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11485-240">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-240">Source IP address</span></span></th>
<th><span data-ttu-id="11485-241">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-241">Destination IP address</span></span></th>
<th><span data-ttu-id="11485-242">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11485-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11485-243">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-244">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="11485-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="11485-245">Any</span><span class="sxs-lookup"><span data-stu-id="11485-245">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-246">Für Verbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="11485-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="11485-247">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="11485-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11485-248">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="11485-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11485-249">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-249">Source IP address</span></span></th>
<th><span data-ttu-id="11485-250">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="11485-250">Destination IP address</span></span></th>
<th><span data-ttu-id="11485-251">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11485-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11485-252">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-253">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="11485-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="11485-254">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-255">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="11485-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-256">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="11485-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="11485-257">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-258">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="11485-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="11485-259">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="11485-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-260">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11485-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11485-261">Clients</span><span class="sxs-lookup"><span data-stu-id="11485-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="11485-262">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-263">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="11485-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-264">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="11485-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="11485-265">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-266">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="11485-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="11485-267">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="11485-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-268">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11485-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11485-269">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-270">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="11485-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="11485-271">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="11485-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-272">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="11485-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="11485-273">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="11485-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="11485-274">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="11485-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="11485-275">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="11485-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="11485-276">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="11485-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11485-277">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="11485-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11485-278">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="11485-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="11485-279">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="11485-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="11485-280">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="11485-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11485-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11485-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11485-282">Any</span><span class="sxs-lookup"><span data-stu-id="11485-282">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-283">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="11485-284">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="11485-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="11485-285">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="11485-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11485-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="11485-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="11485-287">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11485-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="11485-288">Any</span><span class="sxs-lookup"><span data-stu-id="11485-288">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-289">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="11485-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="11485-290">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="11485-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11485-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="11485-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="11485-292">Any</span><span class="sxs-lookup"><span data-stu-id="11485-292">Any</span></span></p></td>
<td><p><span data-ttu-id="11485-293">Jede interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="11485-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="11485-294">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zur Edgeserver internen IP-Adresse oder der internen IP-Adresse jedes Edgepool-Mitglieds</span><span class="sxs-lookup"><span data-stu-id="11485-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

