---
title: 'Lync Server 2013: Filetransfers-Tabelle'
description: 'Lync Server 2013: Filetransfers-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573361"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="e994e-103">Filetransfers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e994e-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e994e-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e994e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e994e-105">Jeder Datensatz steht für eine Dateiübertragungssitzung.</span><span class="sxs-lookup"><span data-stu-id="e994e-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e994e-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="e994e-106">Column</span></span></th>
<th><span data-ttu-id="e994e-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e994e-107">Data Type</span></span></th>
<th><span data-ttu-id="e994e-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="e994e-108">Key/Index</span></span></th>
<th><span data-ttu-id="e994e-109">Details</span><span class="sxs-lookup"><span data-stu-id="e994e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e994e-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="e994e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e994e-112">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e994e-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e994e-113">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e994e-113">Time of session request.</span></span> <span data-ttu-id="e994e-114">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e994e-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e994e-115">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e994e-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e994e-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-117">int</span><span class="sxs-lookup"><span data-stu-id="e994e-117">int</span></span></p></td>
<td><p><span data-ttu-id="e994e-118">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e994e-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e994e-119">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e994e-119">ID number to identify the session.</span></span> <span data-ttu-id="e994e-120">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e994e-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e994e-121">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e994e-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e994e-122"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e994e-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e994e-124">Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="e994e-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e994e-125"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-126">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e994e-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e994e-127">Eindeutige ID zum Unterscheiden zwischen Dateiübertragungen mit dem gleichen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="e994e-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e994e-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-129">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="e994e-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e994e-130">Primary</span><span class="sxs-lookup"><span data-stu-id="e994e-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="e994e-131">Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="e994e-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e994e-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-133">Bit</span><span class="sxs-lookup"><span data-stu-id="e994e-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e994e-p103">Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="e994e-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e994e-136"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-137">Bit</span><span class="sxs-lookup"><span data-stu-id="e994e-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e994e-p104">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="e994e-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e994e-140"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="e994e-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="e994e-141">Bit</span><span class="sxs-lookup"><span data-stu-id="e994e-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e994e-p105">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="e994e-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

