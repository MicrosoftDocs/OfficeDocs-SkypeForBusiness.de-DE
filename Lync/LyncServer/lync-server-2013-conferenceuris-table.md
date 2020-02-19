---
title: 'Lync Server 2013: ConferenceUris-Tabelle'
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
ms.openlocfilehash: b2215eb030f237e8d238310e6f6b7fe223088c02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="68a45-102">ConferenceUris-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a45-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68a45-103">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="68a45-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="68a45-p101">Bei der ConferenceUris-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Konferenz-URIs gespeichert, die an in der Datenbank aufgezeichneten Konferenzsitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="68a45-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68a45-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="68a45-106">Column</span></span></th>
<th><span data-ttu-id="68a45-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="68a45-107">Data Type</span></span></th>
<th><span data-ttu-id="68a45-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="68a45-108">Key/Index</span></span></th>
<th><span data-ttu-id="68a45-109">Details</span><span class="sxs-lookup"><span data-stu-id="68a45-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68a45-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="68a45-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="68a45-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="68a45-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="68a45-112">Primary</span><span class="sxs-lookup"><span data-stu-id="68a45-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="68a45-113">Zeitstempel; zu internen Zwecken.</span><span class="sxs-lookup"><span data-stu-id="68a45-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68a45-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="68a45-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="68a45-115">int</span><span class="sxs-lookup"><span data-stu-id="68a45-115">int</span></span></p></td>
<td><p><span data-ttu-id="68a45-116">Primary</span><span class="sxs-lookup"><span data-stu-id="68a45-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="68a45-117">Eindeutige Zahl, die diesen Konferenz-URI identifiziert.</span><span class="sxs-lookup"><span data-stu-id="68a45-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68a45-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="68a45-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="68a45-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="68a45-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68a45-120">Konferenz-URI</span><span class="sxs-lookup"><span data-stu-id="68a45-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68a45-121"><strong>Prüfsumme</strong></span><span class="sxs-lookup"><span data-stu-id="68a45-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="68a45-122">int</span><span class="sxs-lookup"><span data-stu-id="68a45-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68a45-p102">Prüfsumme von ConferenceUri. Wird verwendet, um die Geschwindigkeit von Datenbanksuchvorgängen zu steigern.</span><span class="sxs-lookup"><span data-stu-id="68a45-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68a45-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="68a45-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="68a45-126">int</span><span class="sxs-lookup"><span data-stu-id="68a45-126">int</span></span></p></td>
<td><p><span data-ttu-id="68a45-127">Fremd</span><span class="sxs-lookup"><span data-stu-id="68a45-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="68a45-128">URI-Typ, beispielsweise conf: Chat für Sofortnachrichtenkonferenz oder conf: Audio-Video für Audio/Videokonferenz.</span><span class="sxs-lookup"><span data-stu-id="68a45-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="68a45-129">Weitere Informationen finden Sie in der Tabelle <a href="lync-server-2013-uritypes-table.md">UriTypes in lync Server 2013</a> Tabelle.</span><span class="sxs-lookup"><span data-stu-id="68a45-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

