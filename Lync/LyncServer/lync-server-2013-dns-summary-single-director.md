---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen einzelnen Director'
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
ms.openlocfilehash: d1eaaebf1fb695bc1ee6ea1b86f980a666cf0a70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515532"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8ac30-102">DNS-Zusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ac30-102">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac30-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8ac30-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8ac30-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des einzelnen Directors erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8ac30-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="8ac30-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="8ac30-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="8ac30-106">Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert.</span><span class="sxs-lookup"><span data-stu-id="8ac30-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="8ac30-107">Anders als die Front-End-Server, hostet der Director keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="8ac30-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="8ac30-108">Für den Director erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="8ac30-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ac30-109">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="8ac30-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8ac30-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="8ac30-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="8ac30-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="8ac30-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="8ac30-112">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="8ac30-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ac30-113">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ac30-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ac30-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8ac30-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8ac30-115">Director</span><span class="sxs-lookup"><span data-stu-id="8ac30-115">Director</span></span></p></td>
<td><p><span data-ttu-id="8ac30-116">Director-Hosteintrag für Replikation und Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="8ac30-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac30-117">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ac30-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ac30-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ac30-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ac30-119">Director</span><span class="sxs-lookup"><span data-stu-id="8ac30-119">Director</span></span></p></td>
<td><p><span data-ttu-id="8ac30-120">SIP (Inbound Session Initiation Protocol) von der internen Edge-Schnittstelle des Edgeserver</span><span class="sxs-lookup"><span data-stu-id="8ac30-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac30-121">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ac30-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ac30-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ac30-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ac30-123">Director</span><span class="sxs-lookup"><span data-stu-id="8ac30-123">Director</span></span></p></td>
<td><p><span data-ttu-id="8ac30-124">Veröffentlichte Dialin-Webdienste vom Reverseproxyserver</span><span class="sxs-lookup"><span data-stu-id="8ac30-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac30-125">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ac30-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ac30-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ac30-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ac30-127">Director</span><span class="sxs-lookup"><span data-stu-id="8ac30-127">Director</span></span></p></td>
<td><p><span data-ttu-id="8ac30-128">Veröffentlichte Meet-Webdienste vom Reverseproxyserver</span><span class="sxs-lookup"><span data-stu-id="8ac30-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac30-129">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ac30-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ac30-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ac30-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ac30-131">Director</span><span class="sxs-lookup"><span data-stu-id="8ac30-131">Director</span></span></p></td>
<td><p><span data-ttu-id="8ac30-132">Veröffentlicht und definiert durch das Reverse-Proxy-WebTICKET externe Webdienste für den Director</span><span class="sxs-lookup"><span data-stu-id="8ac30-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

