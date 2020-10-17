---
title: 'Lync Server 2013: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT'
description: 'Lync Server 2013: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT.'
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
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563941"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="c12d6-103">Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c12d6-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c12d6-104">_**Letztes Änderungsstand des Themas:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="c12d6-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="c12d6-105">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c12d6-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="c12d6-106">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="c12d6-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="c12d6-107">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="c12d6-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="c12d6-108">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="c12d6-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="c12d6-109">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="c12d6-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="c12d6-110">**Unternehmens Umkreisnetzwerk für einen skalierten konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT**</span><span class="sxs-lookup"><span data-stu-id="c12d6-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="c12d6-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="c12d6-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="c12d6-112">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="c12d6-112">Port and Protocol Details</span></span>

<span data-ttu-id="c12d6-113">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c12d6-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="c12d6-114">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt).</span><span class="sxs-lookup"><span data-stu-id="c12d6-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="c12d6-115">Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c12d6-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="c12d6-116">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="c12d6-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c12d6-117">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c12d6-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c12d6-118">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-118">Source IP address</span></span></th>
<th><span data-ttu-id="c12d6-119">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-119">Destination IP address</span></span></th>
<th><span data-ttu-id="c12d6-120">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c12d6-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c12d6-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c12d6-122">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-122">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-123">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="c12d6-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-124">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="c12d6-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c12d6-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c12d6-126">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="c12d6-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-127">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-128">XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-verbünden</span><span class="sxs-lookup"><span data-stu-id="c12d6-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-129">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c12d6-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c12d6-130">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-132">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="c12d6-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-133">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="c12d6-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="c12d6-134">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-135">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-135">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-136">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="c12d6-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-137">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="c12d6-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="c12d6-138">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-139">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-140">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="c12d6-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-141">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-142">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-142">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-143">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-144">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="c12d6-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-145">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-146">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-146">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-147">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-148">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c12d6-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-149">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-150">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-151">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-151">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-152">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c12d6-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-153">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-154">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-155">Edgeserver Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-156">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="c12d6-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-157">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c12d6-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c12d6-158">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-159">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-159">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-160">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="c12d6-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-161">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c12d6-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c12d6-162">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-163">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-163">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-164">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="c12d6-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-165">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c12d6-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c12d6-166">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-166">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-167">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-168">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="c12d6-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-169">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c12d6-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c12d6-170">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-170">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-171">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-172">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="c12d6-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-173">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c12d6-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c12d6-174">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-175">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-175">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-176">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="c12d6-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="c12d6-177">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c12d6-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-178">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c12d6-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c12d6-179">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-179">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-180">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-181">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c12d6-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-182">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-183">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-183">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-184">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-185">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-186">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-187">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-188">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-188">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-189">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="c12d6-190">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT: interne Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="c12d6-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c12d6-191">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c12d6-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c12d6-192">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-192">Source IP address</span></span></th>
<th><span data-ttu-id="c12d6-193">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-193">Destination IP address</span></span></th>
<th><span data-ttu-id="c12d6-194">Kommentare</span><span class="sxs-lookup"><span data-stu-id="c12d6-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c12d6-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c12d6-196">Any (kann als Front-End-Server Adresse definiert werden oder Front-End-Pool IP-Adresse, die den XMPP-Gatewaydienst ausführt)</span><span class="sxs-lookup"><span data-stu-id="c12d6-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-197">IP-Adresse Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c12d6-198">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="c12d6-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-200">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c12d6-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-201">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-202">Ausgehender SIP-Datenverkehr (von Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) zu Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-204">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-205">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c12d6-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-206">Eingehender SIP-Datenverkehr (an Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="c12d6-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="c12d6-208">Any (kann als Front-End-Server IP-Adresse oder jede Front-End-Server IP-Adresse in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c12d6-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-209">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-210">Webkonferenz Datenverkehr von Front-End-Server oder jeder Front-End-Server in einem Pool an Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="c12d6-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="c12d6-212">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c12d6-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-213">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-214">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="c12d6-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-215">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c12d6-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c12d6-216">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-216">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-217">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-218">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="c12d6-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-219">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-220">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-220">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-221">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-222">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="c12d6-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c12d6-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-224">Any (kann als Front-End-Server-IP-Adresse oder als Pool mit dem zentralen Verwaltungsspeicher definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c12d6-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="c12d6-225">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-226">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="c12d6-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c12d6-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c12d6-228">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-228">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-229">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-230">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="c12d6-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c12d6-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c12d6-232">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-232">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-233">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-234">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="c12d6-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c12d6-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c12d6-236">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-236">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-237">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c12d6-238">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="c12d6-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="c12d6-239">Firewallzusammenfassung für Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="c12d6-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c12d6-240">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c12d6-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c12d6-241">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-241">Source IP address</span></span></th>
<th><span data-ttu-id="c12d6-242">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-242">Destination IP address</span></span></th>
<th><span data-ttu-id="c12d6-243">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c12d6-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-244">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-245">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="c12d6-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c12d6-246">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-246">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-247">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c12d6-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c12d6-248">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="c12d6-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c12d6-249">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c12d6-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c12d6-250">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-250">Source IP address</span></span></th>
<th><span data-ttu-id="c12d6-251">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c12d6-251">Destination IP address</span></span></th>
<th><span data-ttu-id="c12d6-252">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c12d6-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-253">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-254">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c12d6-255">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-256">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c12d6-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-257">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c12d6-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c12d6-258">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-259">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c12d6-260">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c12d6-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-261">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c12d6-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c12d6-262">Clients</span><span class="sxs-lookup"><span data-stu-id="c12d6-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="c12d6-263">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-264">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="c12d6-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-265">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c12d6-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c12d6-266">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-267">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="c12d6-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c12d6-268">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c12d6-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-269">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c12d6-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c12d6-270">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-271">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="c12d6-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c12d6-272">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c12d6-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-273">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c12d6-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c12d6-274">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="c12d6-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c12d6-275">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c12d6-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c12d6-276">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c12d6-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c12d6-277">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="c12d6-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c12d6-278">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c12d6-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c12d6-279">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="c12d6-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="c12d6-280">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="c12d6-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c12d6-281">Kommentare</span><span class="sxs-lookup"><span data-stu-id="c12d6-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c12d6-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c12d6-283">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-283">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-284">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c12d6-285">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="c12d6-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c12d6-286">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="c12d6-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c12d6-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c12d6-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c12d6-288">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c12d6-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c12d6-289">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-289">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-290">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="c12d6-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c12d6-291">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="c12d6-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c12d6-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c12d6-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c12d6-293">Beliebig</span><span class="sxs-lookup"><span data-stu-id="c12d6-293">Any</span></span></p></td>
<td><p><span data-ttu-id="c12d6-294">Jede interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="c12d6-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="c12d6-295">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zur Edgeserver internen IP-Adresse oder der internen IP-Adresse jedes Edgepool-Mitglieds</span><span class="sxs-lookup"><span data-stu-id="c12d6-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

