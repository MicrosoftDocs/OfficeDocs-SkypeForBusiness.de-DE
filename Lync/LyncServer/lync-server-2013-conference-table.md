---
title: 'Lync Server 2013: Konferenz Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7b6627f6976001bdb1440db9aa40c33d89cfc7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="38931-102">Konferenz Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38931-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38931-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="38931-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="38931-p101">Bei der Conference-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="38931-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38931-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="38931-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="38931-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="38931-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="38931-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="38931-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="38931-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="38931-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38931-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="38931-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="38931-111">int</span><span class="sxs-lookup"><span data-stu-id="38931-111">int</span></span></p></td>
<td><p><span data-ttu-id="38931-112">Primary</span><span class="sxs-lookup"><span data-stu-id="38931-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="38931-113">Eindeutige Zahl, die diesen Konferenzdatensatz identifiziert.</span><span class="sxs-lookup"><span data-stu-id="38931-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38931-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="38931-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="38931-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="38931-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="38931-116">eindeutige</span><span class="sxs-lookup"><span data-stu-id="38931-116">unique</span></span></p></td>
<td><p><span data-ttu-id="38931-117">Konferenz-URI, falls dies eine Konferenz ist, oder Dialogkennung, wenn dies eine Peer-zu-Peer-Sitzung ist.</span><span class="sxs-lookup"><span data-stu-id="38931-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38931-118"><strong>Prüfsumme</strong></span><span class="sxs-lookup"><span data-stu-id="38931-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="38931-119">int</span><span class="sxs-lookup"><span data-stu-id="38931-119">int</span></span></p></td>
<td><p><span data-ttu-id="38931-120">Index</span><span class="sxs-lookup"><span data-stu-id="38931-120">index</span></span></p></td>
<td><p><span data-ttu-id="38931-p102">Prüfsumme der Konferenz-URI. Für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="38931-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38931-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="38931-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="38931-124">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="38931-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38931-125">Ausschließlich für interne Zwecke.</span><span class="sxs-lookup"><span data-stu-id="38931-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

