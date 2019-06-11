---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen einzelnen Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca7fea825267dcdc5aa03a2e6c3c9fb3fc26a84b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="73c02-102">DNS-Zusammenfassung für einen einzelnen Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73c02-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73c02-103">_**Letztes Änderungsdatum des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="73c02-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="73c02-104">Die folgende Tabelle enthält eine Zusammenfassung der DNS-Einträge, die für die Unterstützung des einzelnen Directors erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="73c02-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="73c02-105">Die Rolle des Directors erfordert ähnliche DNS-Einträge wie der Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="73c02-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="73c02-106">Die Anzahl der benötigten Datensätze wird in den für das Director-Zertifikat erforderlichen Alternativen Betreff-Namen widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="73c02-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="73c02-107">Anders als der Front-End-Server hostet der Director keine Benutzerkonten oder hostet die Mobilitätsdienste.</span><span class="sxs-lookup"><span data-stu-id="73c02-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="73c02-108">Für den Director erforderliche DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="73c02-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73c02-109">Ort/Typ/Port</span><span class="sxs-lookup"><span data-stu-id="73c02-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="73c02-110">FQDN/DNS-Eintrag</span><span class="sxs-lookup"><span data-stu-id="73c02-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="73c02-111">IP-Adresse/FQDN</span><span class="sxs-lookup"><span data-stu-id="73c02-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="73c02-112">Karten/Kommentare</span><span class="sxs-lookup"><span data-stu-id="73c02-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73c02-113">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="73c02-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73c02-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="73c02-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="73c02-115">Director</span><span class="sxs-lookup"><span data-stu-id="73c02-115">Director</span></span></p></td>
<td><p><span data-ttu-id="73c02-116">Director-Hosteintrag für Replikation und Server-zu-Server</span><span class="sxs-lookup"><span data-stu-id="73c02-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73c02-117">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="73c02-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73c02-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73c02-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73c02-119">Director</span><span class="sxs-lookup"><span data-stu-id="73c02-119">Director</span></span></p></td>
<td><p><span data-ttu-id="73c02-120">SIP (Inbound Session Initiation Protocol) von der Schnittstelle des Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="73c02-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73c02-121">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="73c02-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73c02-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73c02-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73c02-123">Director</span><span class="sxs-lookup"><span data-stu-id="73c02-123">Director</span></span></p></td>
<td><p><span data-ttu-id="73c02-124">Veröffentlichte Dialin-Webdienste vom Reverse-Proxy</span><span class="sxs-lookup"><span data-stu-id="73c02-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73c02-125">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="73c02-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73c02-126">Meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73c02-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73c02-127">Director</span><span class="sxs-lookup"><span data-stu-id="73c02-127">Director</span></span></p></td>
<td><p><span data-ttu-id="73c02-128">Veröffentlicht Meet Web Services from Reverse Proxy</span><span class="sxs-lookup"><span data-stu-id="73c02-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73c02-129">Internes DNS/A</span><span class="sxs-lookup"><span data-stu-id="73c02-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="73c02-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="73c02-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="73c02-131">Director</span><span class="sxs-lookup"><span data-stu-id="73c02-131">Director</span></span></p></td>
<td><p><span data-ttu-id="73c02-132">Veröffentlicht und definiert vom Reverse Proxy Web-Ticket externe Webdienste für den Director</span><span class="sxs-lookup"><span data-stu-id="73c02-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

