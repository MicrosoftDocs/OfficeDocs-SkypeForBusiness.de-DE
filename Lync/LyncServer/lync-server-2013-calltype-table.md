---
title: 'Lync Server 2013: CallType-Tabelle'
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
ms.openlocfilehash: 80e26d2d0db659a82159220fa3c8fa8f06a078f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="11130-102">CallType-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11130-102">CallType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11130-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="11130-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="11130-104">Die CallType-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Anruftypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="11130-104">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11130-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="11130-105">Column</span></span></th>
<th><span data-ttu-id="11130-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="11130-106">Data Type</span></span></th>
<th><span data-ttu-id="11130-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="11130-107">Key/Index</span></span></th>
<th><span data-ttu-id="11130-108">Details</span><span class="sxs-lookup"><span data-stu-id="11130-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11130-109"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="11130-109"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="11130-110">int</span><span class="sxs-lookup"><span data-stu-id="11130-110">int</span></span></p></td>
<td><p><span data-ttu-id="11130-111">Primary</span><span class="sxs-lookup"><span data-stu-id="11130-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11130-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="11130-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="11130-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="11130-113">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="11130-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="11130-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="11130-115">0 – Unbekannt</span><span class="sxs-lookup"><span data-stu-id="11130-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="11130-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="11130-116">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="11130-117">2--Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="11130-117">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="11130-118">3 – Audio</span><span class="sxs-lookup"><span data-stu-id="11130-118">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="11130-119">4 – Audio und Video</span><span class="sxs-lookup"><span data-stu-id="11130-119">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="11130-120">5 – Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="11130-120">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

