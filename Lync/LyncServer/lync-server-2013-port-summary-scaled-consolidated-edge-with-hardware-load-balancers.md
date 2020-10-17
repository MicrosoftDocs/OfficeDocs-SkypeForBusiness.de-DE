---
title: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardware-Lastenausgleich
description: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleich.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564591"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="e69bd-103">Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e69bd-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e69bd-104">_**Letztes Änderungsstand des Themas:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="e69bd-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="e69bd-105">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e69bd-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e69bd-106">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="e69bd-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e69bd-107">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="e69bd-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="e69bd-108">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="e69bd-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e69bd-109">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="e69bd-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e69bd-110">**Skalierter konsolidierter Edgeserver mit Hardware Lastenausgleich**</span><span class="sxs-lookup"><span data-stu-id="e69bd-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="e69bd-111">![Edgeserver Umkreisnetzwerk-Ports und-Protokolle](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edgeserver Umkreisnetzwerk-Ports und-Protokolle")</span><span class="sxs-lookup"><span data-stu-id="e69bd-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e69bd-112">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="e69bd-112">Port and Protocol Details</span></span>

<span data-ttu-id="e69bd-113">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e69bd-114">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt).</span><span class="sxs-lookup"><span data-stu-id="e69bd-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="e69bd-115">Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e69bd-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="e69bd-116">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Lastenausgleich für Hardware: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="e69bd-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e69bd-117">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e69bd-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e69bd-118">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-118">Source IP address</span></span></th>
<th><span data-ttu-id="e69bd-119">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-119">Destination IP address</span></span></th>
<th><span data-ttu-id="e69bd-120">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e69bd-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-121">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e69bd-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e69bd-122">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-123">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-123">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-124">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="e69bd-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-125">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e69bd-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e69bd-126">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-127">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-128">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="e69bd-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-129">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e69bd-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e69bd-130">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-131">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-132">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="e69bd-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-133">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e69bd-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e69bd-134">Edgeserver A/V-Edgedienst IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-135">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-135">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-136">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-137">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e69bd-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e69bd-138">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-140">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-141">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e69bd-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e69bd-142">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-142">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-143">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-144">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="e69bd-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-145">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e69bd-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e69bd-146">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-146">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-147">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-148">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="e69bd-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-149">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e69bd-150">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-151">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-151">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-152">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="e69bd-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e69bd-153">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e69bd-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-154">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e69bd-155">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-155">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-156">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-157">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-158">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-159">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-159">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-160">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-161">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-162">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-163">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-164">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-164">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-165">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="e69bd-166">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: interne Schnittstelle Knoten 1 und Knoten 2</span><span class="sxs-lookup"><span data-stu-id="e69bd-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e69bd-167">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e69bd-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e69bd-168">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-168">Source IP address</span></span></th>
<th><span data-ttu-id="e69bd-169">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-169">Destination IP address</span></span></th>
<th><span data-ttu-id="e69bd-170">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e69bd-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e69bd-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e69bd-172">Any (kann als Front-End-Server Adresse definiert werden oder Front-End-Pool virtuelle IP-Adresse, die den XMPP-Gatewaydienst ausführt)</span><span class="sxs-lookup"><span data-stu-id="e69bd-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-173">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-174">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="e69bd-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e69bd-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-176">Any (kann als Front-End-Server Server-IP oder-Pool definiert werden, der den zentralen Verwaltungsspeicher umfasst)</span><span class="sxs-lookup"><span data-stu-id="e69bd-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-177">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-178">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e69bd-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e69bd-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e69bd-180">Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</span><span class="sxs-lookup"><span data-stu-id="e69bd-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-181">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-182">Webkonferenz Datenverkehr von der internen Bereitstellung zur internen Edgeserver-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-183">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e69bd-184">Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</span><span class="sxs-lookup"><span data-stu-id="e69bd-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-185">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-186">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="e69bd-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-187">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-188">Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</span><span class="sxs-lookup"><span data-stu-id="e69bd-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-189">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-190">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="e69bd-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e69bd-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e69bd-192">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-192">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-193">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-194">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="e69bd-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e69bd-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e69bd-196">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-196">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-197">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-198">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="e69bd-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e69bd-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e69bd-200">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-200">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-201">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-202">Zentralisierter Protokollierungsdienst-Controller mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController.exe) oder Agent-Befehlen (ClsAgent.exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="e69bd-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e69bd-203">Hardware Geräte zum Lastenausgleich haben spezifische Anforderungen, wenn Sie bereitgestellt werden, um Verfügbarkeit und Lastenausgleich für lync Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="e69bd-204">Die Anforderungen sind in der folgenden Abbildung und den Tabellen definiert.</span><span class="sxs-lookup"><span data-stu-id="e69bd-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="e69bd-205">Drittanbieter verwenden möglicherweise unterschiedliche Terminologie für die hier definierten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="e69bd-206">Es ist erforderlich, die Anforderungen von lync Server den Features und Konfigurationsoptionen Ihres Hardware-Lastenausgleichs Anbieters zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="e69bd-207">Berücksichtigen Sie beim Konfigurieren von Hardware-Lastenausgleichsmodulen die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="e69bd-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="e69bd-208">Die Quellnetzwerk Adressübersetzung (SNAT) kann für Zugriffs-Edgedienst und Webkonferenz-Edgedienst auf dem Hardwaregerät zum Lastenausgleich konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e69bd-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="e69bd-209">SNAT kann nicht auf dem A/V-Edgedienst konfiguriert werden – der A/V-Edgedienst muss mit der realen Serveradresse und nicht mit der virtuellen HLB-IP (VIP), für einfaches Traversieren von UDP über NAT (Stun)/Traversal mit Relay NAT (Turn)/Federation Turn (FTURN) ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e69bd-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="e69bd-210">Wenn der Client eine Anforderung an die HLB sendet, muss die Antwort vom HLB-VIP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="e69bd-211">Wenn der Client eine Anforderung an den Edge sendet, muss die Antwort von der Edge-IP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="e69bd-212">Öffentliche IP-Adressen werden auf jeder Server Schnittstelle und den VIPs der HLB verwendet, und Ihre Anforderungen an die öffentliche IP-Adresse lauten N + 1, wobei es eine öffentliche IP-Adresse für jede reale Server Schnittstelle und eine für jede HLB-VIP gibt.</span><span class="sxs-lookup"><span data-stu-id="e69bd-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="e69bd-213">Wenn Sie 2 Edgeserver im Pool haben, ergeben sich 9 öffentliche IP-Adressen, wobei 3 für die HLB-VIPs und eine für jede Edge-Server-Schnittstelle (insgesamt sechs für die Server) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e69bd-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="e69bd-214">Für Zugriffs-Edgedienst und Webkonferenz-Edgedienst (und Verwenden von NAT auf der HLB) kontaktiert der Client den VIP, der VIP ändert die Quell-IP-Adresse vom Client in seine eigene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="e69bd-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="e69bd-215">Die Server Schnittstelle adressiert die Absenderadresse an den VIP, der VIP ändert die Quelladresse von der IP-Adresse der Server Schnittstelle und sendet das Paket an den Client.</span><span class="sxs-lookup"><span data-stu-id="e69bd-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="e69bd-216">Für den A/V-Edgedienst darf der VIP die Quell-IP-Adresse nicht ändern, und die reale Serveradresse wird direkt an den Client zurückgegeben – Sie können NAT nicht für den Datenverkehr in der HLB konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e69bd-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="e69bd-217">Wenn der Client eine Anforderung an den HLB-VIP sendet, muss die Antwort vom HLB-VIP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="e69bd-218">Wenn der Client eine Anforderung an die Edge-IP sendet, muss die Antwort von der Edge-IP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="e69bd-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="e69bd-219">Für AV behält die externe Firewall die öffentliche IP-Adresse des realen Servers für alle Pakete bei.</span><span class="sxs-lookup"><span data-stu-id="e69bd-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="e69bd-220">Nach der festgelegten Meldung erfolgt der Client für A/V-Edgedienst Kommunikation mit dem realen Server und nicht mit der HLB.</span><span class="sxs-lookup"><span data-stu-id="e69bd-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="e69bd-221">Interner Edgeserver für interne Server und Clients müssen weitergeleitet werden, und für alle internen Netzwerke, die Server oder Clients hosten, werden persistente Routen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e69bd-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="e69bd-222">Das HLB Zugriffs-Edgedienst VIP fungiert als Standardgateway für jede Edge-Server-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e69bd-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e69bd-223">Weitere Informationen zur NAT-Planung und-Funktionalität finden Sie unter <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware Lastenausgleichsanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e69bd-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e69bd-224">![Details zu Edgeserver Ports und Protokollen](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Details zu Edgeserver Ports und Protokollen")</span><span class="sxs-lookup"><span data-stu-id="e69bd-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="e69bd-225">Erforderliche Einstellungen für externe Ports für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: virtuelle IPS für externe Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e69bd-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e69bd-226">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e69bd-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e69bd-227">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-227">Source IP address</span></span></th>
<th><span data-ttu-id="e69bd-228">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-228">Destination IP address</span></span></th>
<th><span data-ttu-id="e69bd-229">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e69bd-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e69bd-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e69bd-231">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-231">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-232">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="e69bd-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-233">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="e69bd-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e69bd-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e69bd-235">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="e69bd-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-236">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-236">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-237">XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-verbünden</span><span class="sxs-lookup"><span data-stu-id="e69bd-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-238">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-239">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-239">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-240">Zugriffs-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-241">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="e69bd-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-242">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e69bd-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e69bd-243">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-243">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-244">Zugriffs-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-245">SIP-Signalisierungs-, Verbund-und öffentliche Instant Messaging-Konnektivität mit SIP</span><span class="sxs-lookup"><span data-stu-id="e69bd-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-246">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e69bd-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e69bd-247">Zugriffs-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-248">Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="e69bd-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="e69bd-249">SIP-Signalisierungs-, Verbund-und öffentliche Instant Messaging-Konnektivität mit SIP</span><span class="sxs-lookup"><span data-stu-id="e69bd-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-250">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-251">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-251">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-252">Edgeserver Webkonferenz-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-253">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="e69bd-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-254">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e69bd-255">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-255">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-256">Edgeserver A/V-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-257">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-258">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-259">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-259">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-260">Edgeserver A/V-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e69bd-261">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="e69bd-262">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: virtuelle IP-Adressen der internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e69bd-263">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="e69bd-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e69bd-264">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-264">Source IP address</span></span></th>
<th><span data-ttu-id="e69bd-265">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="e69bd-265">Destination IP address</span></span></th>
<th><span data-ttu-id="e69bd-266">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="e69bd-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-267">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e69bd-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e69bd-268">Any (kann als Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="e69bd-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-269">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-270">Ausgehender SIP-Datenverkehr (vom Director, Directorpool virtuellen IP-Adresse, Front-End-Server oder Front-End-Pool virtuellen IP-Adresse) zu einem internen VIP-Edge-Ausgang</span><span class="sxs-lookup"><span data-stu-id="e69bd-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-271">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e69bd-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e69bd-272">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-273">Any (kann als Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="e69bd-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-274">Eingehender SIP-Datenverkehr (an Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e69bd-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e69bd-276">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="e69bd-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e69bd-277">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-278">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e69bd-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-279">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e69bd-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e69bd-280">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-280">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-281">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-282">Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen internen Benutzern und externen Benutzern</span><span class="sxs-lookup"><span data-stu-id="e69bd-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e69bd-283">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-284">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-284">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-285">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-286">Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e69bd-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e69bd-287">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e69bd-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e69bd-288">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e69bd-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e69bd-289">Beliebig</span><span class="sxs-lookup"><span data-stu-id="e69bd-289">Any</span></span></p></td>
<td><p><span data-ttu-id="e69bd-290">Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e69bd-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

