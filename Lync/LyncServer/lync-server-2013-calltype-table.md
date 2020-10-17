---
title: 'Lync Server 2013: CallType-Tabelle'
description: 'Lync Server 2013: CallType-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565171"
---
# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="6500f-103">CallType-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6500f-103">CallType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6500f-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6500f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6500f-105">Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6500f-105">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6500f-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="6500f-106">Column</span></span></th>
<th><span data-ttu-id="6500f-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6500f-107">Data Type</span></span></th>
<th><span data-ttu-id="6500f-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="6500f-108">Key/Index</span></span></th>
<th><span data-ttu-id="6500f-109">Details</span><span class="sxs-lookup"><span data-stu-id="6500f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6500f-110"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="6500f-110"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="6500f-111">int</span><span class="sxs-lookup"><span data-stu-id="6500f-111">int</span></span></p></td>
<td><p><span data-ttu-id="6500f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6500f-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6500f-113"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="6500f-113"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="6500f-114">nvarchar</span><span class="sxs-lookup"><span data-stu-id="6500f-114">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6500f-115">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="6500f-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="6500f-116">0 – Unbekannt</span><span class="sxs-lookup"><span data-stu-id="6500f-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="6500f-117">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="6500f-117">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="6500f-118">2--Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="6500f-118">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="6500f-119">3 – Audio</span><span class="sxs-lookup"><span data-stu-id="6500f-119">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="6500f-120">4 – Audio und Video</span><span class="sxs-lookup"><span data-stu-id="6500f-120">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="6500f-121">5 – Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="6500f-121">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

