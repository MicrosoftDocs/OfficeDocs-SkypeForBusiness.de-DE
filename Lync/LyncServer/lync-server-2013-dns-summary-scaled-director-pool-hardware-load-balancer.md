---
title: 'Lync Server 2013: DNS-Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich'
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
ms.openlocfilehash: 7ed4a3a810e4f1aa2fc5228e61cd68af163c91f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="e0ecd-102">DNS-Zusammenfassung – skalierte Directorpool, Hardwaregerät zum Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0ecd-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0ecd-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e0ecd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e0ecd-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des Directors für die Hardware Lastenausgleich erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e0ecd-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="e0ecd-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="e0ecd-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="e0ecd-106">Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert.</span><span class="sxs-lookup"><span data-stu-id="e0ecd-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="e0ecd-107">Anders als die Front-End-Server, hostet der Directorpool keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="e0ecd-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="e0ecd-108">Für den Directorpool erforderliche DNS-Einträge mit einem Hardware Gerät zum Lastenausgleich und DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="e0ecd-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0ecd-109">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="e0ecd-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e0ecd-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="e0ecd-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="e0ecd-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="e0ecd-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="e0ecd-112">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="e0ecd-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0ecd-113">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e0ecd-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e0ecd-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-115">Director</span><span class="sxs-lookup"><span data-stu-id="e0ecd-115">Director</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-116">Director-Hosteintrag, der für die Replikation und Server-zu-Server-Kommunikation verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e0ecd-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0ecd-117">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e0ecd-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e0ecd-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-119">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e0ecd-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-120">Host Eintrag für den DNS-Lastenausgleich Directorpool</span><span class="sxs-lookup"><span data-stu-id="e0ecd-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0ecd-121">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e0ecd-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0ecd-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-123">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e0ecd-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-124">SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e0ecd-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0ecd-125">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e0ecd-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0ecd-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-127">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e0ecd-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-128">Hardwaregerät zum Lastenausgleich des veröffentlichten Dialin-Webdiensts vom Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="e0ecd-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0ecd-129">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="e0ecd-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0ecd-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-131">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e0ecd-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-132">Hardwaregerät zum Lastenausgleich des veröffentlichten Besprechungs-Webdiensts vom Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="e0ecd-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0ecd-133">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="e0ecd-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0ecd-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-135">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="e0ecd-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="e0ecd-136">Von den externen Webticket-Webdiensten des Reverseproxy mit Hardwarelastenausgleich veröffentlichter und definierter Reverseproxy für den Directorpool</span><span class="sxs-lookup"><span data-stu-id="e0ecd-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

