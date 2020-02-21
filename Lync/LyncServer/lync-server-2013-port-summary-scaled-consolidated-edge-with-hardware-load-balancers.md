---
title: Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardware-Lastenausgleich
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
ms.openlocfilehash: e6af913a6be7b92a7a640a2e06537197ba21351c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="58af6-102">Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58af6-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58af6-103">_**Letztes Änderungsstand des Themas:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="58af6-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="58af6-104">Die in dieser Szenario-Architektur beschriebene lync Server 2013 Edgeserver Funktionalität ähnelt dem, was in lync Server 2010 implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="58af6-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="58af6-105">Die auffälligste Ergänzung ist der Port **5269 over TCP** -Eintrag für das Extensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="58af6-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="58af6-106">Lync Server 2013 stellt optional einen XMPP-Proxy auf dem Edgeserver oder Edgepool und dem XMPP-Gatewayserver auf dem Front-End-Server oder Front-End-Pool bereit.</span><span class="sxs-lookup"><span data-stu-id="58af6-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="58af6-107">Zusätzlich zu IPv4 unterstützt die Edgeserver jetzt IPv6.</span><span class="sxs-lookup"><span data-stu-id="58af6-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="58af6-108">In den Szenarios wird jedoch nur IPv4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="58af6-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="58af6-109">**Skalierter konsolidierter Edgeserver mit Hardware Lastenausgleich**</span><span class="sxs-lookup"><span data-stu-id="58af6-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="58af6-110">![Edgeserver Umkreisnetzwerk-Ports und-Protokolle](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edgeserver Umkreisnetzwerk-Ports und-Protokolle")</span><span class="sxs-lookup"><span data-stu-id="58af6-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="58af6-111">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="58af6-111">Port and Protocol Details</span></span>

<span data-ttu-id="58af6-112">Es wird empfohlen, nur die Ports zu öffnen, die zur Unterstützung der Funktionalität erforderlich sind, für die Sie externen Zugriff bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="58af6-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="58af6-113">Damit der Remotezugriff für einen beliebigen Edgedienst funktioniert, muss der SIP-Datenverkehr in beide Richtungen übertragen werden können (wie in der Abbildung zum eingehenden/ausgehenden Edgedatenverkehr gezeigt).</span><span class="sxs-lookup"><span data-stu-id="58af6-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="58af6-114">Anders ausgedrückt: Für Chat, Anwesenheit, Webkonferenzen, Audio/Video (A/V) und Partnerverbund ist SIP-Messaging an den und vom Zugriffs-Edgedienst erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58af6-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="58af6-115">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Lastenausgleich für Hardware: externe Schnittstelle – Knoten 1 und Knoten 2 (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="58af6-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58af6-116">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="58af6-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="58af6-117">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-117">Source IP address</span></span></th>
<th><span data-ttu-id="58af6-118">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-118">Destination IP address</span></span></th>
<th><span data-ttu-id="58af6-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58af6-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58af6-120">Access/http/TCP/80</span><span class="sxs-lookup"><span data-stu-id="58af6-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="58af6-121">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-122">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-122">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-123">Zertifikatsperre/Zertifikatsperrlistenprüfung und -abruf</span><span class="sxs-lookup"><span data-stu-id="58af6-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="58af6-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="58af6-125">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-126">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-126">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-127">DNS-Abfrage über TCP</span><span class="sxs-lookup"><span data-stu-id="58af6-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="58af6-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="58af6-129">Edgeserver Zugriffs-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-130">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-130">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-131">DNS-Abfrage über UDP</span><span class="sxs-lookup"><span data-stu-id="58af6-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-132">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="58af6-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="58af6-133">Edgeserver A/V-Edgedienst IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-134">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-134">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-135">Erforderlich für Partnerverbund mit Partnern, die Office Communications Server 2007, Office Communications Server 2007 R2, lync Server 2010 und lync Server 2013 durchführen.</span><span class="sxs-lookup"><span data-stu-id="58af6-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-136">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="58af6-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="58af6-137">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-138">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-138">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-139">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen.</span><span class="sxs-lookup"><span data-stu-id="58af6-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-140">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="58af6-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="58af6-141">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-141">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-142">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-143">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="58af6-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-144">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="58af6-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="58af6-145">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-145">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-146">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-147">Nur für Partnerverbund mit Partnern erforderlich, die Office Communications Server 2007 durchführen</span><span class="sxs-lookup"><span data-stu-id="58af6-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-148">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="58af6-149">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-150">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-150">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-151">3478 Outbound wird verwendet, um die Version von Edgeserver zu bestimmen, mit der lync Server kommuniziert, und auch für den Mediendatenverkehr von Edgeserver zu Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="58af6-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="58af6-152">Erforderlich für Partnerverbund mit lync Server 2010, Windows Live Messenger und Office Communications Server 2007 R2 und auch, wenn mehrere Edge-Pools in einem Unternehmen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="58af6-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-153">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="58af6-154">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-154">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-155">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-156">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-157">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-158">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-158">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-159">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-160">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-161">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-162">Edgeserver A/V-Edgedienst öffentliche IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-163">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-163">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-164">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="58af6-165">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: interne Schnittstelle Knoten 1 und Knoten 2</span><span class="sxs-lookup"><span data-stu-id="58af6-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58af6-166">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="58af6-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="58af6-167">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-167">Source IP address</span></span></th>
<th><span data-ttu-id="58af6-168">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-168">Destination IP address</span></span></th>
<th><span data-ttu-id="58af6-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58af6-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58af6-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="58af6-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="58af6-171">Any (kann als Front-End-Server Adresse definiert werden oder Front-End-Pool virtuelle IP-Adresse, die den XMPP-Gatewaydienst ausführt)</span><span class="sxs-lookup"><span data-stu-id="58af6-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="58af6-172">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-173">Ausgehender XMPP-Datenverkehr vom XMPP-Gatewaydienst, der auf Front-End-Server oder Front-End-Pool läuft</span><span class="sxs-lookup"><span data-stu-id="58af6-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="58af6-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="58af6-175">Any (kann als Front-End-Server Server-IP oder-Pool definiert werden, der den zentralen Verwaltungsspeicher umfasst)</span><span class="sxs-lookup"><span data-stu-id="58af6-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="58af6-176">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-177">Replikation von Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver</span><span class="sxs-lookup"><span data-stu-id="58af6-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="58af6-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="58af6-179">Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</span><span class="sxs-lookup"><span data-stu-id="58af6-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="58af6-180">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-181">Webkonferenz Datenverkehr von der internen Bereitstellung zur internen Edgeserver-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-182">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="58af6-183">Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</span><span class="sxs-lookup"><span data-stu-id="58af6-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="58af6-184">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-185">Bevorzugter Pfad für die A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="58af6-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-186">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-187">Any (kann als Director-IP, Front-End-Server-IP oder virtueller Pool-IP definiert werden)</span><span class="sxs-lookup"><span data-stu-id="58af6-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="58af6-188">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-189">Fallback-Pfad für A/V-Medienübertragung zwischen internen und externen Benutzern, Survivable Branch Appliance oder Survivable Branch Server wenn die UDP-Kommunikation nicht hergestellt werden kann, wird TCP für Dateiübertragung und Desktopfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="58af6-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="58af6-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="58af6-191">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-191">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-192">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-193">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="58af6-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="58af6-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="58af6-195">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-195">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-196">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-197">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="58af6-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="58af6-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="58af6-199">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-199">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-200">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-201">Dienstcontroller für zentralisierte Protokollierung mit lync Server-Verwaltungsshell-und zentralisierten Protokollierungsdienst-Cmdlets, ClsController-Befehlszeilenoptionen (ClsController. exe) oder Agent-Befehlen (ClsAgent. exe) und Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="58af6-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="58af6-202">Hardware Geräte zum Lastenausgleich haben spezifische Anforderungen, wenn Sie bereitgestellt werden, um Verfügbarkeit und Lastenausgleich für lync Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="58af6-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="58af6-203">Die Anforderungen sind in der folgenden Abbildung und den Tabellen definiert.</span><span class="sxs-lookup"><span data-stu-id="58af6-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="58af6-204">Drittanbieter verwenden möglicherweise unterschiedliche Terminologie für die hier definierten Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="58af6-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="58af6-205">Es ist erforderlich, die Anforderungen von lync Server den Features und Konfigurationsoptionen Ihres Hardware-Lastenausgleichs Anbieters zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="58af6-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="58af6-206">Berücksichtigen Sie beim Konfigurieren von Hardware-Lastenausgleichsmodulen die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="58af6-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="58af6-207">Die Quellnetzwerk Adressübersetzung (SNAT) kann für Zugriffs-Edgedienst und Webkonferenz-Edgedienst auf dem Hardwaregerät zum Lastenausgleich konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="58af6-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="58af6-208">SNAT kann nicht auf dem A/V-Edgedienst konfiguriert werden – der A/V-Edgedienst muss mit der realen Serveradresse und nicht mit der virtuellen HLB-IP (VIP), für einfaches Traversieren von UDP über NAT (Stun)/Traversal mit Relay NAT (Turn)/Federation Turn (FTURN) ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="58af6-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="58af6-209">Wenn der Client eine Anforderung an die HLB sendet, muss die Antwort vom HLB-VIP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="58af6-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="58af6-210">Wenn der Client eine Anforderung an den Edge sendet, muss die Antwort von der Edge-IP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="58af6-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="58af6-211">Öffentliche IP-Adressen werden auf jeder Server Schnittstelle und den VIPs der HLB verwendet, und Ihre Anforderungen an die öffentliche IP-Adresse lauten N + 1, wobei es eine öffentliche IP-Adresse für jede reale Server Schnittstelle und eine für jede HLB-VIP gibt.</span><span class="sxs-lookup"><span data-stu-id="58af6-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="58af6-212">Wenn Sie 2 Edgeserver im Pool haben, ergeben sich 9 öffentliche IP-Adressen, wobei 3 für die HLB-VIPs und eine für jede Edge-Server-Schnittstelle (insgesamt sechs für die Server) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58af6-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="58af6-213">Für Zugriffs-Edgedienst und Webkonferenz-Edgedienst (und Verwenden von NAT auf der HLB) kontaktiert der Client den VIP, der VIP ändert die Quell-IP-Adresse vom Client in seine eigene IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="58af6-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="58af6-214">Die Server Schnittstelle adressiert die Absenderadresse an den VIP, der VIP ändert die Quelladresse von der IP-Adresse der Server Schnittstelle und sendet das Paket an den Client.</span><span class="sxs-lookup"><span data-stu-id="58af6-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="58af6-215">Für den A/V-Edgedienst darf der VIP die Quell-IP-Adresse nicht ändern, und die reale Serveradresse wird direkt an den Client zurückgegeben – Sie können NAT nicht für den Datenverkehr in der HLB konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="58af6-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="58af6-216">Wenn der Client eine Anforderung an den HLB-VIP sendet, muss die Antwort vom HLB-VIP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="58af6-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="58af6-217">Wenn der Client eine Anforderung an die Edge-IP sendet, muss die Antwort von der Edge-IP zurückkommen.</span><span class="sxs-lookup"><span data-stu-id="58af6-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="58af6-218">Für AV behält die externe Firewall die öffentliche IP-Adresse des realen Servers für alle Pakete bei.</span><span class="sxs-lookup"><span data-stu-id="58af6-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="58af6-219">Nach der festgelegten Meldung erfolgt der Client für A/V-Edgedienst Kommunikation mit dem realen Server und nicht mit der HLB.</span><span class="sxs-lookup"><span data-stu-id="58af6-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="58af6-220">Interner Edgeserver für interne Server und Clients müssen weitergeleitet werden, und für alle internen Netzwerke, die Server oder Clients hosten, werden persistente Routen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="58af6-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="58af6-221">Das HLB Zugriffs-Edgedienst VIP fungiert als Standardgateway für jede Edge-Server-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="58af6-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="58af6-222">Weitere Informationen zur NAT-Planung und-Funktionalität finden Sie unter <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware Lastenausgleichsanforderungen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="58af6-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="58af6-223">![Details zu Edgeserver Ports und Protokollen](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Details zu Edgeserver Ports und Protokollen")</span><span class="sxs-lookup"><span data-stu-id="58af6-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="58af6-224">Erforderliche Einstellungen für externe Ports für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: virtuelle IPS für externe Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="58af6-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58af6-225">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="58af6-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="58af6-226">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-226">Source IP address</span></span></th>
<th><span data-ttu-id="58af6-227">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-227">Destination IP address</span></span></th>
<th><span data-ttu-id="58af6-228">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58af6-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58af6-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="58af6-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="58af6-230">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-230">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-231">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="58af6-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="58af6-232">XMPP-Proxydienst akzeptiert Datenverkehr von XMPP-Kontakten in definierten XMPP-Partnerverbunden</span><span class="sxs-lookup"><span data-stu-id="58af6-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="58af6-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="58af6-234">XMPP-Proxy Dienst (Freigabe der IP-Adresse mit Zugriffs-Edgedienst)</span><span class="sxs-lookup"><span data-stu-id="58af6-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="58af6-235">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-235">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-236">XMPP-Proxy Dienst sendet Datenverkehr an XMPP-Kontakte in definierten XMPP-verbünden</span><span class="sxs-lookup"><span data-stu-id="58af6-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-237">Access/SIP (TLS)-/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-238">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-238">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-239">Zugriffs-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-240">Client-zu-Server-SIP-Datenverkehr für den externen Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="58af6-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-241">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="58af6-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="58af6-242">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-242">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-243">Zugriffs-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-244">SIP-Signalisierungs-, Verbund-und öffentliche Instant Messaging-Konnektivität mit SIP</span><span class="sxs-lookup"><span data-stu-id="58af6-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-245">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="58af6-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="58af6-246">Zugriffs-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-247">Verbundpartner</span><span class="sxs-lookup"><span data-stu-id="58af6-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="58af6-248">SIP-Signalisierungs-, Verbund-und öffentliche Instant Messaging-Konnektivität mit SIP</span><span class="sxs-lookup"><span data-stu-id="58af6-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-249">Webkonferenz-PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-250">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-250">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-251">Edgeserver Webkonferenz-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-252">Webkonferenzmedien</span><span class="sxs-lookup"><span data-stu-id="58af6-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-253">A/V/Stun, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="58af6-254">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-254">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-255">Edgeserver A/V-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-256">STUN/TURN-Aushandlung von Kandidaten über UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-257">A/V/Stun, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-258">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-258">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-259">Edgeserver A/V-Edgedienst öffentliche VIP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="58af6-260">STUN/TURN-Aushandlung von Kandidaten über TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="58af6-261">Zusammenfassung der Firewall für einen skalierten konsolidierten Edgeserver, Hardware Lastenausgleich: virtuelle IP-Adressen der internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58af6-262">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="58af6-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="58af6-263">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-263">Source IP address</span></span></th>
<th><span data-ttu-id="58af6-264">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="58af6-264">Destination IP address</span></span></th>
<th><span data-ttu-id="58af6-265">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58af6-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58af6-266">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="58af6-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="58af6-267">Any (kann als Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="58af6-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="58af6-268">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-269">Ausgehender SIP-Datenverkehr (vom Director, Directorpool virtuellen IP-Adresse, Front-End-Server oder Front-End-Pool virtuellen IP-Adresse) zu einem internen VIP-Edge-Ausgang</span><span class="sxs-lookup"><span data-stu-id="58af6-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-270">Access/SIP (MTLS)-/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="58af6-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="58af6-271">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-272">Any (kann als Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse definiert werden)</span><span class="sxs-lookup"><span data-stu-id="58af6-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="58af6-273">Eingehender SIP-Datenverkehr (an Director, Directorpool virtuelle IP-Adresse, Front-End-Server oder Front-End-Pool virtuelle IP-Adresse) aus Edgeserver internen Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="58af6-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="58af6-275">Any (kann als Front-End-Server IP-Adresse oder Front-End-Pool IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mit diesem Edgeserver definiert werden)</span><span class="sxs-lookup"><span data-stu-id="58af6-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="58af6-276">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-277">Authentifizierung von a/v-Benutzern (a/v-Authentifizierungsdienst) aus Front-End-Server oder Front-End-Pool-IP-Adresse oder Survivable Branch Appliance oder Survivable Branch Server mithilfe dieses Edgeserver</span><span class="sxs-lookup"><span data-stu-id="58af6-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-278">Stun/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="58af6-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="58af6-279">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-279">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-280">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-281">Bevorzugter Pfad für die Übertragung von A/V-Mediendaten zwischen internen Benutzern und externen Benutzern</span><span class="sxs-lookup"><span data-stu-id="58af6-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58af6-282">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-283">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-283">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-284">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-285">Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</span><span class="sxs-lookup"><span data-stu-id="58af6-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58af6-286">Stun/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="58af6-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="58af6-287">Edgeserver interne VIP-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58af6-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="58af6-288">Any</span><span class="sxs-lookup"><span data-stu-id="58af6-288">Any</span></span></p></td>
<td><p><span data-ttu-id="58af6-289">Ausweichpfad für die Übertragung von A/V-Mediendaten zwischen internen und externen Benutzern, wenn keine UDP-Kommunikation hergestellt werden kann und TCP für die Dateiübertragung und Desktopfreigabe verwendet wird</span><span class="sxs-lookup"><span data-stu-id="58af6-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

