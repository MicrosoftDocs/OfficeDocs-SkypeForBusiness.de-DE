---
title: 'Lync Server 2013: Port Zusammenfassung für einen einzelnen Director'
description: 'Lync Server 2013: Port Summary – Single Director.'
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
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566371"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="0f9a4-103">Port Zusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9a4-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f9a4-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0f9a4-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0f9a4-105">Firewall-Portanforderungen für einen einzelnen Director bestehen aus den Ports, die verwendet werden, um die Kommunikation mit dem Director von der internen Schnittstelle oder dem internen Netzwerk des Reverseproxys herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="0f9a4-106">Microsoft lync Server 2013 standardmäßig erwartet, dass Ports http/TCP 8080 und HTTPS/TCP 4443 vom Reverseproxy zum Director geöffnet werden, sowie die Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="0f9a4-107">Darüber hinaus muss SIP-Kommunikation (Session Initiation Protocol) von der Edgeserver internen Schnittstelle zum Director und zum Front-End-Pool und Front-End-Server erfolgen.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="0f9a4-108">Das SIP-Protokoll verwendet SIP/MTLS/TCP 5061 vom Edgeserver zum Front-End-Pool und Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="0f9a4-109">Eine Regel, die SIP/MTLS/TCP 5061 Kommunikation vom Director, Front-End-Pool und Front-End-Server zur Edgeserver internen Schnittstelle zulässt, muss ebenfalls erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="0f9a4-110">Einzelne Director-Ports und-Protokolle für Firewall-Definitionen</span><span class="sxs-lookup"><span data-stu-id="0f9a4-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f9a4-111">Rolle/Protokoll/TCP oder UDP/Port</span><span class="sxs-lookup"><span data-stu-id="0f9a4-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0f9a4-112">Quell-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0f9a4-112">Source IP address</span></span></th>
<th><span data-ttu-id="0f9a4-113">Ziel-IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0f9a4-113">Destination IP address</span></span></th>
<th><span data-ttu-id="0f9a4-114">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="0f9a4-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f9a4-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="0f9a4-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-116">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="0f9a4-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-117">Director</span><span class="sxs-lookup"><span data-stu-id="0f9a4-117">Director</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-118">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f9a4-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="0f9a4-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-120">Interne Schnittstelle des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="0f9a4-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-121">Director</span><span class="sxs-lookup"><span data-stu-id="0f9a4-121">Director</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-122">Zunächst von der externen Seite des Reverseproxys empfangen, wird die Kommunikation an den Director und Front-End-Server-Webdienste gesendet.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f9a4-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="0f9a4-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-124">Director</span><span class="sxs-lookup"><span data-stu-id="0f9a4-124">Director</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-125">Front-End-Server oder Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="0f9a4-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-126">Inter-Server-Kommunikation zwischen dem Director und dem Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="0f9a4-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f9a4-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="0f9a4-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-128">Interne Clients</span><span class="sxs-lookup"><span data-stu-id="0f9a4-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-129">Director-Webdienste</span><span class="sxs-lookup"><span data-stu-id="0f9a4-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-130">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f9a4-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="0f9a4-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-132">Internal Clients</span><span class="sxs-lookup"><span data-stu-id="0f9a4-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-133">Director-Webdienste</span><span class="sxs-lookup"><span data-stu-id="0f9a4-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-134">Der Director stellt Webdienste für interne und externe Clients bereit.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f9a4-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="0f9a4-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-136">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f9a4-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-137">Director</span><span class="sxs-lookup"><span data-stu-id="0f9a4-137">Director</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-138">SIP-Kommunikation vom Edgeserver zum Director und zum Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="0f9a4-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f9a4-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="0f9a4-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-140">Beliebig</span><span class="sxs-lookup"><span data-stu-id="0f9a4-140">Any</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-141">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f9a4-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-142">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="0f9a4-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f9a4-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="0f9a4-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-144">Beliebig</span><span class="sxs-lookup"><span data-stu-id="0f9a4-144">Any</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-145">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f9a4-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-146">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="0f9a4-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f9a4-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="0f9a4-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-148">Beliebig</span><span class="sxs-lookup"><span data-stu-id="0f9a4-148">Any</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-149">Edgeserver interne Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f9a4-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0f9a4-150">Befehle und Protokollsammlung für den Controller des zentralisierten Protokollierungsdiensts (ClsController.exe) oder Agent (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="0f9a4-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

