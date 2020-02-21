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
ms.openlocfilehash: 6db93ea1b09e50d48ee5e0276d90e3db3975e9fe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="57151-102">ErrorDef-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57151-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57151-103">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="57151-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="57151-104">In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die möglicherweise auftreten.</span><span class="sxs-lookup"><span data-stu-id="57151-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="57151-105">Jeder Datensatz ist eine Art von Fehler.</span><span class="sxs-lookup"><span data-stu-id="57151-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57151-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="57151-106">Column</span></span></th>
<th><span data-ttu-id="57151-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="57151-107">Data Type</span></span></th>
<th><span data-ttu-id="57151-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="57151-108">Key/Index</span></span></th>
<th><span data-ttu-id="57151-109">Details</span><span class="sxs-lookup"><span data-stu-id="57151-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57151-110"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="57151-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="57151-111">int</span><span class="sxs-lookup"><span data-stu-id="57151-111">int</span></span></p></td>
<td><p><span data-ttu-id="57151-112">Primary</span><span class="sxs-lookup"><span data-stu-id="57151-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="57151-113">Eindeutige ID-Nummer, die diese Art von Fehler identifiziert.</span><span class="sxs-lookup"><span data-stu-id="57151-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57151-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="57151-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="57151-115">int</span><span class="sxs-lookup"><span data-stu-id="57151-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="57151-116">Standard mäßiger SIP-Antwortcode, der diesem Fehler zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="57151-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57151-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="57151-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="57151-118">int</span><span class="sxs-lookup"><span data-stu-id="57151-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="57151-119">Microsoft-Diagnose-ID.</span><span class="sxs-lookup"><span data-stu-id="57151-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57151-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="57151-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="57151-121">Int</span><span class="sxs-lookup"><span data-stu-id="57151-121">Int</span></span></p></td>
<td><p><span data-ttu-id="57151-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="57151-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="57151-123">Der Typ des Anrufs.</span><span class="sxs-lookup"><span data-stu-id="57151-123">Type of the call.</span></span> <span data-ttu-id="57151-124">Weitere Informationen finden Sie <a href="lync-server-2013-calltype-table.md">in der CallType-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="57151-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57151-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="57151-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="57151-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="57151-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="57151-127">Der Typ der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="57151-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="57151-128">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="57151-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57151-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="57151-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="57151-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="57151-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="57151-131">Der Inhaltstyp der fehlgeschlagenen Anforderung.</span><span class="sxs-lookup"><span data-stu-id="57151-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="57151-132">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="57151-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

