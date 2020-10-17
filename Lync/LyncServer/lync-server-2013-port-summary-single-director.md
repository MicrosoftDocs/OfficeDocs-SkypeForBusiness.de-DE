---
title: 'Lync Server 2013: Port Zusammenfassung für einen einzelnen Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541cd7eb560cd9d509c5c0beec206803f2cddecc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533992"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="b20cf-102">Port Zusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b20cf-102">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b20cf-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b20cf-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b20cf-104">Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b20cf-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="b20cf-105">Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b20cf-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="b20cf-106">Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b20cf-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b20cf-107">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b20cf-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b20cf-108">Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b20cf-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="b20cf-109">Einzelne Director-Ports und-Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="b20cf-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b20cf-110">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b20cf-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b20cf-111">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="b20cf-111">Source IP address</span></span></th>
<th><span data-ttu-id="b20cf-112">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="b20cf-112">Destination IP address</span></span></th>
<th><span data-ttu-id="b20cf-113">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="b20cf-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b20cf-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="b20cf-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="b20cf-115">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="b20cf-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b20cf-116">Director</span><span class="sxs-lookup"><span data-stu-id="b20cf-116">Director</span></span></p></td>
<td><p><span data-ttu-id="b20cf-117">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="b20cf-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b20cf-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="b20cf-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="b20cf-119">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="b20cf-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b20cf-120">Director</span><span class="sxs-lookup"><span data-stu-id="b20cf-120">Director</span></span></p></td>
<td><p><span data-ttu-id="b20cf-121">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="b20cf-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b20cf-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="b20cf-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="b20cf-123">Director</span><span class="sxs-lookup"><span data-stu-id="b20cf-123">Director</span></span></p></td>
<td><p><span data-ttu-id="b20cf-124">Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="b20cf-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="b20cf-125">Inter-Server-Kommunikation zwischen dem Director und dem Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="b20cf-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b20cf-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="b20cf-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="b20cf-127">Interne Clients</span><span class="sxs-lookup"><span data-stu-id="b20cf-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b20cf-128">Director-Webdienste</span><span class="sxs-lookup"><span data-stu-id="b20cf-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="b20cf-129">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="b20cf-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b20cf-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="b20cf-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="b20cf-131">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="b20cf-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b20cf-132">Director-Webdienste</span><span class="sxs-lookup"><span data-stu-id="b20cf-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="b20cf-133">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="b20cf-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b20cf-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="b20cf-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="b20cf-135">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b20cf-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b20cf-136">Director</span><span class="sxs-lookup"><span data-stu-id="b20cf-136">Director</span></span></p></td>
<td><p><span data-ttu-id="b20cf-137">SIP-Kommunikation vom Edgeserver zum Director und zum Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b20cf-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b20cf-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b20cf-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b20cf-139">Beliebig</span><span class="sxs-lookup"><span data-stu-id="b20cf-139">Any</span></span></p></td>
<td><p><span data-ttu-id="b20cf-140">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b20cf-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b20cf-141">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="b20cf-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b20cf-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b20cf-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b20cf-143">Beliebig</span><span class="sxs-lookup"><span data-stu-id="b20cf-143">Any</span></span></p></td>
<td><p><span data-ttu-id="b20cf-144">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b20cf-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b20cf-145">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="b20cf-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b20cf-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b20cf-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b20cf-147">Beliebig</span><span class="sxs-lookup"><span data-stu-id="b20cf-147">Any</span></span></p></td>
<td><p><span data-ttu-id="b20cf-148">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b20cf-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b20cf-149">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="b20cf-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

