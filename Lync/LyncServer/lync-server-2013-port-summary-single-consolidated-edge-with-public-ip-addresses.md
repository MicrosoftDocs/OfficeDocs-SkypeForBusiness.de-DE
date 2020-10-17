---
title: Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
description: Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen.
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
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566401"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="29cd6-103">Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29cd6-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="29cd6-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="29cd6-105">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="29cd6-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="29cd6-106">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="29cd6-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="29cd6-107">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="29cd6-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="29cd6-108">Planungsinformationen für den Reverseproxy und den Partnerverbund finden Sie in [Szenarien für Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) und [Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="29cd6-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="29cd6-109">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="29cd6-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="29cd6-110">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="29cd6-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="29cd6-111">**Unternehmens Umkreisnetzwerk für einzelnen konsolidierten Edgeserver mit öffentlicher IP-Adressierung**</span><span class="sxs-lookup"><span data-stu-id="29cd6-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="29cd6-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="29cd6-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="29cd6-113">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="29cd6-113">Port and Protocol Details</span></span>

<span data-ttu-id="29cd6-114">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="29cd6-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="29cd6-p103">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt). Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="29cd6-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="29cd6-117">Firewallzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen: Externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29cd6-118">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="29cd6-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="29cd6-119">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-119">Source IP address</span></span></th>
<th><span data-ttu-id="29cd6-120">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-120">Destination IP address</span></span></th>
<th><span data-ttu-id="29cd6-121">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="29cd6-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="29cd6-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="29cd6-123">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-123">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-124">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="29cd6-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-125">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="29cd6-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-126">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="29cd6-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="29cd6-127">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-128">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-128">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-129">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="29cd6-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-130">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="29cd6-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="29cd6-131">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-132">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-133">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="29cd6-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-134">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="29cd6-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="29cd6-135">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-136">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-136">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-137">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="29cd6-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-138">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-139">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-140">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-141">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="29cd6-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-142">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-143">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-143">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-144">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-145">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="29cd6-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-146">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-147">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-148">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-148">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-149">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="29cd6-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-150">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-151">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-151">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-152">Edgeserver Webkonferenz-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-153">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="29cd6-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-154">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="29cd6-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="29cd6-155">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-156">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-156">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-157">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-158">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="29cd6-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="29cd6-159">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-160">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-160">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-161">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="29cd6-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-162">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="29cd6-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="29cd6-163">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-163">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-164">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-165">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-166">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="29cd6-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="29cd6-167">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-167">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-168">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-169">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="29cd6-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-170">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="29cd6-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="29cd6-171">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-172">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-172">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-173">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="29cd6-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="29cd6-174">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29cd6-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-175">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="29cd6-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="29cd6-176">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-176">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-177">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-178">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="29cd6-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-179">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-180">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-180">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-181">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-182">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-183">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-184">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-185">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-185">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-186">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="29cd6-187">Firewallzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen: Interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29cd6-188">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="29cd6-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="29cd6-189">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-189">Source IP address</span></span></th>
<th><span data-ttu-id="29cd6-190">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-190">Destination IP address</span></span></th>
<th><span data-ttu-id="29cd6-191">Kommentare</span><span class="sxs-lookup"><span data-stu-id="29cd6-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="29cd6-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="29cd6-193">Any (kann als Standard Edition-Server IP, Standard Edition-Server IP-Adresse oder Pool-IP-Adresse mit dem XMPP-Gatewaydienst definiert werden)</span><span class="sxs-lookup"><span data-stu-id="29cd6-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-194">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-195">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="29cd6-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-197">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="29cd6-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-198">Edgeserver IP oder Pool, der die interne Schnittstelle aufhält</span><span class="sxs-lookup"><span data-stu-id="29cd6-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-199">Ausgehender SIP-Datenverkehr (von Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) zu Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-201">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-202">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="29cd6-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-203">Eingehender SIP-Datenverkehr (an Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="29cd6-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="29cd6-205">Any (kann als Front-End-Server IP-Adresse oder jede Front-End-Server IP-Adresse in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="29cd6-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-206">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-207">Webkonferenz Datenverkehr von Front-End-Server oder jeder Front-End-Server in einem Pool an Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="29cd6-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="29cd6-209">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="29cd6-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-210">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-211">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="29cd6-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-212">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="29cd6-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="29cd6-213">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-213">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-214">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-215">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="29cd6-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-216">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-217">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-217">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-218">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-219">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="29cd6-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="29cd6-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-221">Any (kann als Front-End-Server-IP-Adresse oder als Pool mit dem zentralen Verwaltungsspeicher definiert werden)</span><span class="sxs-lookup"><span data-stu-id="29cd6-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="29cd6-222">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-223">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="29cd6-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="29cd6-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="29cd6-225">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-225">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-226">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-227">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="29cd6-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="29cd6-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="29cd6-229">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-229">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-230">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-231">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="29cd6-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="29cd6-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="29cd6-233">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-233">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-234">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="29cd6-235">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="29cd6-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="29cd6-236">Firewallzusammenfassung für Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="29cd6-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29cd6-237">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="29cd6-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="29cd6-238">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-238">Source IP address</span></span></th>
<th><span data-ttu-id="29cd6-239">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-239">Destination IP address</span></span></th>
<th><span data-ttu-id="29cd6-240">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="29cd6-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-241">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-242">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="29cd6-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-243">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-243">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-244">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="29cd6-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="29cd6-245">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="29cd6-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29cd6-246">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="29cd6-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="29cd6-247">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-247">Source IP address</span></span></th>
<th><span data-ttu-id="29cd6-248">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="29cd6-248">Destination IP address</span></span></th>
<th><span data-ttu-id="29cd6-249">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="29cd6-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-250">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-251">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="29cd6-252">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="29cd6-253">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="29cd6-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-254">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="29cd6-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="29cd6-255">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="29cd6-256">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="29cd6-257">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="29cd6-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-258">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="29cd6-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="29cd6-259">Clients</span><span class="sxs-lookup"><span data-stu-id="29cd6-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="29cd6-260">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="29cd6-261">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="29cd6-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-262">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="29cd6-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="29cd6-263">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="29cd6-264">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="29cd6-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="29cd6-265">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="29cd6-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-266">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="29cd6-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="29cd6-267">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="29cd6-268">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="29cd6-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="29cd6-269">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="29cd6-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-270">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="29cd6-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="29cd6-271">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="29cd6-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="29cd6-272">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="29cd6-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="29cd6-273">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="29cd6-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="29cd6-274">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="29cd6-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29cd6-275">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="29cd6-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="29cd6-276">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="29cd6-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="29cd6-277">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="29cd6-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="29cd6-278">Kommentare</span><span class="sxs-lookup"><span data-stu-id="29cd6-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="29cd6-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="29cd6-280">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-280">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-281">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-282">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="29cd6-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="29cd6-283">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="29cd6-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29cd6-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="29cd6-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="29cd6-285">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29cd6-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="29cd6-286">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-286">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-287">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="29cd6-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="29cd6-288">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="29cd6-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29cd6-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="29cd6-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="29cd6-290">Beliebig</span><span class="sxs-lookup"><span data-stu-id="29cd6-290">Any</span></span></p></td>
<td><p><span data-ttu-id="29cd6-291">Jede interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="29cd6-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="29cd6-292">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zur Edgeserver internen IP-Adresse oder der internen IP-Adresse jedes Edgepool-Mitglieds</span><span class="sxs-lookup"><span data-stu-id="29cd6-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

