---
title: 'Lync Server 2013: ErrorDef-Tabelle'
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
ms.openlocfilehash: 55a6ab9a8bf50639267824c8330701ee74cb3f5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="4c5b3-102">ErrorDef-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c5b3-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c5b3-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="4c5b3-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="4c5b3-104">In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="4c5b3-105">Jeder Datensatz ist eine Art von Fehler.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5b3-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="4c5b3-106">Column</span></span></th>
<th><span data-ttu-id="4c5b3-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4c5b3-107">Data Type</span></span></th>
<th><span data-ttu-id="4c5b3-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="4c5b3-108">Key/Index</span></span></th>
<th><span data-ttu-id="4c5b3-109">Details</span><span class="sxs-lookup"><span data-stu-id="4c5b3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5b3-110"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="4c5b3-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5b3-111">int</span><span class="sxs-lookup"><span data-stu-id="4c5b3-111">int</span></span></p></td>
<td><p><span data-ttu-id="4c5b3-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4c5b3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c5b3-113">Eindeutige ID-Nummer, die diese Art von Fehler kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5b3-114"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="4c5b3-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5b3-115">int</span><span class="sxs-lookup"><span data-stu-id="4c5b3-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c5b3-116">Standard mäßiger SIP-Antwortcode, der diesem Fehler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5b3-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5b3-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5b3-118">int</span><span class="sxs-lookup"><span data-stu-id="4c5b3-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c5b3-119">Microsoft-Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5b3-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4c5b3-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5b3-121">Int</span><span class="sxs-lookup"><span data-stu-id="4c5b3-121">Int</span></span></p></td>
<td><p><span data-ttu-id="4c5b3-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="4c5b3-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4c5b3-123">Der Typ des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-123">Type of the call.</span></span> <span data-ttu-id="4c5b3-124">Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der Tabelle "CallType" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4c5b3-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5b3-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="4c5b3-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5b3-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="4c5b3-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c5b3-127">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="4c5b3-128">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="4c5b3-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5b3-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="4c5b3-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5b3-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="4c5b3-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c5b3-131">Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="4c5b3-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="4c5b3-132">Diese Daten können mithilfe dieser Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="4c5b3-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

