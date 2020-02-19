---
title: 'Lync Server 2013: CallPriorities-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d8d8a905fd34cecd77195fa9b824a5319778870
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="42954-102">CallPriorities-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42954-102">CallPriorities table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42954-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="42954-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="42954-104">Die CallPriorities-Tabelle ist eine statische Tabelle, in der die Liste der möglichen Aufrufprioritäten wie "emergency", "urgent" oder "normal" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="42954-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42954-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="42954-105">Column</span></span></th>
<th><span data-ttu-id="42954-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="42954-106">Data Type</span></span></th>
<th><span data-ttu-id="42954-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="42954-107">Key/Index</span></span></th>
<th><span data-ttu-id="42954-108">Details</span><span class="sxs-lookup"><span data-stu-id="42954-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42954-109"><strong>Prioritäts-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="42954-109"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="42954-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="42954-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="42954-111">Primary</span><span class="sxs-lookup"><span data-stu-id="42954-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42954-112"><strong>Priority</strong></span><span class="sxs-lookup"><span data-stu-id="42954-112"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="42954-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42954-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42954-114">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="42954-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="42954-115">0 – Unbekannt</span><span class="sxs-lookup"><span data-stu-id="42954-115">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="42954-116">1 – Nicht dringend</span><span class="sxs-lookup"><span data-stu-id="42954-116">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="42954-117">2 – Normal</span><span class="sxs-lookup"><span data-stu-id="42954-117">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="42954-118">3 – Dringend</span><span class="sxs-lookup"><span data-stu-id="42954-118">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="42954-119">4 – Notfall</span><span class="sxs-lookup"><span data-stu-id="42954-119">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

