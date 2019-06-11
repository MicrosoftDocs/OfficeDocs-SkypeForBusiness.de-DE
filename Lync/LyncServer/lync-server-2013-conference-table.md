---
title: 'Lync Server 2013: Conference-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f57f7baf017507da44677cc475c99d192fe868f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="76986-102">Conference-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76986-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76986-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="76986-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="76986-104">Die Konferenz Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="76986-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="76986-105">Jeder Datensatz steht für eine Konferenz oder eine Peer-to-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="76986-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76986-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="76986-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="76986-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="76986-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="76986-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="76986-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="76986-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="76986-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76986-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="76986-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="76986-111">int</span><span class="sxs-lookup"><span data-stu-id="76986-111">int</span></span></p></td>
<td><p><span data-ttu-id="76986-112">Primary</span><span class="sxs-lookup"><span data-stu-id="76986-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="76986-113">Eindeutige Nummer, die diesen Konferenz Eintrag kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="76986-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76986-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="76986-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="76986-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="76986-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="76986-116">eindeutigen</span><span class="sxs-lookup"><span data-stu-id="76986-116">unique</span></span></p></td>
<td><p><span data-ttu-id="76986-117">Konferenz-URI, wenn es sich um eine Konferenz handelt, oder wenn es sich um eine Peer-to-Peer-Sitzung handelt.</span><span class="sxs-lookup"><span data-stu-id="76986-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76986-118"><strong>Prüfsumme</strong></span><span class="sxs-lookup"><span data-stu-id="76986-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="76986-119">int</span><span class="sxs-lookup"><span data-stu-id="76986-119">int</span></span></p></td>
<td><p><span data-ttu-id="76986-120">Index</span><span class="sxs-lookup"><span data-stu-id="76986-120">index</span></span></p></td>
<td><p><span data-ttu-id="76986-121">Die Prüfsumme des Konferenz-URIs.</span><span class="sxs-lookup"><span data-stu-id="76986-121">Checksum of the conference URI.</span></span> <span data-ttu-id="76986-122">Diese wird intern verwendet.</span><span class="sxs-lookup"><span data-stu-id="76986-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76986-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="76986-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="76986-124">datetime</span><span class="sxs-lookup"><span data-stu-id="76986-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76986-125">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="76986-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

