---
title: 'Lync Server 2013: ErrorDef-Tabelle'
description: 'Lync Server 2013: ErrorDef-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542751"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="805ae-103">ErrorDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805ae-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="805ae-104">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="805ae-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="805ae-105">In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die möglicherweise auftreten.</span><span class="sxs-lookup"><span data-stu-id="805ae-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="805ae-106">Jeder Datensatz ist eine Art von Fehler.</span><span class="sxs-lookup"><span data-stu-id="805ae-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="805ae-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="805ae-107">Column</span></span></th>
<th><span data-ttu-id="805ae-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="805ae-108">Data Type</span></span></th>
<th><span data-ttu-id="805ae-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="805ae-109">Key/Index</span></span></th>
<th><span data-ttu-id="805ae-110">Details</span><span class="sxs-lookup"><span data-stu-id="805ae-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="805ae-111"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="805ae-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="805ae-112">int</span><span class="sxs-lookup"><span data-stu-id="805ae-112">int</span></span></p></td>
<td><p><span data-ttu-id="805ae-113">Primary</span><span class="sxs-lookup"><span data-stu-id="805ae-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="805ae-114">Eindeutige ID-Nummer, die diese Art von Fehler identifiziert.</span><span class="sxs-lookup"><span data-stu-id="805ae-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="805ae-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="805ae-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="805ae-116">int</span><span class="sxs-lookup"><span data-stu-id="805ae-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="805ae-117">Standard mäßiger SIP-Antwortcode, der diesem Fehler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="805ae-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="805ae-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="805ae-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="805ae-119">int</span><span class="sxs-lookup"><span data-stu-id="805ae-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="805ae-120">Microsoft-Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="805ae-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="805ae-121"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="805ae-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="805ae-122">Int</span><span class="sxs-lookup"><span data-stu-id="805ae-122">Int</span></span></p></td>
<td><p><span data-ttu-id="805ae-123">Fremd</span><span class="sxs-lookup"><span data-stu-id="805ae-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="805ae-124">Der Typ des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="805ae-124">Type of the call.</span></span> <span data-ttu-id="805ae-125">Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der CallType-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="805ae-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="805ae-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="805ae-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="805ae-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="805ae-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="805ae-128">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="805ae-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="805ae-129">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="805ae-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="805ae-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="805ae-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="805ae-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="805ae-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="805ae-132">Der Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="805ae-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="805ae-133">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="805ae-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

