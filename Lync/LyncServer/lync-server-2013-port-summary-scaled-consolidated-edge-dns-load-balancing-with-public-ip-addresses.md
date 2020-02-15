---
title: 'Lync Server 2013: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f49a5f14d66e921dc84c42553d3af6a6dddf925
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="c5a5c-102">Port Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5a5c-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5a5c-103">_**Letztes Änderungsstand des Themas:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="c5a5c-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="c5a5c-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="c5a5c-105">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="c5a5c-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="c5a5c-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="c5a5c-107">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="c5a5c-108">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="c5a5c-109">**Unternehmens Umkreisnetzwerk für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen**</span><span class="sxs-lookup"><span data-stu-id="c5a5c-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="c5a5c-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="c5a5c-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="c5a5c-111">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="c5a5c-111">Port and Protocol Details</span></span>

<span data-ttu-id="c5a5c-112">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="c5a5c-113">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt).</span><span class="sxs-lookup"><span data-stu-id="c5a5c-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="c5a5c-114">Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="c5a5c-115">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a5c-116">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c5a5c-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a5c-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-117">Source IP address</span></span></th>
<th><span data-ttu-id="c5a5c-118">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-118">Destination IP address</span></span></th>
<th><span data-ttu-id="c5a5c-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5a5c-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c5a5c-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-121">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-121">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-122">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-123">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="c5a5c-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-124">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c5a5c-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-125">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-126">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-126">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-127">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="c5a5c-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="c5a5c-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-129">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-130">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-130">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-131">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="c5a5c-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-133">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-134">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-134">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-135">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-136">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-137">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-137">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-138">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-139">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="c5a5c-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-140">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-141">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-141">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-142">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-143">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-144">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-145">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-146">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-146">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-147">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-148">Webkonferenz/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-149">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-149">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-150">Edgeserver Webkonferenz-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-151">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="c5a5c-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c5a5c-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-153">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-154">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-154">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-155">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c5a5c-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-157">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-158">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-158">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-159">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c5a5c-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-161">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-161">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-162">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-163">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="c5a5c-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c5a5c-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-165">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-165">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-166">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-167">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="c5a5c-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-168">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a5c-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-169">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-170">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-170">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-171">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="c5a5c-172">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-173">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a5c-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-174">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-174">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-175">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-176">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a5c-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-177">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-178">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-178">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-179">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-180">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-181">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-182">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-183">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-183">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-184">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="c5a5c-185">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen: interne Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a5c-186">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c5a5c-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a5c-187">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-187">Source IP address</span></span></th>
<th><span data-ttu-id="c5a5c-188">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-188">Destination IP address</span></span></th>
<th><span data-ttu-id="c5a5c-189">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c5a5c-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c5a5c-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-191">Any (kann als Front-End-Server Adresse definiert werden oder Front-End-Pool IP-Adresse, die den XMPP-Gatewaydienst ausführt)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-192">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-193">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="c5a5c-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-195">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-196">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-197">Ausgehender SIP-Datenverkehr (von Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) zu Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-199">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-200">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-201">Eingehender SIP-Datenverkehr (an Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="c5a5c-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-203">Any (kann als Front-End-Server IP-Adresse oder jede Front-End-Server IP-Adresse in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-204">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-205">Webkonferenz Datenverkehr von Front-End-Server oder jeder Front-End-Server in einem Pool an Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="c5a5c-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-207">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-208">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-209">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="c5a5c-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-210">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a5c-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-211">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-211">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-212">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-213">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="c5a5c-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-214">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-215">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-215">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-216">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-217">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-219">Any (kann als Front-End-Server-IP-Adresse oder als Pool mit dem zentralen Verwaltungsspeicher definiert werden)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-220">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-221">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="c5a5c-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c5a5c-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-223">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-223">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-224">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-225">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="c5a5c-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c5a5c-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-227">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-227">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-228">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-229">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="c5a5c-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c5a5c-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-231">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-231">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-232">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-233">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="c5a5c-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="c5a5c-234">Firewallzusammenfassung für Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="c5a5c-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a5c-235">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c5a5c-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a5c-236">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-236">Source IP address</span></span></th>
<th><span data-ttu-id="c5a5c-237">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-237">Destination IP address</span></span></th>
<th><span data-ttu-id="c5a5c-238">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5a5c-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-239">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-240">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="c5a5c-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-241">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-241">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-242">Für Verbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c5a5c-243">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="c5a5c-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a5c-244">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c5a5c-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a5c-245">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-245">Source IP address</span></span></th>
<th><span data-ttu-id="c5a5c-246">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c5a5c-246">Destination IP address</span></span></th>
<th><span data-ttu-id="c5a5c-247">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5a5c-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-248">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-249">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-250">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-251">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-252">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c5a5c-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-253">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-254">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-255">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-256">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c5a5c-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-257">Clients</span><span class="sxs-lookup"><span data-stu-id="c5a5c-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-258">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-259">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="c5a5c-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c5a5c-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-261">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-262">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="c5a5c-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-263">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-264">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a5c-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-265">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-266">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="c5a5c-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-267">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5a5c-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-268">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c5a5c-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-269">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="c5a5c-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-270">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="c5a5c-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-271">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c5a5c-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c5a5c-272">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5a5c-273">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c5a5c-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c5a5c-274">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="c5a5c-275">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="c5a5c-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c5a5c-276">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="c5a5c-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c5a5c-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-278">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-278">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-279">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-280">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c5a5c-281">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="c5a5c-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5a5c-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c5a5c-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-283">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5a5c-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-284">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-284">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-285">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c5a5c-286">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="c5a5c-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5a5c-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c5a5c-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-288">Any</span><span class="sxs-lookup"><span data-stu-id="c5a5c-288">Any</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-289">Jede interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="c5a5c-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="c5a5c-290">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zur Edgeserver internen IP-Adresse oder der internen IP-Adresse jedes Edgepool-Mitglieds</span><span class="sxs-lookup"><span data-stu-id="c5a5c-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

