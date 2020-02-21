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
ms.openlocfilehash: 3052aa95aa6cd846717aa98c5778531aeee6f7e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="ada56-102">ErrorCategory-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ada56-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ada56-103">_**Letztes Änderungsstand des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="ada56-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="ada56-104">Die ErrorCategory-Tabelle enthält den Anzeigenamen für jede Microsoft lync Server 2013 Diagnose Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="ada56-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="ada56-105">Standardmäßig verwendet lync Server 2013 die folgenden Klassifizierungen:</span><span class="sxs-lookup"><span data-stu-id="ada56-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="ada56-106">0--Success</span><span class="sxs-lookup"><span data-stu-id="ada56-106">0 -- Success</span></span>

  - <span data-ttu-id="ada56-107">1 – Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="ada56-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="ada56-108">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="ada56-108">2 – Unexpected failure</span></span>

<span data-ttu-id="ada56-109">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ada56-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ada56-110">Spalte</span><span class="sxs-lookup"><span data-stu-id="ada56-110">Column</span></span></th>
<th><span data-ttu-id="ada56-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ada56-111">Data Type</span></span></th>
<th><span data-ttu-id="ada56-112">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="ada56-112">Key/Index</span></span></th>
<th><span data-ttu-id="ada56-113">Details</span><span class="sxs-lookup"><span data-stu-id="ada56-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ada56-114"><strong>CategoryID</strong></span><span class="sxs-lookup"><span data-stu-id="ada56-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="ada56-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="ada56-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ada56-116">Primary</span><span class="sxs-lookup"><span data-stu-id="ada56-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ada56-117">Eindeutige ID für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="ada56-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ada56-118"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="ada56-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ada56-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ada56-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ada56-120">Wert und Anzeigename, der der Klassifizierung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ada56-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="ada56-121">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ada56-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ada56-122">0--Success</span><span class="sxs-lookup"><span data-stu-id="ada56-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="ada56-123">1 – Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="ada56-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="ada56-124">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="ada56-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

