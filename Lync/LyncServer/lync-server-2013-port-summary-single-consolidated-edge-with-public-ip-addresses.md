---
title: Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c307ff7318a426610cf371a3d6f55591a7c6ed0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="08ecf-102">Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08ecf-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08ecf-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="08ecf-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="08ecf-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="08ecf-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="08ecf-105">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="08ecf-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="08ecf-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="08ecf-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="08ecf-107">Planungsinformationen für den Reverseproxy und den Partnerverbund finden Sie in [Szenarien für Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) und [Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="08ecf-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="08ecf-108">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="08ecf-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="08ecf-109">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="08ecf-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="08ecf-110">**Unternehmens Umkreisnetzwerk für einzelnen konsolidierten Edgeserver mit öffentlicher IP-Adressierung**</span><span class="sxs-lookup"><span data-stu-id="08ecf-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="08ecf-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="08ecf-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="08ecf-112">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="08ecf-112">Port and Protocol Details</span></span>

<span data-ttu-id="08ecf-113">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="08ecf-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="08ecf-p103">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt). Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="08ecf-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="08ecf-116">Firewallzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen: Externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ecf-117">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08ecf-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08ecf-118">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-118">Source IP address</span></span></th>
<th><span data-ttu-id="08ecf-119">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-119">Destination IP address</span></span></th>
<th><span data-ttu-id="08ecf-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08ecf-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="08ecf-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="08ecf-122">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-122">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-123">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="08ecf-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-124">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="08ecf-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-125">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="08ecf-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="08ecf-126">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-127">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-127">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-128">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="08ecf-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="08ecf-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="08ecf-130">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-131">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-131">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-132">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="08ecf-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="08ecf-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="08ecf-134">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-135">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-135">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-136">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="08ecf-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-137">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-138">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-138">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-139">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-140">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="08ecf-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-141">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-142">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-142">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-143">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-144">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="08ecf-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-145">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-146">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-147">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-147">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-148">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="08ecf-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-149">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-150">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-150">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-151">Edgeserver Webkonferenz-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-152">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="08ecf-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="08ecf-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08ecf-154">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-155">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-155">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-156">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="08ecf-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="08ecf-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08ecf-158">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-159">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-159">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-160">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="08ecf-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="08ecf-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08ecf-162">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-162">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-163">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-164">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="08ecf-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="08ecf-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08ecf-166">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-166">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-167">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-168">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="08ecf-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-169">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08ecf-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08ecf-170">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-171">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-171">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-172">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="08ecf-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="08ecf-173">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="08ecf-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-174">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08ecf-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08ecf-175">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-175">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-176">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-177">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08ecf-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-178">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-179">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-179">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-180">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-181">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-182">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-183">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-184">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-184">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-185">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="08ecf-186">Firewallzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen: Interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ecf-187">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08ecf-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08ecf-188">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-188">Source IP address</span></span></th>
<th><span data-ttu-id="08ecf-189">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-189">Destination IP address</span></span></th>
<th><span data-ttu-id="08ecf-190">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="08ecf-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="08ecf-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="08ecf-192">Any (kann als Standard Edition-Server IP, Standard Edition-Server IP-Adresse oder Pool-IP-Adresse mit dem XMPP-Gatewaydienst definiert werden)</span><span class="sxs-lookup"><span data-stu-id="08ecf-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-193">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-194">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="08ecf-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-196">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="08ecf-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-197">Edgeserver IP oder Pool, der die interne Schnittstelle aufhält</span><span class="sxs-lookup"><span data-stu-id="08ecf-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-198">Ausgehender SIP-Datenverkehr (von Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) zu Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-200">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-201">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="08ecf-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-202">Eingehender SIP-Datenverkehr (an Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="08ecf-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="08ecf-204">Any (kann als Front-End-Server IP-Adresse oder jede Front-End-Server IP-Adresse in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="08ecf-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-205">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-206">Webkonferenz Datenverkehr von Front-End-Server oder jeder Front-End-Server in einem Pool an Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="08ecf-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="08ecf-208">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="08ecf-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-209">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-210">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="08ecf-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-211">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08ecf-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08ecf-212">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-212">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-213">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-214">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="08ecf-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-215">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-216">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-216">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-217">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-218">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="08ecf-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="08ecf-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-220">Any (kann als Front-End-Server-IP-Adresse oder als Pool mit dem zentralen Verwaltungsspeicher definiert werden)</span><span class="sxs-lookup"><span data-stu-id="08ecf-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="08ecf-221">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-222">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="08ecf-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="08ecf-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="08ecf-224">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-224">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-225">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-226">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="08ecf-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="08ecf-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="08ecf-228">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-228">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-229">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-230">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="08ecf-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="08ecf-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="08ecf-232">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-232">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-233">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="08ecf-234">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="08ecf-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="08ecf-235">Firewallzusammenfassung für Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="08ecf-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ecf-236">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08ecf-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08ecf-237">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-237">Source IP address</span></span></th>
<th><span data-ttu-id="08ecf-238">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-238">Destination IP address</span></span></th>
<th><span data-ttu-id="08ecf-239">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08ecf-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-240">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-241">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="08ecf-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-242">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-242">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-243">Für Verbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="08ecf-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="08ecf-244">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="08ecf-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ecf-245">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08ecf-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08ecf-246">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-246">Source IP address</span></span></th>
<th><span data-ttu-id="08ecf-247">Ziel­-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="08ecf-247">Destination IP address</span></span></th>
<th><span data-ttu-id="08ecf-248">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08ecf-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-249">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-250">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="08ecf-251">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="08ecf-252">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Instant Messaging-Diensten über SIP</span><span class="sxs-lookup"><span data-stu-id="08ecf-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-253">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="08ecf-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="08ecf-254">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="08ecf-255">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="08ecf-256">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="08ecf-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-257">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="08ecf-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="08ecf-258">Clients</span><span class="sxs-lookup"><span data-stu-id="08ecf-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="08ecf-259">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="08ecf-260">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="08ecf-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="08ecf-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="08ecf-262">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08ecf-263">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="08ecf-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="08ecf-264">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="08ecf-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-265">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08ecf-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08ecf-266">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08ecf-267">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="08ecf-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="08ecf-268">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08ecf-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-269">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="08ecf-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="08ecf-270">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="08ecf-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="08ecf-271">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="08ecf-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="08ecf-272">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="08ecf-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="08ecf-273">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="08ecf-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ecf-274">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="08ecf-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="08ecf-275">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="08ecf-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="08ecf-276">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="08ecf-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="08ecf-277">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="08ecf-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="08ecf-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="08ecf-279">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-279">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-280">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-281">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="08ecf-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="08ecf-282">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="08ecf-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ecf-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="08ecf-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="08ecf-284">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08ecf-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="08ecf-285">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-285">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-286">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="08ecf-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="08ecf-287">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="08ecf-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ecf-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="08ecf-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="08ecf-289">Any</span><span class="sxs-lookup"><span data-stu-id="08ecf-289">Any</span></span></p></td>
<td><p><span data-ttu-id="08ecf-290">Jede interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="08ecf-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="08ecf-291">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zur Edgeserver internen IP-Adresse oder der internen IP-Adresse jedes Edgepool-Mitglieds</span><span class="sxs-lookup"><span data-stu-id="08ecf-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

