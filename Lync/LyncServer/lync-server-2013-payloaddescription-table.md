---
title: 'Lync Server 2013: PayloadDescription-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c49e8acab38237b3d2f79ce3cc1838a5b204ae65
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="aae69-102">PayloadDescription-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aae69-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aae69-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="aae69-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="aae69-p101">Bei der PayloadDescription-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für einen Codec, der in einer Audio- oder Videositzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aae69-p101">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aae69-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="aae69-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="aae69-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="aae69-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="aae69-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="aae69-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="aae69-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="aae69-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aae69-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="aae69-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="aae69-111">int</span><span class="sxs-lookup"><span data-stu-id="aae69-111">int</span></span></p></td>
<td><p><span data-ttu-id="aae69-112">Primary</span><span class="sxs-lookup"><span data-stu-id="aae69-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="aae69-113">Eindeutige Zahl, die den Codec identifiziert.</span><span class="sxs-lookup"><span data-stu-id="aae69-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae69-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="aae69-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="aae69-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aae69-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aae69-116">Eigen</span><span class="sxs-lookup"><span data-stu-id="aae69-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="aae69-117">Name des Codecs.</span><span class="sxs-lookup"><span data-stu-id="aae69-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

