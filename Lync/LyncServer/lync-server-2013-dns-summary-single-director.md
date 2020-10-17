---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen einzelnen Director'
description: 'Lync Server 2013: DNS-Zusammenfassung – einzelner Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553231"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="03a5d-103">DNS-Zusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03a5d-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03a5d-104">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="03a5d-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="03a5d-105">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des einzelnen Directors erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="03a5d-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="03a5d-106">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="03a5d-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="03a5d-107">Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert.</span><span class="sxs-lookup"><span data-stu-id="03a5d-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="03a5d-108">Anders als die Front-End-Server, hostet der Director keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="03a5d-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="03a5d-109">Für den Director erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="03a5d-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03a5d-110">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="03a5d-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="03a5d-111">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="03a5d-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="03a5d-112">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="03a5d-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="03a5d-113">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="03a5d-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03a5d-114">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="03a5d-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="03a5d-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="03a5d-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="03a5d-116">Director</span><span class="sxs-lookup"><span data-stu-id="03a5d-116">Director</span></span></p></td>
<td><p><span data-ttu-id="03a5d-117">Director-Hosteintrag für Replikation und Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="03a5d-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03a5d-118">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="03a5d-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="03a5d-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03a5d-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03a5d-120">Director</span><span class="sxs-lookup"><span data-stu-id="03a5d-120">Director</span></span></p></td>
<td><p><span data-ttu-id="03a5d-121">SIP (Inbound Session Initiation Protocol) von der internen Edge-Schnittstelle des Edgeserver</span><span class="sxs-lookup"><span data-stu-id="03a5d-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03a5d-122">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="03a5d-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="03a5d-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03a5d-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03a5d-124">Director</span><span class="sxs-lookup"><span data-stu-id="03a5d-124">Director</span></span></p></td>
<td><p><span data-ttu-id="03a5d-125">Veröffentlichte Dialin-Webdienste vom Reverseproxyserver</span><span class="sxs-lookup"><span data-stu-id="03a5d-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03a5d-126">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="03a5d-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="03a5d-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03a5d-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03a5d-128">Director</span><span class="sxs-lookup"><span data-stu-id="03a5d-128">Director</span></span></p></td>
<td><p><span data-ttu-id="03a5d-129">Veröffentlichte Meet-Webdienste vom Reverseproxyserver</span><span class="sxs-lookup"><span data-stu-id="03a5d-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03a5d-130">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="03a5d-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="03a5d-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03a5d-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="03a5d-132">Director</span><span class="sxs-lookup"><span data-stu-id="03a5d-132">Director</span></span></p></td>
<td><p><span data-ttu-id="03a5d-133">Veröffentlicht und definiert durch das Reverse-Proxy-WebTICKET externe Webdienste für den Director</span><span class="sxs-lookup"><span data-stu-id="03a5d-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

