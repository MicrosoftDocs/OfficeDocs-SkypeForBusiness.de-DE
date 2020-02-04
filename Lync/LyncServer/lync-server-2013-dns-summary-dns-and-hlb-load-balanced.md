---
title: 'Lync Server 2013: DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich'
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
ms.openlocfilehash: c5b84ccab2b3074662016a19c5f0a51d0cb70405
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="1a906-102">DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a906-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a906-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1a906-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1a906-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die erforderlich sind, um den Director für DNS-Lastenausgleich und Hardwarelastenausgleich zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1a906-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="1a906-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie der Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="1a906-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="1a906-106">Die Anzahl der benötigten Datensätze wird in den für das Director-Zertifikat erforderlichen Alternativen Betreff-Namen widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="1a906-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="1a906-107">Anders als der Front-End-Server hostet der Director-Pool keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="1a906-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="1a906-108">Für den Director-Pool erforderliche DNS-Einträge mithilfe des DNS-Lastenausgleichs und des Hardware Lastenausgleichs</span><span class="sxs-lookup"><span data-stu-id="1a906-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a906-109">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="1a906-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1a906-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="1a906-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1a906-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="1a906-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1a906-112">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="1a906-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a906-113">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="1a906-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1a906-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1a906-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1a906-115">Director</span><span class="sxs-lookup"><span data-stu-id="1a906-115">Director</span></span></p></td>
<td><p><span data-ttu-id="1a906-116">Director-Hosteintrag für Replikation und Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="1a906-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a906-117">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="1a906-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1a906-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1a906-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1a906-119">Directorpool</span><span class="sxs-lookup"><span data-stu-id="1a906-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="1a906-120">Host-Eintrag für den DNS Load Balancing Director-Pool für Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="1a906-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a906-121">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="1a906-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1a906-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a906-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1a906-123">Directorpool</span><span class="sxs-lookup"><span data-stu-id="1a906-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="1a906-124">SIP (Inbound Session Initiation Protocol) von der internen Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="1a906-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a906-125">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="1a906-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1a906-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a906-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1a906-127">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1a906-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1a906-128">Hardware Load Balanced veröffentlichte Dialin-Webdienste vom Reverse-Proxy</span><span class="sxs-lookup"><span data-stu-id="1a906-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a906-129">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="1a906-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1a906-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a906-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1a906-131">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1a906-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1a906-132">Hardware Load Balanced veröffentlicht Meet Web Services from Reverse Proxy</span><span class="sxs-lookup"><span data-stu-id="1a906-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a906-133">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="1a906-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1a906-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a906-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1a906-135">Director Pool HLB VIP</span><span class="sxs-lookup"><span data-stu-id="1a906-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1a906-136">Vom Reverse Proxy Web-Ticket externe Webdienste für den Director-Pool veröffentlichte und definierte Hardware Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="1a906-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

