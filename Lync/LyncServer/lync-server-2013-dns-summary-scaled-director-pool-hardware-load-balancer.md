---
title: 'Lync Server 2013: DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich)'
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
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="6190d-102">DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6190d-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6190d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6190d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6190d-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung des Directors Hardware Load Balanced erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6190d-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="6190d-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie der Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="6190d-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="6190d-106">Die Anzahl der benötigten Datensätze wird in den für das Director-Zertifikat erforderlichen Alternativen Betreff-Namen widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="6190d-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="6190d-107">Anders als der Front-End-Server hostet der Director-Pool keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="6190d-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="6190d-108">Für den Director-Pool erforderliche DNS-Einträge unter Verwendung eines Hardware Lastenausgleichs und des DNS-Lastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="6190d-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6190d-109">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="6190d-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="6190d-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="6190d-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="6190d-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="6190d-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="6190d-112">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="6190d-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6190d-113">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="6190d-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6190d-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6190d-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6190d-115">Director</span><span class="sxs-lookup"><span data-stu-id="6190d-115">Director</span></span></p></td>
<td><p><span data-ttu-id="6190d-116">Director-Hosteintrag für Replikation und Server-zu-Server-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="6190d-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6190d-117">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="6190d-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6190d-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6190d-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6190d-119">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="6190d-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="6190d-120">Host-Eintrag für den Director-Pool für DNS Load Balancing</span><span class="sxs-lookup"><span data-stu-id="6190d-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6190d-121">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="6190d-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6190d-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6190d-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6190d-123">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="6190d-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="6190d-124">SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="6190d-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6190d-125">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="6190d-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6190d-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6190d-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6190d-127">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="6190d-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="6190d-128">Hardware Load Balanced veröffentlichte Dialin-Webdienste vom Reverse-Proxy</span><span class="sxs-lookup"><span data-stu-id="6190d-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6190d-129">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="6190d-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6190d-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6190d-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6190d-131">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="6190d-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="6190d-132">Hardware Load Balanced veröffentlicht Meet Web Services from Reverse Proxy</span><span class="sxs-lookup"><span data-stu-id="6190d-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6190d-133">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="6190d-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="6190d-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6190d-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6190d-135">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="6190d-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="6190d-136">Vom Reverse Proxy Web-Ticket externe Webdienste für den Director-Pool veröffentlichte und definierte Hardware Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="6190d-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

