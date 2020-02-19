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
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="b14d1-102">DNS-Zusammenfassung für einen einzelnen Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b14d1-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b14d1-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b14d1-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b14d1-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die zur Unterstützung des einzelnen Directors erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b14d1-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="b14d1-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie die Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b14d1-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="b14d1-106">Die erforderliche Anzahl von Datensätzen wird in den für das Director-Zertifikat erforderlichen alternativen Antragstellernamen reflektiert.</span><span class="sxs-lookup"><span data-stu-id="b14d1-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="b14d1-107">Anders als die Front-End-Server, hostet der Director keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="b14d1-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="b14d1-108">Für den Director erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="b14d1-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b14d1-109">Standort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="b14d1-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b14d1-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="b14d1-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="b14d1-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="b14d1-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="b14d1-112">Zugeordnet zu/Kommentar</span><span class="sxs-lookup"><span data-stu-id="b14d1-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b14d1-113">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="b14d1-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b14d1-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b14d1-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b14d1-115">Director</span><span class="sxs-lookup"><span data-stu-id="b14d1-115">Director</span></span></p></td>
<td><p><span data-ttu-id="b14d1-116">Director-Hosteintrag für Replikation und Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="b14d1-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14d1-117">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="b14d1-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b14d1-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b14d1-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b14d1-119">Director</span><span class="sxs-lookup"><span data-stu-id="b14d1-119">Director</span></span></p></td>
<td><p><span data-ttu-id="b14d1-120">SIP (Inbound Session Initiation Protocol) von der internen Edge-Schnittstelle des Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b14d1-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b14d1-121">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="b14d1-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b14d1-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b14d1-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b14d1-123">Director</span><span class="sxs-lookup"><span data-stu-id="b14d1-123">Director</span></span></p></td>
<td><p><span data-ttu-id="b14d1-124">Veröffentlichte Dialin-Webdienste vom Reverseproxyserver</span><span class="sxs-lookup"><span data-stu-id="b14d1-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14d1-125">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="b14d1-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b14d1-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b14d1-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b14d1-127">Director</span><span class="sxs-lookup"><span data-stu-id="b14d1-127">Director</span></span></p></td>
<td><p><span data-ttu-id="b14d1-128">Veröffentlichte Meet-Webdienste vom Reverseproxyserver</span><span class="sxs-lookup"><span data-stu-id="b14d1-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b14d1-129">Interne DNS/A</span><span class="sxs-lookup"><span data-stu-id="b14d1-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b14d1-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b14d1-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b14d1-131">Director</span><span class="sxs-lookup"><span data-stu-id="b14d1-131">Director</span></span></p></td>
<td><p><span data-ttu-id="b14d1-132">Veröffentlicht und definiert durch das Reverse-Proxy-WebTICKET externe Webdienste für den Director</span><span class="sxs-lookup"><span data-stu-id="b14d1-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

