---
title: 'Lync Server 2013: ErrorCategory-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f21535c1806223e7687ceb24ee94a93fe15238d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533152"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="bda83-102">ErrorCategory-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bda83-102">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bda83-103">_**Letztes Änderungsstand des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="bda83-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="bda83-104">Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Microsoft lync Server 2013 Diagnose Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="bda83-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="bda83-105">Standardmäßig verwendet lync Server 2013 die folgenden Klassifizierungen:</span><span class="sxs-lookup"><span data-stu-id="bda83-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="bda83-106">0--Success</span><span class="sxs-lookup"><span data-stu-id="bda83-106">0 -- Success</span></span>

  - <span data-ttu-id="bda83-107">1 – Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="bda83-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="bda83-108">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="bda83-108">2 – Unexpected failure</span></span>

<span data-ttu-id="bda83-109">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="bda83-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bda83-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="bda83-110">Column</span></span></th>
<th><span data-ttu-id="bda83-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="bda83-111">Data Type</span></span></th>
<th><span data-ttu-id="bda83-112">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="bda83-112">Key/Index</span></span></th>
<th><span data-ttu-id="bda83-113">Details</span><span class="sxs-lookup"><span data-stu-id="bda83-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bda83-114"><strong>CategoryID</strong></span><span class="sxs-lookup"><span data-stu-id="bda83-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="bda83-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="bda83-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bda83-116">Primary</span><span class="sxs-lookup"><span data-stu-id="bda83-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="bda83-117">Eindeutige ID für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="bda83-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bda83-118"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="bda83-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="bda83-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bda83-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bda83-120">Wert und Anzeigename, der der Klassifizierung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bda83-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="bda83-121">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="bda83-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bda83-122">0--Success</span><span class="sxs-lookup"><span data-stu-id="bda83-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="bda83-123">1 – Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="bda83-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="bda83-124">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="bda83-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

