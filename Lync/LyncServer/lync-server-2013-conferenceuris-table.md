---
title: 'Lync Server 2013: ConferenceUris-Tabelle'
description: 'Lync Server 2013: ConferenceUris-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566741"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="4fb90-103">ConferenceUris-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb90-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fb90-104">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="4fb90-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="4fb90-p101">Bei der ConferenceUris-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Konferenz-URIs gespeichert, die an in der Datenbank aufgezeichneten Konferenzsitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="4fb90-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4fb90-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="4fb90-107">Column</span></span></th>
<th><span data-ttu-id="4fb90-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4fb90-108">Data Type</span></span></th>
<th><span data-ttu-id="4fb90-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="4fb90-109">Key/Index</span></span></th>
<th><span data-ttu-id="4fb90-110">Details</span><span class="sxs-lookup"><span data-stu-id="4fb90-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fb90-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4fb90-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4fb90-112">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="4fb90-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4fb90-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4fb90-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4fb90-114">Zeitstempel; zu internen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="4fb90-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fb90-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4fb90-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4fb90-116">int</span><span class="sxs-lookup"><span data-stu-id="4fb90-116">int</span></span></p></td>
<td><p><span data-ttu-id="4fb90-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4fb90-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4fb90-118">Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4fb90-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fb90-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="4fb90-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4fb90-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4fb90-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fb90-121">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="4fb90-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fb90-122"><strong>Prüfsumme</strong></span><span class="sxs-lookup"><span data-stu-id="4fb90-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="4fb90-123">int</span><span class="sxs-lookup"><span data-stu-id="4fb90-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4fb90-p102">Prüfsumme von ConferenceUri. Wird verwendet, um die Geschwindigkeit von Datenbanksuchvorgängen zu steigern.</span><span class="sxs-lookup"><span data-stu-id="4fb90-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fb90-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4fb90-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4fb90-127">int</span><span class="sxs-lookup"><span data-stu-id="4fb90-127">int</span></span></p></td>
<td><p><span data-ttu-id="4fb90-128">Fremd</span><span class="sxs-lookup"><span data-stu-id="4fb90-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4fb90-129">URI-Typ, beispielsweise conf: Chat für Sofortnachrichtenkonferenz oder conf: Audio-Video für Audio/Videokonferenz.</span><span class="sxs-lookup"><span data-stu-id="4fb90-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="4fb90-130">Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-uritypes-table.md">UriTypes in lync Server 2013</a> Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fb90-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

