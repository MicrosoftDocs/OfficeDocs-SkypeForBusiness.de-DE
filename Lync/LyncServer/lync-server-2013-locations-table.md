---
title: 'Lync Server 2013: Locations-Tabelle'
description: 'Lync Server 2013: Locations-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570581"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="b42a9-103">Tabelle "Locations" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b42a9-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b42a9-104">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="b42a9-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="b42a9-105">Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z. B. ein E9-1-1-Anruf) dar.</span><span class="sxs-lookup"><span data-stu-id="b42a9-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b42a9-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="b42a9-106">Column</span></span></th>
<th><span data-ttu-id="b42a9-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b42a9-107">Data Type</span></span></th>
<th><span data-ttu-id="b42a9-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="b42a9-108">Key/Index</span></span></th>
<th><span data-ttu-id="b42a9-109">Details</span><span class="sxs-lookup"><span data-stu-id="b42a9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b42a9-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="b42a9-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b42a9-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b42a9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b42a9-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="b42a9-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b42a9-113">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="b42a9-113">Time of session request.</span></span> <span data-ttu-id="b42a9-114">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b42a9-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b42a9-115">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b42a9-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b42a9-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b42a9-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b42a9-117">int</span><span class="sxs-lookup"><span data-stu-id="b42a9-117">int</span></span></p></td>
<td><p><span data-ttu-id="b42a9-118">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="b42a9-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b42a9-119">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b42a9-119">ID number to identify the session.</span></span> <span data-ttu-id="b42a9-120">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b42a9-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b42a9-121">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b42a9-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b42a9-122"><strong>Ort</strong></span><span class="sxs-lookup"><span data-stu-id="b42a9-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="b42a9-123">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="b42a9-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b42a9-124">Standort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="b42a9-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

