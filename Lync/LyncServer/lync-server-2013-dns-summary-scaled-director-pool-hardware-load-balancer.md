---
title: 'Lync Server 2013: DNS-Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich'
description: 'Lync Server 2013: DNS-Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555881"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e278d-103">DNS-Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e278d-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e278d-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e278d-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e278d-105">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des Directors für die Hardware Lastenausgleich erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e278d-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="e278d-106">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e278d-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="e278d-107">Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert.</span><span class="sxs-lookup"><span data-stu-id="e278d-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="e278d-108">Anders als die Front-End-Server, hostet der Directorpool keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="e278d-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="e278d-109">Für den Directorpool erforderliche DNS-Einträge mit einem Hardware Gerät zum Lastenausgleich und DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="e278d-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e278d-110">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="e278d-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e278d-111">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="e278d-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="e278d-112">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="e278d-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="e278d-113">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="e278d-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e278d-114">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e278d-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e278d-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e278d-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e278d-116">Director</span><span class="sxs-lookup"><span data-stu-id="e278d-116">Director</span></span></p></td>
<td><p><span data-ttu-id="e278d-117">Director-Hosteintrag, der für die Replikation und Server-zu-Server-Kommunikation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e278d-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e278d-118">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="e278d-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e278d-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e278d-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e278d-120">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e278d-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e278d-121">Host Eintrag für den DNS-Lastenausgleich Directorpool</span><span class="sxs-lookup"><span data-stu-id="e278d-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e278d-122">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e278d-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e278d-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e278d-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e278d-124">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e278d-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e278d-125">SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e278d-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e278d-126">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e278d-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e278d-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e278d-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e278d-128">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e278d-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e278d-129">Hardwaregerät zum Lastenausgleich des veröffentlichten Dialin-Webdiensts vom Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="e278d-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e278d-130">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="e278d-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e278d-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e278d-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e278d-132">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e278d-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e278d-133">Hardwaregerät zum Lastenausgleich des veröffentlichten Besprechungs-Webdiensts vom Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="e278d-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e278d-134">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="e278d-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e278d-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e278d-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e278d-136">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e278d-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e278d-137">Von den externen Webticket-Webdiensten des Reverseproxy mit Hardwarelastenausgleich veröffentlichter und definierter Reverseproxy für den Directorpool</span><span class="sxs-lookup"><span data-stu-id="e278d-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

