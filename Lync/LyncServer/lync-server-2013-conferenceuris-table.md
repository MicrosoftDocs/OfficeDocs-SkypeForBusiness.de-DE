---
title: 'Lync Server 2013: ConferenceUris-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="46a9d-102">ConferenceUris-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46a9d-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46a9d-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="46a9d-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="46a9d-104">Die Tabelle ConfereneUris ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Konferenz-URIs gespeichert ist, die an Konferenzsitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="46a9d-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="46a9d-105">Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="46a9d-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46a9d-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="46a9d-106">Column</span></span></th>
<th><span data-ttu-id="46a9d-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="46a9d-107">Data Type</span></span></th>
<th><span data-ttu-id="46a9d-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="46a9d-108">Key/Index</span></span></th>
<th><span data-ttu-id="46a9d-109">Details</span><span class="sxs-lookup"><span data-stu-id="46a9d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46a9d-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="46a9d-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="46a9d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="46a9d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="46a9d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="46a9d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="46a9d-113">Zeitstempel, intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="46a9d-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46a9d-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="46a9d-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="46a9d-115">int</span><span class="sxs-lookup"><span data-stu-id="46a9d-115">int</span></span></p></td>
<td><p><span data-ttu-id="46a9d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="46a9d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="46a9d-117">Eindeutige Nummer, die diesen Konferenz-URI kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="46a9d-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46a9d-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="46a9d-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="46a9d-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="46a9d-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="46a9d-120">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="46a9d-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46a9d-121"><strong>Prüfsumme</strong></span><span class="sxs-lookup"><span data-stu-id="46a9d-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="46a9d-122">int</span><span class="sxs-lookup"><span data-stu-id="46a9d-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="46a9d-123">Prüfsumme von ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="46a9d-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="46a9d-124">Wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="46a9d-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46a9d-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="46a9d-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="46a9d-126">int</span><span class="sxs-lookup"><span data-stu-id="46a9d-126">int</span></span></p></td>
<td><p><span data-ttu-id="46a9d-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="46a9d-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="46a9d-128">URI-Typ wie conf: Chat für im-Konferenz oder conf: Audio-Video für Audio/Video-Konferenz.</span><span class="sxs-lookup"><span data-stu-id="46a9d-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="46a9d-129">Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-uritypes-table.md">UriTypes in der lync Server 2013</a> -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="46a9d-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

