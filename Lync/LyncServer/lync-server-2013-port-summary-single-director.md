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
ms.openlocfilehash: 8515785f66101df3af0d7d35de565ba344e2b91a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="4c1bd-102">Port Zusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c1bd-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c1bd-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4c1bd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4c1bd-104">Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="4c1bd-105">Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="4c1bd-106">Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="4c1bd-107">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="4c1bd-108">Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="4c1bd-109">Einzelne Director-Ports und-Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="4c1bd-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c1bd-110">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="4c1bd-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4c1bd-111">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="4c1bd-111">Source IP address</span></span></th>
<th><span data-ttu-id="4c1bd-112">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="4c1bd-112">Destination IP address</span></span></th>
<th><span data-ttu-id="4c1bd-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c1bd-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c1bd-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="4c1bd-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-115">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="4c1bd-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-116">Director</span><span class="sxs-lookup"><span data-stu-id="4c1bd-116">Director</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-117">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bd-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="4c1bd-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-119">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="4c1bd-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-120">Director</span><span class="sxs-lookup"><span data-stu-id="4c1bd-120">Director</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-121">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bd-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="4c1bd-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-123">Director</span><span class="sxs-lookup"><span data-stu-id="4c1bd-123">Director</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-124">Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="4c1bd-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-125">Inter-Server-Kommunikation zwischen dem Director und dem Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="4c1bd-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bd-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="4c1bd-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-127">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="4c1bd-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-128">Director-Webdienste</span><span class="sxs-lookup"><span data-stu-id="4c1bd-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-129">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bd-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="4c1bd-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-131">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="4c1bd-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-132">Director-Webdienste</span><span class="sxs-lookup"><span data-stu-id="4c1bd-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-133">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bd-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="4c1bd-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-135">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c1bd-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-136">Director</span><span class="sxs-lookup"><span data-stu-id="4c1bd-136">Director</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-137">SIP-Kommunikation vom Edgeserver zum Director und zum Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="4c1bd-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bd-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="4c1bd-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-139">Any</span><span class="sxs-lookup"><span data-stu-id="4c1bd-139">Any</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-140">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c1bd-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-141">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="4c1bd-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c1bd-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="4c1bd-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-143">Any</span><span class="sxs-lookup"><span data-stu-id="4c1bd-143">Any</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-144">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c1bd-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-145">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="4c1bd-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c1bd-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="4c1bd-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-147">Any</span><span class="sxs-lookup"><span data-stu-id="4c1bd-147">Any</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-148">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4c1bd-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4c1bd-149">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="4c1bd-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

