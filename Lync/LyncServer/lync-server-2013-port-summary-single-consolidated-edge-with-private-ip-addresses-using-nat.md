---
title: Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT
description: Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564561"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="6fd21-103">Port Zusammenfassung für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fd21-103">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd21-104">_**Letztes Änderungsstand des Themas:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="6fd21-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="6fd21-105">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6fd21-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="6fd21-106">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="6fd21-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="6fd21-107">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="6fd21-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="6fd21-108">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="6fd21-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="6fd21-109">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fd21-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="6fd21-110">**Netzwerk Perimeter für eine einzelne konsolidierte Edgeserver mit privater IP-Adressierung mithilfe von NAT**</span><span class="sxs-lookup"><span data-stu-id="6fd21-110">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="6fd21-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="6fd21-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="6fd21-112">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="6fd21-112">Port and Protocol Details</span></span>

<span data-ttu-id="6fd21-113">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="6fd21-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="6fd21-114">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt).</span><span class="sxs-lookup"><span data-stu-id="6fd21-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="6fd21-115">Anders ausgedrückt, ist das SIP-Messaging zum und vom Zugriffs-Edgedienst an Instant Messaging (Sofortnachrichten), Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Verbund beteiligt.</span><span class="sxs-lookup"><span data-stu-id="6fd21-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="6fd21-116">Zusammenfassung der Firewall für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-116">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd21-117">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="6fd21-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6fd21-118">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-118">Source IP address</span></span></th>
<th><span data-ttu-id="6fd21-119">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-119">Destination IP address</span></span></th>
<th><span data-ttu-id="6fd21-120">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="6fd21-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6fd21-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6fd21-122">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-122">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-123">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="6fd21-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-124">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="6fd21-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-125">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="6fd21-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="6fd21-126">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-126">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-127">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-128">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="6fd21-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="6fd21-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="6fd21-130">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-131">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-132">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="6fd21-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="6fd21-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="6fd21-134">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-135">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-135">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-136">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="6fd21-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-137">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-138">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-139">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-139">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-140">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="6fd21-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-141">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-142">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-142">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-143">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-144">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="6fd21-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-145">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-146">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-147">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-147">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-148">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="6fd21-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-149">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-150">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-151">Edgeserver Webkonferenz-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-151">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-152">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="6fd21-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6fd21-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6fd21-154">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-154">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-155">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-155">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-156">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="6fd21-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6fd21-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6fd21-158">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-159">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-159">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-160">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="6fd21-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6fd21-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6fd21-162">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-162">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-163">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-163">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-164">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="6fd21-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6fd21-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6fd21-166">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-166">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-167">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-168">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="6fd21-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-169">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6fd21-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6fd21-170">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-171">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-171">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-172">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6fd21-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="6fd21-173">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6fd21-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-174">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6fd21-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6fd21-175">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-175">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-176">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-176">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-177">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6fd21-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-178">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-179">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-179">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-180">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-181">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-182">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-183">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-184">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-184">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-185">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="6fd21-186">Zusammenfassung der Firewall für einen einzelnen konsolidierten Edgeserver mit privaten IP-Adressen mithilfe von NAT: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-186">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd21-187">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="6fd21-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6fd21-188">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-188">Source IP address</span></span></th>
<th><span data-ttu-id="6fd21-189">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-189">Destination IP address</span></span></th>
<th><span data-ttu-id="6fd21-190">Kommentare</span><span class="sxs-lookup"><span data-stu-id="6fd21-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6fd21-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6fd21-192">Any (kann als Standard Edition-Server IP, Standard Edition-Server IP-Adresse oder Pool-IP-Adresse mit dem XMPP-Gatewaydienst definiert werden)</span><span class="sxs-lookup"><span data-stu-id="6fd21-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-193">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-194">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="6fd21-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-196">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="6fd21-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-197">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-198">Ausgehender SIP-Datenverkehr (von Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) zu Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-200">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-201">Any (kann als Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="6fd21-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-202">Eingehender SIP-Datenverkehr (an Director, Directorpool IP-Adresse, Front-End-Server oder Front-End-Pool IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="6fd21-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="6fd21-204">Any (kann als Front-End-Server IP-Adresse oder jede Front-End-Server IP-Adresse in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="6fd21-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-205">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-206">Webkonferenz Datenverkehr von Front-End-Server oder jeder Front-End-Server in einem Pool an Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="6fd21-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="6fd21-208">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="6fd21-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-209">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-210">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6fd21-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-211">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6fd21-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6fd21-212">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-212">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-213">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-214">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="6fd21-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-215">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-216">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-216">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-217">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-218">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fd21-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="6fd21-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-220">Any (kann als Front-End-Server-IP-Adresse oder als Pool mit dem zentralen Verwaltungsspeicher definiert werden)</span><span class="sxs-lookup"><span data-stu-id="6fd21-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="6fd21-221">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-222">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6fd21-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="6fd21-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="6fd21-224">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-224">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-225">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-226">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="6fd21-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="6fd21-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="6fd21-228">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-228">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-229">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-230">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="6fd21-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="6fd21-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="6fd21-232">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-232">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-233">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6fd21-234">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="6fd21-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="6fd21-235">Firewallzusammenfassung für Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="6fd21-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd21-236">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="6fd21-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6fd21-237">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-237">Source IP address</span></span></th>
<th><span data-ttu-id="6fd21-238">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-238">Destination IP address</span></span></th>
<th><span data-ttu-id="6fd21-239">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="6fd21-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-240">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-241">Öffentliche IP-Adresse des Zugriffs-Edgediensts</span><span class="sxs-lookup"><span data-stu-id="6fd21-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6fd21-242">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-242">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-243">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="6fd21-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="6fd21-244">Firewallzusammenfassung – Öffentlicher Chat</span><span class="sxs-lookup"><span data-stu-id="6fd21-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd21-245">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="6fd21-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6fd21-246">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-246">Source IP address</span></span></th>
<th><span data-ttu-id="6fd21-247">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="6fd21-247">Destination IP address</span></span></th>
<th><span data-ttu-id="6fd21-248">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="6fd21-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-249">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-250">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6fd21-251">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-252">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="6fd21-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-253">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6fd21-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6fd21-254">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-255">Partner für Verbindung mit öffentlichem Chatdienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6fd21-256">Für Partnerverbundkonnektivität und die Verbindung mit öffentlichen Chatdiensten über SIP</span><span class="sxs-lookup"><span data-stu-id="6fd21-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-257">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6fd21-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6fd21-258">Clients</span><span class="sxs-lookup"><span data-stu-id="6fd21-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="6fd21-259">Edgeserver Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-260">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="6fd21-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6fd21-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6fd21-262">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-263">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="6fd21-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6fd21-264">Verwendet für A/V-Sitzungen mit Windows Live Messenger, wenn Verbindung mit öffentlichem Chatdienst konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6fd21-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-265">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6fd21-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6fd21-266">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-267">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="6fd21-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6fd21-268">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6fd21-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-269">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6fd21-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6fd21-270">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="6fd21-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6fd21-271">Edgeserver A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="6fd21-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6fd21-272">Erforderlich für Verbindung mit öffentlichem Chatdienst mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6fd21-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="6fd21-273">Firewallzusammenfassung für XMPP (Extensible Messaging and Presence-Protokoll)</span><span class="sxs-lookup"><span data-stu-id="6fd21-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6fd21-274">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="6fd21-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6fd21-275">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="6fd21-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="6fd21-276">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="6fd21-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="6fd21-277">Kommentare</span><span class="sxs-lookup"><span data-stu-id="6fd21-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6fd21-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6fd21-279">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-279">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-280">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6fd21-281">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="6fd21-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6fd21-282">Ermöglicht die Kommunikation mit dem Edgeserver XMPP-Proxy von Partnerverbund-XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="6fd21-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd21-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6fd21-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6fd21-284">IP-Adresse Edgeserver Zugriffs-Edgedienst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fd21-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6fd21-285">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-285">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-286">Standardmäßiger Server-zu-Server-Kommunikationsport für XMPP.</span><span class="sxs-lookup"><span data-stu-id="6fd21-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6fd21-287">Ermöglicht die Kommunikation vom Edgeserver XMPP-Proxy zu Partner-XMPP-Partnern.</span><span class="sxs-lookup"><span data-stu-id="6fd21-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd21-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6fd21-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6fd21-289">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6fd21-289">Any</span></span></p></td>
<td><p><span data-ttu-id="6fd21-290">Jede interne Edgeserver-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="6fd21-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="6fd21-291">Interner XMPP-Datenverkehr vom XMPP-Gateway im Front-End-Server oder Front-End-Pool zur Edgeserver internen IP-Adresse oder der internen IP-Adresse jedes Edgepool-Mitglieds</span><span class="sxs-lookup"><span data-stu-id="6fd21-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

