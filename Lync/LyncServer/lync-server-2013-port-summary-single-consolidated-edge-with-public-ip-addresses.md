---
title: Portzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen
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
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="57092-102">Portzusammenfassung für einen einzelnen konsolidierten Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57092-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57092-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="57092-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="57092-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013-Edgeserver-Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="57092-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="57092-105">Die bemerkenswerteste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="57092-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="57092-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edge-Server oder Edge-Pool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="57092-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="57092-107">Planungsinformationen für den Reverseproxy und die Föderation finden Sie in [Szenarien für den Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) und [Planen für SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) -Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="57092-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="57092-108">Neben IPv4 unterstützt der Edgeserver nun IPv6.</span><span class="sxs-lookup"><span data-stu-id="57092-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="57092-109">Aus Gründen der Übersichtlichkeit wird in den Szenarien nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="57092-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="57092-110">**Unternehmens Umkreisnetzwerk für einzelnen konsolidierten Edge mit öffentlicher IP-Adressierung**</span><span class="sxs-lookup"><span data-stu-id="57092-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="57092-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="57092-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="57092-112">Port- und Protokolldetails</span><span class="sxs-lookup"><span data-stu-id="57092-112">Port and Protocol Details</span></span>

<span data-ttu-id="57092-113">Wir empfehlen, nur die Ports zu öffnen, die erforderlich sind, um die Funktionalität zu unterstützen, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="57092-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="57092-114">Damit der Remotezugriff für jeden Edgedienst funktionieren kann, ist es zwingend erforderlich, dass der SIP-Datenverkehr bidirektional erfolgt, wie in der Abbildung für eingehende/ausgehende Edge-Datenverkehr dargestellt.</span><span class="sxs-lookup"><span data-stu-id="57092-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="57092-115">Anders ausgedrückt: das SIP-Messaging zum und vom Access-Edgedienst ist an Instant Messaging (im), Anwesenheitsinformationen, Webkonferenzen, Audio/Video (A/V) und Föderation beteiligt.</span><span class="sxs-lookup"><span data-stu-id="57092-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="57092-116">Zusammenfassung der Firewall für einzelne konsolidierte Edges mit öffentlichen IP-Adressen: externe Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57092-117">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="57092-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="57092-118">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-118">Source IP address</span></span></th>
<th><span data-ttu-id="57092-119">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-119">Destination IP address</span></span></th>
<th><span data-ttu-id="57092-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57092-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57092-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="57092-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="57092-122">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-122">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-123">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</span><span class="sxs-lookup"><span data-stu-id="57092-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="57092-124">Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen</span><span class="sxs-lookup"><span data-stu-id="57092-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-125">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="57092-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="57092-126">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-127">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-128">Zertifikatsperrung/CRL-Prüfung und-Abruf</span><span class="sxs-lookup"><span data-stu-id="57092-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="57092-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="57092-130">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-131">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-132">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="57092-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="57092-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="57092-134">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-135">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-135">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-136">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="57092-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-137">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="57092-138">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-138">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-139">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-140">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="57092-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-141">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-142">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-142">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-143">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-144">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="57092-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-145">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-146">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-147">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-147">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-148">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="57092-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-149">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="57092-150">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-150">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-151">Edge-Server-Webkonferenz-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-152">Web-Konferenzmedien</span><span class="sxs-lookup"><span data-stu-id="57092-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="57092-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="57092-154">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="57092-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-155">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-155">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-156">Erforderlich für die Föderation mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 ausführen.</span><span class="sxs-lookup"><span data-stu-id="57092-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="57092-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="57092-158">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-159">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-159">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-160">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="57092-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="57092-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="57092-162">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-162">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-163">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-164">Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57092-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="57092-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="57092-166">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-166">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-167">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-168">Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57092-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-169">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="57092-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="57092-170">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-171">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-171">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-172">3478 Outbound wird verwendet, um die Version von Edgeserver zu ermitteln, mit der lync Server kommuniziert, sowie für Mediendatenverkehr vom Edge-Server-zu-Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="57092-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="57092-173">Erforderlich für den Verbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="57092-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-174">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="57092-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="57092-175">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-175">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-176">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-177">Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="57092-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-178">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="57092-179">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-179">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-180">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-181">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-182">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="57092-183">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-184">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-184">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-185">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="57092-186">Zusammenfassung der Firewall für einzelne konsolidierte Edges mit öffentlichen IP-Adressen: interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57092-187">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="57092-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="57092-188">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-188">Source IP address</span></span></th>
<th><span data-ttu-id="57092-189">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-189">Destination IP address</span></span></th>
<th><span data-ttu-id="57092-190">Kommentare</span><span class="sxs-lookup"><span data-stu-id="57092-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57092-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="57092-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="57092-192">Any (kann als Standard Edition Server IP, Standard Edition Server-IP-Adresse oder Pool-IP-Adresse mit dem XMPP-Gatewayserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="57092-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="57092-193">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-194">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="57092-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-196">Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="57092-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="57092-197">Edge-Server-IP oder Pool, der die interne Schnittstelle enthält</span><span class="sxs-lookup"><span data-stu-id="57092-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-198">Ausgehender SIP-Datenverkehr (von Director, Director-Pool-IP-Adresse, Front-End-Server oder IP-Adresse des Front-End-Pools) zu einer internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-200">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-201">Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="57092-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="57092-202">Eingehende SIP-Datenverkehr (an Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools) aus der internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="57092-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="57092-204">Any (kann als Front-End-Server-IP-Adresse oder jede IP-Adresse eines Front-End-Servers in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="57092-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="57092-205">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-206">Webkonferenzen-Datenverkehr vom Front-End-Server oder jedem Front-End-Server, falls in einem Pool, zu einer internen Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="57092-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="57092-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="57092-208">Any (kann als Front-End-Server-IP-Adresse oder IP-Adresse des Front-End-Pools oder einer überlebensfähigen Branch-Appliance oder eines Überlebenden Branch-Servers mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="57092-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="57092-209">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-210">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) vom Front-End-Server oder der IP-Adresse des Front-End-Pools oder von einer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mit diesem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="57092-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-211">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="57092-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="57092-212">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-212">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-213">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-214">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="57092-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-215">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="57092-216">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-216">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-217">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-218">Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survival-Branch-Appliance oder einem Überlebenden Branch-Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="57092-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="57092-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="57092-220">Any (kann als die IP-Adresse des Front-End-Servers oder-Pools definiert werden, der den zentralen Verwaltungsspeicher enthält)</span><span class="sxs-lookup"><span data-stu-id="57092-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="57092-221">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-222">Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="57092-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="57092-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="57092-224">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-224">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-225">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-226">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="57092-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="57092-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="57092-228">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-228">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-229">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-230">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="57092-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="57092-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="57092-232">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-232">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-233">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57092-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="57092-234">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="57092-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="57092-235">Zusammenfassung der Firewall für den Verbund</span><span class="sxs-lookup"><span data-stu-id="57092-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57092-236">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="57092-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="57092-237">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-237">Source IP address</span></span></th>
<th><span data-ttu-id="57092-238">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-238">Destination IP address</span></span></th>
<th><span data-ttu-id="57092-239">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57092-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57092-240">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-241">Access Edge Service (öffentliche IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="57092-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-242">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-242">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-243">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="57092-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="57092-244">Zusammenfassung der Firewall – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="57092-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57092-245">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="57092-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="57092-246">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-246">Source IP address</span></span></th>
<th><span data-ttu-id="57092-247">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="57092-247">Destination IP address</span></span></th>
<th><span data-ttu-id="57092-248">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57092-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57092-249">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-250">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="57092-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="57092-251">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="57092-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="57092-252">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="57092-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-253">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="57092-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="57092-254">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="57092-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="57092-255">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="57092-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="57092-256">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="57092-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-257">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="57092-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="57092-258">Clients</span><span class="sxs-lookup"><span data-stu-id="57092-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="57092-259">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="57092-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="57092-260">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="57092-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="57092-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="57092-262">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="57092-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="57092-263">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="57092-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="57092-264">Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn die Konnektivität für öffentliche Chats konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="57092-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-265">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="57092-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="57092-266">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="57092-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="57092-267">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="57092-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="57092-268">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="57092-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-269">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="57092-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="57092-270">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="57092-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="57092-271">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="57092-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="57092-272">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="57092-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="57092-273">Zusammenfassung der Firewall für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="57092-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57092-274">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="57092-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="57092-275">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="57092-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="57092-276">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="57092-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="57092-277">Kommentare</span><span class="sxs-lookup"><span data-stu-id="57092-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57092-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="57092-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="57092-279">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-279">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-280">IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</span><span class="sxs-lookup"><span data-stu-id="57092-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-281">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="57092-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="57092-282">Ermöglicht die Kommunikation mit dem Edge-Server-XMPP-Proxy von Federated XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="57092-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57092-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="57092-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="57092-284">IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</span><span class="sxs-lookup"><span data-stu-id="57092-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="57092-285">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-285">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-286">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="57092-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="57092-287">Ermöglicht die Kommunikation vom Edge Server XMPP-Proxy an Federated XMPP-Partner</span><span class="sxs-lookup"><span data-stu-id="57092-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57092-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="57092-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="57092-289">Beliebig</span><span class="sxs-lookup"><span data-stu-id="57092-289">Any</span></span></p></td>
<td><p><span data-ttu-id="57092-290">Jede interne Edge-Server-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="57092-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="57092-291">Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zur internen IP-Adresse des Edge-Servers oder zur internen IP-Adresse jedes Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="57092-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

