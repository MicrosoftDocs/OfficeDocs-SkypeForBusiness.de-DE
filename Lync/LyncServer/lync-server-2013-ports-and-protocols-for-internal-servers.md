---
title: 'Lync Server 2013: Ports und Protokolle für interne Server'
description: 'Lync Server 2013: Ports und Protokolle für interne Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566355"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="b0f4f-103">Ports und Protokolle für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0f4f-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0f4f-104">_**Letztes Änderungsstand des Themas:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="b0f4f-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="b0f4f-105">In diesem Abschnitt werden die von Servern, Lastenausgleichssystemen und Clients in einer lync Server-Bereitstellung verwendeten Ports und Protokolle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0f4f-106">Lync-und Communicator-Clients werden, wenn Sie an einer Kommunikation mit einem einzelnen beteiligt sind, häufig als Peer-to-Peer bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="b0f4f-107">Technisch gesehen kommunizieren die beiden Clients in einer eins-zu-eins-Unterhaltung mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="b0f4f-108">IMMCU ist eine Komponente von Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="b0f4f-109">Wenn Sie die IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Aufzeichnung von Anrufdetails und andere Features, die der Front-End-Server aktiviert, aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="b0f4f-110">Die Kommunikation erfolgt über einen dynamischen Quell Port auf dem Client zum Front-End-Server Port TLS/TCP/5061 (vorausgesetzt, dass die empfohlene Transportschichtsicherheit verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="b0f4f-111">Die Peer-zu-Peer-Kommunikation (sowie mehr Parteien-Chat) ist nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b0f4f-112">Port-und Protokoll Details</span><span class="sxs-lookup"><span data-stu-id="b0f4f-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0f4f-113">Die Windows-Firewall muss gestartet werden, bevor Sie die lync Server Dienste auf einem Server starten, da lync Server die erforderlichen Ports in der Firewall öffnet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="b0f4f-114">Ausführliche Informationen zur Firewall-Konfiguration für Edge-Komponenten finden Sie unter [bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="b0f4f-115">In der folgenden Tabelle sind die Ports aufgeführt, die für jede interne Serverrolle geöffnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="b0f4f-116">Erforderliche Serverports (nach Server Rolle)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-116">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0f4f-117">Serverrolle</span><span class="sxs-lookup"><span data-stu-id="b0f4f-117">Server role</span></span></th>
<th><span data-ttu-id="b0f4f-118">Dienstname</span><span class="sxs-lookup"><span data-stu-id="b0f4f-118">Service name</span></span></th>
<th><span data-ttu-id="b0f4f-119">Port</span><span class="sxs-lookup"><span data-stu-id="b0f4f-119">Port</span></span></th>
<th><span data-ttu-id="b0f4f-120">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b0f4f-120">Protocol</span></span></th>
<th><span data-ttu-id="b0f4f-121">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="b0f4f-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-122">Alle Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-123">SQL-Browser</span><span class="sxs-lookup"><span data-stu-id="b0f4f-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-124">1434</span><span class="sxs-lookup"><span data-stu-id="b0f4f-124">1434</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-125">UDP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-126">SQL-Browser für die lokale replizierte Kopie der zentraler Verwaltungsspeicher Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-127">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-128">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-129">5060</span><span class="sxs-lookup"><span data-stu-id="b0f4f-129">5060</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-130">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-131">Optional von Standard Edition-Servern und Front-End-Servern für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-132">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-133">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-134">5061</span><span class="sxs-lookup"><span data-stu-id="b0f4f-134">5061</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-136">Wird von Standard Edition-Servern und Front-End-Pools für die gesamte interne SIP-Kommunikation zwischen Servern (MTLS), für die SIP-Kommunikation zwischen Server und Client (TLS) und für die SIP-Kommunikation zwischen Front-End-Servern und Vermittlungsservern (MTLS) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-136">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="b0f4f-137">Wird auch für die Kommunikation mit Monitoring Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-137">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-138">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-139">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-140">444</span><span class="sxs-lookup"><span data-stu-id="b0f4f-140">444</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-141">HTTPS</span></span></p>
<p><span data-ttu-id="b0f4f-142">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-143">Wird für die HTTPS-Kommunikation zwischen dem Fokus (der lync Server Komponente, die den Konferenzstatus verwaltet) und den einzelnen Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="b0f4f-144">Dieser Port wird auch für die TCP-Kommunikation zwischen Survivable Branch Appliances und Front-End-Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-145">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-146">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-147">135</span><span class="sxs-lookup"><span data-stu-id="b0f4f-147">135</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-148">DCOM und Remoteprozeduraufruf (RPC)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-149">Wird für DCOM-basierte Vorgänge wie das Verschieben von Benutzern, die Benutzer Replikationssynchronisierung und die Adressbuchsynchronisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-150">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-151">Lync Server Sofortnachrichten-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-152">5062</span><span class="sxs-lookup"><span data-stu-id="b0f4f-152">5062</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-153">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-154">Wird für eingehende SIP-Anforderungen für Chat Konferenzen (Instant Messaging) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-155">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-156">Lync Server Webkonferenzdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-157">8057</span><span class="sxs-lookup"><span data-stu-id="b0f4f-157">8057</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-159">Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) vom Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-160">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-161">Lync Server Webkonferenz-Kompatibilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-162">8058</span><span class="sxs-lookup"><span data-stu-id="b0f4f-162">8058</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-164">Wird zum Überwachen von PSOM-Verbindungen (Persistent Shared Object Model) aus dem Live Meeting-Client und früheren Versionen von lync Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-165">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-166">Lync Server Audio/Video-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-167">5063</span><span class="sxs-lookup"><span data-stu-id="b0f4f-167">5063</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-168">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-169">Wird für eingehende SIP-Anforderungen für Audio/Video-Konferenzen (A/V) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-170">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-171">Lync Server Audio/Video-Konferenzdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="b0f4f-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-174">Für Videokonferenzen verwendeter Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-175">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-176">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-177">80</span><span class="sxs-lookup"><span data-stu-id="b0f4f-177">80</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-179">Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (von IIS-Webkomponenten verwendete URLs) verwendet, wenn kein HTTPS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-180">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-181">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-182">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-182">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-184">Wird für die Kommunikation von Front-End-Servern mit den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-185">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-186">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-187">8080</span><span class="sxs-lookup"><span data-stu-id="b0f4f-187">8080</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-188">TCP und http</span><span class="sxs-lookup"><span data-stu-id="b0f4f-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-189">Wird von Webkomponenten für den externen Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-190">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-191">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="b0f4f-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-192">4443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-192">4443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-194">HTTPS (vom Reverseproxy) und HTTPS-Front-End-Kommunikation zwischen Pools für die Auto Ermittlungs Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-195">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-196">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="b0f4f-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-197">8060</span><span class="sxs-lookup"><span data-stu-id="b0f4f-197">8060</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-199">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-200">Webserverkomponente</span><span class="sxs-lookup"><span data-stu-id="b0f4f-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-201">8061</span><span class="sxs-lookup"><span data-stu-id="b0f4f-201">8061</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-203">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-204">Komponente "Mobility Services"</span><span class="sxs-lookup"><span data-stu-id="b0f4f-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-205">5086</span><span class="sxs-lookup"><span data-stu-id="b0f4f-205">5086</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-207">SIP-Port für interne Prozesse der Mobilitätsdienste</span><span class="sxs-lookup"><span data-stu-id="b0f4f-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-208">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-209">Komponente "Mobility Services"</span><span class="sxs-lookup"><span data-stu-id="b0f4f-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-210">5087</span><span class="sxs-lookup"><span data-stu-id="b0f4f-210">5087</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-212">SIP-Port für interne Prozesse der Mobilitätsdienste</span><span class="sxs-lookup"><span data-stu-id="b0f4f-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-213">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-214">Komponente "Mobility Services"</span><span class="sxs-lookup"><span data-stu-id="b0f4f-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-215">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-215">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-217">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-218">Lync Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-219">5064</span><span class="sxs-lookup"><span data-stu-id="b0f4f-219">5064</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-220">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-221">Wird für eingehende SIP-Anforderungen für Einwahlkonferenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-222">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-223">Lync Server Konferenz Aufsichtsdienst (Einwahlkonferenzen)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-224">5072</span><span class="sxs-lookup"><span data-stu-id="b0f4f-224">5072</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-225">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-226">Wird für eingehende SIP-Anforderungen für Attendant (Einwahlkonferenzen) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-227">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b0f4f-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-228">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-229">5070</span><span class="sxs-lookup"><span data-stu-id="b0f4f-229">5070</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-230">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-231">Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server zum Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-232">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b0f4f-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-233">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-234">5067</span><span class="sxs-lookup"><span data-stu-id="b0f4f-234">5067</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-236">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-237">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b0f4f-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-238">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-239">5068</span><span class="sxs-lookup"><span data-stu-id="b0f4f-239">5068</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-240">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-241">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway zum Vermittlungsserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-242">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b0f4f-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-243">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-244">5081</span><span class="sxs-lookup"><span data-stu-id="b0f4f-244">5081</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-245">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-246">Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-247">Front-End-Server, auf denen auch eine verbundene Vermittlungsserver ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b0f4f-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-248">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-249">5082</span><span class="sxs-lookup"><span data-stu-id="b0f4f-249">5082</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-251">Wird für ausgehende SIP-Anforderungen vom Vermittlungsserver an das PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-252">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-253">Lync Server Anwendungsfreigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-254">5065</span><span class="sxs-lookup"><span data-stu-id="b0f4f-254">5065</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-255">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-256">Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-257">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-258">Lync Server Anwendungsfreigabe Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="b0f4f-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-260">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-261">Für die Anwendungsfreigabe verwendete Medienportbereich.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-262">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-263">Lync Server Konferenz Ansagedienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-264">5073</span><span class="sxs-lookup"><span data-stu-id="b0f4f-264">5073</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-265">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-266">Wird für eingehende SIP-Anforderungen für den lync Server Konferenzankündigungsdienst (für Einwahlkonferenzen) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-267">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-268">Lync Server Dienst zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="b0f4f-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-269">5075</span><span class="sxs-lookup"><span data-stu-id="b0f4f-269">5075</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-270">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-271">Wird für eingehende SIP-Anforderungen für den Anwendung zum Parken von Anrufen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-272">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-273">Lync Server Audio-Test Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-274">5076</span><span class="sxs-lookup"><span data-stu-id="b0f4f-274">5076</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-275">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-276">Wird für eingehende SIP-Anforderungen für den Audio-Test Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-277">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-278">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="b0f4f-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-279">5066</span><span class="sxs-lookup"><span data-stu-id="b0f4f-279">5066</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-280">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-281">Wird für das ausgehende Enhanced 9-1-1 (E9-1-1)-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-282">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-283">Lync Server Reaktionsgruppendienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-284">5071</span><span class="sxs-lookup"><span data-stu-id="b0f4f-284">5071</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-285">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-286">Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-287">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-288">Lync Server Reaktionsgruppendienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-289">8404</span><span class="sxs-lookup"><span data-stu-id="b0f4f-289">8404</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-291">Wird für eingehende SIP-Anforderungen für den Reaktionsgruppenanwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-292">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-293">Lync Server bandbreitenrichtliniendienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-294">5080</span><span class="sxs-lookup"><span data-stu-id="b0f4f-294">5080</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-295">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-296">Wird für die Anrufsteuerung durch den bandbreitenrichtliniendienst für A/V-Edge-Umdrehungs Datenverkehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-297">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-298">Lync Server bandbreitenrichtliniendienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-299">448</span><span class="sxs-lookup"><span data-stu-id="b0f4f-299">448</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-300">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-301">Wird für die Anrufsteuerung vom lync Server bandbreitenrichtliniendienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-302">Front-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet</span><span class="sxs-lookup"><span data-stu-id="b0f4f-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-303">Lync Server des Master Replicator-Agent-Diensts</span><span class="sxs-lookup"><span data-stu-id="b0f4f-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-304">445</span><span class="sxs-lookup"><span data-stu-id="b0f4f-304">445</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-305">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-306">Wird zum Pushen von Konfigurationsdaten aus dem zentralen Verwaltungsspeicher auf Server mit lync Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-307">Alle Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-308">SQL-Browser</span><span class="sxs-lookup"><span data-stu-id="b0f4f-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-309">1434</span><span class="sxs-lookup"><span data-stu-id="b0f4f-309">1434</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-310">UDP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-311">SQL-Browser für lokale replizierte Kopie der Daten des zentralen Verwaltungsspeichers in der lokalen SQL Server Instanz</span><span class="sxs-lookup"><span data-stu-id="b0f4f-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-312">Alle internen Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-313">Verschiedene</span><span class="sxs-lookup"><span data-stu-id="b0f4f-313">Various</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="b0f4f-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-316">Medienportbereich, der für Audiokonferenzen auf allen internen Servern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="b0f4f-317">Wird von allen Servern verwendet, die Audio beenden: Front-End-Server (für lync Server Konferenz Aufsichtsdienst, lync Server Konferenzankündigungsdienst und lync Server Audio/Video-Konferenzdienst) und Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-318">Office-webapps-Server</span><span class="sxs-lookup"><span data-stu-id="b0f4f-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0f4f-319">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0f4f-320">Wird von lync Server 2013 verwendet, um eine Verbindung mit Office-webapps Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-321">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-322">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-323">5060</span><span class="sxs-lookup"><span data-stu-id="b0f4f-323">5060</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-324">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-325">Optional für statische Routen zu vertrauenswürdigen Diensten wie Remote Anruf Steuerungs Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-326">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-327">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-328">444</span><span class="sxs-lookup"><span data-stu-id="b0f4f-328">444</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-329">HTTPS</span></span></p>
<p><span data-ttu-id="b0f4f-330">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-331">Kommunikation zwischen Servern zwischen Front-End und Director.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="b0f4f-332">Darüber hinaus veröffentlichen Clientzertifikate (an Front-End-Server) oder überprüfen, ob das Clientzertifikat bereits veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-333">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-334">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-335">80</span><span class="sxs-lookup"><span data-stu-id="b0f4f-335">80</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-336">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-337">Wird für die anfängliche Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-337">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="b0f4f-338">Im normalen Betrieb wechselt zum HTTPS-Datenverkehr unter Verwendung von Port 443 und Protokolltyp TCP.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-338">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-339">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-340">Lync Server-webkompatibilitäts Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-341">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-341">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-343">Wird für die Kommunikation von Directors zu den FQDNs der Webfarm (die von IIS-Webkomponenten verwendeten URLs) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-344">Verwaltungsrat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-345">Lync Server Front-End Dienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-346">5061</span><span class="sxs-lookup"><span data-stu-id="b0f4f-346">5061</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-347">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-348">Wird für die interne Kommunikation zwischen Servern und für Clientverbindungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-349">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="b0f4f-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-350">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-351">5070</span><span class="sxs-lookup"><span data-stu-id="b0f4f-351">5070</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-352">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-353">Wird vom Vermittlungsserver für eingehende Anforderungen vom Front-End-Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-354">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="b0f4f-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-355">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-356">5067</span><span class="sxs-lookup"><span data-stu-id="b0f4f-356">5067</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-358">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-359">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="b0f4f-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-360">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-361">5068</span><span class="sxs-lookup"><span data-stu-id="b0f4f-361">5068</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-362">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-363">Wird für eingehende SIP-Anforderungen vom PSTN-Gateway verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-364">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="b0f4f-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-365">Lync Server Vermittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="b0f4f-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-366">5070</span><span class="sxs-lookup"><span data-stu-id="b0f4f-366">5070</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-368">Wird für SIP-Anforderungen von den Front-End-Servern verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-369">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-370">SIP für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-371">5041</span><span class="sxs-lookup"><span data-stu-id="b0f4f-371">5041</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-373">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-374">Windows Communication Foundation (WCF) für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-375">881</span><span class="sxs-lookup"><span data-stu-id="b0f4f-375">881</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-376">TCP (TLS) und TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-377">Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-378">Dateiübertragungsdienst für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b0f4f-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-379">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-379">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b0f4f-381">Einige Szenarien für die Remoteanrufsteuerung erfordern eine TCP-Verbindung zwischen dem Front-End-Server oder dem Director und der Nebenstellenanlage.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="b0f4f-382">Obwohl lync Server TCP-Port 5060 nicht mehr verwendet, erstellen Sie während der Bereitstellung von Remoteanrufsteuerung eine vertrauenswürdige Serverkonfiguration, die den FQDN des RCC-Leitungs Servers dem TCP-Port zuordnet, den der Front-End-Server oder Director zum Herstellen einer Verbindung mit dem PBX-System verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="b0f4f-383">Ausführliche Informationen finden Sie im <STRONG>CsTrustedApplicationComputer</STRONG> -Cmdlet in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="b0f4f-384">Für Ihre Pools, in denen nur Hardwarelastenausgleich (nicht DNS-Lastenausgleich) verwendet wird, werden in der folgenden Tabelle die Ports aufgeführt, die zum Öffnen der Hardwarelastenausgleichs-Geräte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="b0f4f-385">Hardware Lastenausgleichs-Ports bei Verwendung von nur Hardwarelastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0f4f-386">Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="b0f4f-386">Load Balancer</span></span></th>
<th><span data-ttu-id="b0f4f-387">Port</span><span class="sxs-lookup"><span data-stu-id="b0f4f-387">Port</span></span></th>
<th><span data-ttu-id="b0f4f-388">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b0f4f-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-389">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-390">5061</span><span class="sxs-lookup"><span data-stu-id="b0f4f-390">5061</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-392">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-393">444</span><span class="sxs-lookup"><span data-stu-id="b0f4f-393">444</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-395">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-396">135</span><span class="sxs-lookup"><span data-stu-id="b0f4f-396">135</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-397">DCOM und Remoteprozeduraufruf (RPC)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-398">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-399">80</span><span class="sxs-lookup"><span data-stu-id="b0f4f-399">80</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-401">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-402">8080</span><span class="sxs-lookup"><span data-stu-id="b0f4f-402">8080</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-403">TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server – von NTLM authentifizierte Clients und Geräte</span><span class="sxs-lookup"><span data-stu-id="b0f4f-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-404">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-405">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-405">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-407">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-408">4443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-408">4443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-409">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-410">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-411">5072</span><span class="sxs-lookup"><span data-stu-id="b0f4f-411">5072</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-412">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-413">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-414">5073</span><span class="sxs-lookup"><span data-stu-id="b0f4f-414">5073</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-415">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-416">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-417">5075</span><span class="sxs-lookup"><span data-stu-id="b0f4f-417">5075</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-418">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-419">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-420">5076</span><span class="sxs-lookup"><span data-stu-id="b0f4f-420">5076</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-421">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-422">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-423">5071</span><span class="sxs-lookup"><span data-stu-id="b0f4f-423">5071</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-424">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-425">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-426">5080</span><span class="sxs-lookup"><span data-stu-id="b0f4f-426">5080</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-427">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-428">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-429">448</span><span class="sxs-lookup"><span data-stu-id="b0f4f-429">448</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-430">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-431">Vermittlungsserver Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-432">5070</span><span class="sxs-lookup"><span data-stu-id="b0f4f-432">5070</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-433">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-434">Front-End-Server Lastenausgleich (wenn der Pool auch Vermittlungsserver ausgeführt wird)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-435">5070</span><span class="sxs-lookup"><span data-stu-id="b0f4f-435">5070</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-436">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-437">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-438">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-438">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-440">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-441">444</span><span class="sxs-lookup"><span data-stu-id="b0f4f-441">444</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-443">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-444">5061</span><span class="sxs-lookup"><span data-stu-id="b0f4f-444">5061</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-445">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-446">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-447">4443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-447">4443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-448">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0f4f-449">Für die Front-End-Pools und Director-Pools, die den DNS-Lastenausgleich verwenden, muss auch ein Hardwaregerät zum Lastenausgleich bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-449">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="b0f4f-450">In der folgenden Tabelle sind die Ports aufgeführt, die für diese Hardwarelastenausgleichs-Geräte geöffnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-450">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="b0f4f-451">Hardware Lastenausgleichs-Ports bei Verwendung des DNS-Lastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="b0f4f-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0f4f-452">Lastenausgleichssystem</span><span class="sxs-lookup"><span data-stu-id="b0f4f-452">Load Balancer</span></span></th>
<th><span data-ttu-id="b0f4f-453">Port</span><span class="sxs-lookup"><span data-stu-id="b0f4f-453">Port</span></span></th>
<th><span data-ttu-id="b0f4f-454">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b0f4f-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-455">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-456">80</span><span class="sxs-lookup"><span data-stu-id="b0f4f-456">80</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-458">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-459">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-459">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-461">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-462">8080</span><span class="sxs-lookup"><span data-stu-id="b0f4f-462">8080</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-463">TCP-Client und Geräte Abruf des Stammzertifikats von Front-End-Server – von NTLM authentifizierte Clients und Geräte</span><span class="sxs-lookup"><span data-stu-id="b0f4f-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-464">Front-End-Server Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-465">4443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-465">4443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-466">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-467">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-468">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-468">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b0f4f-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-470">Director-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="b0f4f-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-471">4443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-471">4443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-472">HTTPS (vom Reverseproxy)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="b0f4f-473">Erforderliche Client-Ports</span><span class="sxs-lookup"><span data-stu-id="b0f4f-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0f4f-474">Komponente</span><span class="sxs-lookup"><span data-stu-id="b0f4f-474">Component</span></span></th>
<th><span data-ttu-id="b0f4f-475">Port</span><span class="sxs-lookup"><span data-stu-id="b0f4f-475">Port</span></span></th>
<th><span data-ttu-id="b0f4f-476">Protokoll</span><span class="sxs-lookup"><span data-stu-id="b0f4f-476">Protocol</span></span></th>
<th><span data-ttu-id="b0f4f-477">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="b0f4f-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-478">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-479">67/68</span><span class="sxs-lookup"><span data-stu-id="b0f4f-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-480">DHCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-481">Wird von lync Server verwendet, um den FQDN des Registrars zu finden (wenn DNS-SRV fehlschlägt und manuelle Einstellungen nicht konfiguriert sind).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-482">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-483">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-483">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-485">Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-486">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-487">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-487">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-489">Wird für den Zugriff durch externe Benutzer auf Webkonferenz Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-490">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-491">443</span><span class="sxs-lookup"><span data-stu-id="b0f4f-491">443</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-492">TCP (Stun/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-493">Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (TCP) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-494">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-495">3478</span><span class="sxs-lookup"><span data-stu-id="b0f4f-495">3478</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-496">UDP (Stun/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-497">Wird für den Zugriff durch externe Benutzer auf A/V-Sitzungen und-Medien (UDP) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-498">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-499">5061</span><span class="sxs-lookup"><span data-stu-id="b0f4f-499">5061</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-501">Wird für den Client-zu-Server-SIP-Datenverkehr für den externen Benutzer Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-502">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="b0f4f-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-504">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-505">Wird für die Dateiübertragung zwischen lync-Clients und vorherigen Clients (Clients von Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 und Live Communications Server 2005) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-506">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b0f4f-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-509">Audioport Bereich (mindestens 20 Ports erforderlich)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-510">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b0f4f-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-513">Video Portbereich (mindestens 20 Ports erforderlich).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-514">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b0f4f-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-516">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-517">Peer-zu-Peer-Dateiübertragung (für die Übertragung von Konferenz Dateien verwenden Clients PSOM).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0f4f-518">Clients</span><span class="sxs-lookup"><span data-stu-id="b0f4f-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b0f4f-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-520">TCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-521">Anwendungsfreigabe.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0f4f-522">Aastra 6721ip (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="b0f4f-523">Telefonapparat Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="b0f4f-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="b0f4f-524">IP-Telefon HP 4110 (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="b0f4f-525">IP-Telefon HP 4120 (Telefonapparat)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="b0f4f-526">IP-Telefon Polycom CX500 (Telefon für öffentliche Bereiche)</span><span class="sxs-lookup"><span data-stu-id="b0f4f-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="b0f4f-527">IP-Telefonapparat Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="b0f4f-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="b0f4f-528">Polycom CX700-IP-Tischtelefon</span><span class="sxs-lookup"><span data-stu-id="b0f4f-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="b0f4f-529">IP-Konferenztelefon
Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="b0f4f-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-530">67/68</span><span class="sxs-lookup"><span data-stu-id="b0f4f-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-531">DHCP</span><span class="sxs-lookup"><span data-stu-id="b0f4f-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="b0f4f-532">Wird von den aufgelisteten Geräten verwendet, um das lync Server Zertifikat, den FQDN der Feststellung und den FQDN der Registrierung zu finden.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0f4f-533">**\*** Verwenden Sie zum Konfigurieren bestimmter Ports für diese Medientypen das CsConferencingConfiguration-Cmdlet (Parameter clientmediaportrangeenabled-, ClientMediaPort-und ClientMediaPortRange-Parameter).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0f4f-534">Die festgelegten Programme für lync-Clients erstellen automatisch die erforderlichen Betriebssystem-Firewall-Ausnahmen auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="b0f4f-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b0f4f-535">Die Ports, die für den Zugriff durch externe Benutzer verwendet werden, sind für jedes Szenario erforderlich, in dem der Client die Firewall der Organisation durchlaufen muss (beispielsweise externe Kommunikationen oder Besprechungen, die von anderen Organisationen gehostet werden).</span><span class="sxs-lookup"><span data-stu-id="b0f4f-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

