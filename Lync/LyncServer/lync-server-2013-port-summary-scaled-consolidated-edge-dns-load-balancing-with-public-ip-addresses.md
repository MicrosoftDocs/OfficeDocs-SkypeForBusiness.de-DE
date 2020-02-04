---
title: 'Lync Server 2013: Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
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
ms.openlocfilehash: f67a12b05d8724d31f8ef83bfa4aa704b41cee13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="d8c79-102">Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8c79-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c79-103">_**Letztes Änderungsdatum des Themas:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="d8c79-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="d8c79-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013-Edgeserver-Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d8c79-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="d8c79-105">Die bemerkenswerteste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="d8c79-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="d8c79-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edge-Server oder Edge-Pool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="d8c79-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="d8c79-107">Neben IPv4 unterstützt der Edgeserver nun IPv6.</span><span class="sxs-lookup"><span data-stu-id="d8c79-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="d8c79-108">Aus Gründen der Übersichtlichkeit wird in den Szenarien nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8c79-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="d8c79-109">**Unternehmens Umkreisnetzwerk für skalierten konsolidierten Edge, DNS-Lastenausgleich mit öffentlichen IP-Adressen**</span><span class="sxs-lookup"><span data-stu-id="d8c79-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="d8c79-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="d8c79-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="d8c79-111">Port- und Protokolldetails</span><span class="sxs-lookup"><span data-stu-id="d8c79-111">Port and Protocol Details</span></span>

<span data-ttu-id="d8c79-112">Es wird empfohlen, nur die Ports zu öffnen, die erforderlich sind, um die Funktionalität zu unterstützen, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d8c79-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="d8c79-113">Damit der Remotezugriff für jeden Edgedienst funktionieren kann, ist es zwingend erforderlich, dass der SIP-Datenverkehr bidirektional wie in der Abbildung des eingehenden/ausgehenden Edge-Traffics durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="d8c79-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="d8c79-114">Anders ausgedrückt: das SIP-Messaging zum und vom Access-Edgedienst ist an Instant Messaging (im), Anwesenheitsinformationen, Webkonferenzen, Audio/Video (A/V) und Föderation beteiligt.</span><span class="sxs-lookup"><span data-stu-id="d8c79-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="d8c79-115">Zusammenfassung der Firewall für den konsolidierten skalierten Edge, DNS-Lastenausgleich mit öffentlichen IP-Adressen: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="d8c79-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c79-116">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="d8c79-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d8c79-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-117">Source IP address</span></span></th>
<th><span data-ttu-id="d8c79-118">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-118">Destination IP address</span></span></th>
<th><span data-ttu-id="d8c79-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8c79-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d8c79-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d8c79-121">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-121">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-122">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Access Edge Service)</span><span class="sxs-lookup"><span data-stu-id="d8c79-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-123">Der XMPP-Proxy Dienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Föderationen</span><span class="sxs-lookup"><span data-stu-id="d8c79-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-124">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="d8c79-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="d8c79-125">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="d8c79-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-126">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-127">Zertifikatsperrung/CRL-Prüfung und-Abruf</span><span class="sxs-lookup"><span data-stu-id="d8c79-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="d8c79-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="d8c79-129">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="d8c79-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-130">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-130">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-131">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="d8c79-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="d8c79-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="d8c79-133">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="d8c79-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-134">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-134">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-135">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="d8c79-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-136">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-137">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-137">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-138">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="d8c79-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-139">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="d8c79-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-140">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-141">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-141">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-142">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="d8c79-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-143">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="d8c79-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-144">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-145">Öffentliche IP-Adresse des Edge-Server-Zugriffs-Edge-Diensts</span><span class="sxs-lookup"><span data-stu-id="d8c79-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-146">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-146">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-147">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="d8c79-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-148">Web Conferencing/PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-149">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-149">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-150">Edge-Server-Webkonferenz-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-151">Web-Konferenzmedien</span><span class="sxs-lookup"><span data-stu-id="d8c79-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d8c79-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d8c79-153">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-154">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-154">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-155">Erforderlich für die Föderation mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 ausführen.</span><span class="sxs-lookup"><span data-stu-id="d8c79-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d8c79-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d8c79-157">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-158">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-158">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-159">Nur für den Verbund mit Partnern erforderlich, auf denen Office Communications Server 2007 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d8c79-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d8c79-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d8c79-161">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-161">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-162">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-163">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="d8c79-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d8c79-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d8c79-165">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-165">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-166">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-167">Nur für den Verbund mit Partnern erforderlich, die Office Communications Server 2007 ausführen</span><span class="sxs-lookup"><span data-stu-id="d8c79-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-168">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d8c79-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d8c79-169">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-170">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-170">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-171">3478 Outbound wird verwendet, um die Version von Edgeserver zu ermitteln, mit der lync Server kommuniziert, sowie für Mediendatenverkehr vom Edge-Server-zu-Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="d8c79-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="d8c79-172">Erforderlich für den Verbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d8c79-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-173">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d8c79-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d8c79-174">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-174">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-175">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-176">Betäubung/Turn Verhandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d8c79-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-177">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-178">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-178">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-179">Edge-Server-A/V-Edgedienst, öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-180">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-181">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-182">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-183">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-183">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-184">Betäubung/Turn Verhandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="d8c79-185">Zusammenfassung der Firewall für den konsolidierten skalierten Edge, DNS-Lastenausgleich mit öffentlichen IP-Adressen: interne Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="d8c79-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c79-186">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="d8c79-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d8c79-187">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-187">Source IP address</span></span></th>
<th><span data-ttu-id="d8c79-188">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-188">Destination IP address</span></span></th>
<th><span data-ttu-id="d8c79-189">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d8c79-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d8c79-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d8c79-191">Any (kann als Front-End-Server Adresse oder IP-Adresse des Front-End-Pools definiert werden, auf der der XMPP-Gatewayserver ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="d8c79-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-192">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-193">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="d8c79-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-195">Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="d8c79-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-196">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-197">Ausgehender SIP-Datenverkehr (von Director, Director-Pool-IP-Adresse, Front-End-Server oder IP-Adresse des Front-End-Pools) zu einer internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-199">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-200">Any (kann als Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools definiert werden)</span><span class="sxs-lookup"><span data-stu-id="d8c79-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-201">Eingehende SIP-Datenverkehr (an Director, IP-Adresse des Director-Pools, Front-End-Server oder IP-Adresse des Front-End-Pools) aus der internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="d8c79-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="d8c79-203">Any (kann als Front-End-Server-IP-Adresse oder jede IP-Adresse eines Front-End-Servers in einem Front-End-Pool definiert werden)</span><span class="sxs-lookup"><span data-stu-id="d8c79-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-204">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-205">Webkonferenzen-Datenverkehr vom Front-End-Server oder jedem Front-End-Server, falls in einem Pool, zu einer internen Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="d8c79-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="d8c79-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="d8c79-207">Any (kann als Front-End-Server-IP-Adresse oder IP-Adresse des Front-End-Pools oder einer überlebensfähigen Branch-Appliance oder eines Überlebenden Branch-Servers mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="d8c79-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-208">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-209">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) vom Front-End-Server oder der IP-Adresse des Front-End-Pools oder von einer Überlebenden Branch-Appliance oder einem Überlebenden Branch-Server mit diesem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="d8c79-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-210">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d8c79-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d8c79-211">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-211">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-212">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-213">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="d8c79-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-214">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-215">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-215">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-216">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-217">Fall Back Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survival-Branch-Appliance oder einem Überlebenden Branch-Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8c79-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="d8c79-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-219">Any (kann als die IP-Adresse des Front-End-Servers oder-Pools definiert werden, der den zentralen Verwaltungsspeicher enthält)</span><span class="sxs-lookup"><span data-stu-id="d8c79-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="d8c79-220">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-221">Replikation von Änderungen vom zentralen Verwaltungsspeicher auf den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="d8c79-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d8c79-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d8c79-223">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-223">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-224">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-225">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="d8c79-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d8c79-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d8c79-227">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-227">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-228">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-229">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="d8c79-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d8c79-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d8c79-231">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-231">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-232">Interne Edge-Server-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8c79-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8c79-233">Zentralisierter Protokollierungsdienst Controller mit lync Server-Verwaltungsshell und zentralen Protokolldienst-Cmdlets, Befehlszeilen-ClsController (ClsController. exe) oder Agent (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="d8c79-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="d8c79-234">Zusammenfassung der Firewall für den Verbund</span><span class="sxs-lookup"><span data-stu-id="d8c79-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c79-235">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="d8c79-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d8c79-236">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-236">Source IP address</span></span></th>
<th><span data-ttu-id="d8c79-237">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-237">Destination IP address</span></span></th>
<th><span data-ttu-id="d8c79-238">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8c79-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-239">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-240">Access Edge Service (öffentliche IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="d8c79-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-241">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-241">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-242">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="d8c79-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d8c79-243">Zusammenfassung der Firewall – öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="d8c79-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c79-244">Role/Protocol/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="d8c79-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d8c79-245">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-245">Source IP address</span></span></th>
<th><span data-ttu-id="d8c79-246">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d8c79-246">Destination IP address</span></span></th>
<th><span data-ttu-id="d8c79-247">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8c79-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-248">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-249">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="d8c79-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d8c79-250">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-251">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="d8c79-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-252">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d8c79-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d8c79-253">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-254">Verbindungspartner für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="d8c79-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d8c79-255">Für Verbund-und öffentliche Chat Verbindungen mit SIP</span><span class="sxs-lookup"><span data-stu-id="d8c79-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-256">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d8c79-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d8c79-257">Clients</span><span class="sxs-lookup"><span data-stu-id="d8c79-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="d8c79-258">Edge-Server-Zugriffs-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-259">Client-zu-Server-SIP-Datenverkehr für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="d8c79-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="d8c79-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d8c79-261">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-262">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="d8c79-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d8c79-263">Wird für A/V-Sitzungen mit Windows Live Messenger verwendet, wenn die Konnektivität für öffentliche Chats konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d8c79-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-264">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d8c79-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d8c79-265">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-266">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="d8c79-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d8c79-267">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d8c79-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-268">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d8c79-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d8c79-269">Live Messenger-Clients</span><span class="sxs-lookup"><span data-stu-id="d8c79-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d8c79-270">Edge-Server A/V-Edgedienst</span><span class="sxs-lookup"><span data-stu-id="d8c79-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d8c79-271">Erforderlich für öffentliche Chat Verbindungen mit Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d8c79-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d8c79-272">Zusammenfassung der Firewall für erweiterbares Messaging und Anwesenheits Protokoll</span><span class="sxs-lookup"><span data-stu-id="d8c79-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8c79-273">Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="d8c79-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d8c79-274">Quelle (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="d8c79-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="d8c79-275">Ziel (IP-Adresse)</span><span class="sxs-lookup"><span data-stu-id="d8c79-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d8c79-276">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d8c79-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d8c79-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d8c79-278">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-278">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-279">IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</span><span class="sxs-lookup"><span data-stu-id="d8c79-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-280">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="d8c79-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d8c79-281">Ermöglicht die Kommunikation mit dem Edge-Server-XMPP-Proxy von Federated XMPP-Partnern</span><span class="sxs-lookup"><span data-stu-id="d8c79-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8c79-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d8c79-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d8c79-283">IP-Adresse des Edge-Server-Access-Edge-Service-Interfaces</span><span class="sxs-lookup"><span data-stu-id="d8c79-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d8c79-284">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-284">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-285">Standard mäßiger Server-zu-Server-Kommunikationsanschluss für XMPP.</span><span class="sxs-lookup"><span data-stu-id="d8c79-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d8c79-286">Ermöglicht die Kommunikation vom Edge Server XMPP-Proxy an Federated XMPP-Partner</span><span class="sxs-lookup"><span data-stu-id="d8c79-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8c79-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d8c79-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d8c79-288">Beliebig</span><span class="sxs-lookup"><span data-stu-id="d8c79-288">Any</span></span></p></td>
<td><p><span data-ttu-id="d8c79-289">Jede interne Edge-Server-Schnittstellen-IP</span><span class="sxs-lookup"><span data-stu-id="d8c79-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="d8c79-290">Interner XMPP-Datenverkehr vom XMPP-Gateway auf dem Front-End-Server oder Front-End-Pool zur internen IP-Adresse des Edge-Servers oder zur internen IP-Adresse jedes Edge-Pools</span><span class="sxs-lookup"><span data-stu-id="d8c79-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

