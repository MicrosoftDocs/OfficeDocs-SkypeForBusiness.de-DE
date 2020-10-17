---
title: 'Lync Server 2013: DNS-Zusammenfassung-DNS-und HLB-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532152"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="785e4-102">DNS-Zusammenfassung-DNS-und HLB-Lastenausgleich in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="785e4-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="785e4-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="785e4-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="785e4-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des Directors für DNS-Lastenausgleich und Hardwarelastenausgleich erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="785e4-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="785e4-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="785e4-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="785e4-106">Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert.</span><span class="sxs-lookup"><span data-stu-id="785e4-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="785e4-107">Anders als die Front-End-Server, hostet der Directorpool keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="785e4-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="785e4-108">Für den Directorpool erforderliche DNS-Einträge bei Verwendung des DNS-Lastenausgleichs und des Hardwarelastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="785e4-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="785e4-109">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="785e4-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="785e4-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="785e4-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="785e4-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="785e4-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="785e4-112">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="785e4-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="785e4-113">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="785e4-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="785e4-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="785e4-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="785e4-115">Director</span><span class="sxs-lookup"><span data-stu-id="785e4-115">Director</span></span></p></td>
<td><p><span data-ttu-id="785e4-116">Director-Hosteintrag für Replikation und Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="785e4-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="785e4-117">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="785e4-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="785e4-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="785e4-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="785e4-119">Directorpool</span><span class="sxs-lookup"><span data-stu-id="785e4-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="785e4-120">Host Eintrag für die Directorpool für den DNS-Lastenausgleich für Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="785e4-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="785e4-121">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="785e4-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="785e4-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="785e4-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="785e4-123">Directorpool</span><span class="sxs-lookup"><span data-stu-id="785e4-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="785e4-124">SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edgeserver</span><span class="sxs-lookup"><span data-stu-id="785e4-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="785e4-125">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="785e4-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="785e4-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="785e4-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="785e4-127">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="785e4-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="785e4-128">Hardwaregerät zum Lastenausgleich des veröffentlichten Dialin-Webdiensts vom Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="785e4-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="785e4-129">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="785e4-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="785e4-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="785e4-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="785e4-131">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="785e4-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="785e4-132">Hardwaregerät zum Lastenausgleich des veröffentlichten Besprechungs-Webdiensts vom Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="785e4-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="785e4-133">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="785e4-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="785e4-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="785e4-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="785e4-135">Directorpool-HLB-VIP</span><span class="sxs-lookup"><span data-stu-id="785e4-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="785e4-136">Von den externen Webticket-Webdiensten des Reverseproxy mit Hardwarelastenausgleich veröffentlichter und definierter Reverseproxy für den Directorpool</span><span class="sxs-lookup"><span data-stu-id="785e4-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

