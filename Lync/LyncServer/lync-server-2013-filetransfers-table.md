---
title: 'Lync Server 2013: Filetransfers-Tabelle'
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
ms.openlocfilehash: 3f98cb2ecafbc67bc4a2c231717d18a728363fe0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="12199-102">Filetransfers-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12199-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12199-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="12199-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="12199-104">Jeder Datensatz steht für eine Dateiübertragungssitzung.</span><span class="sxs-lookup"><span data-stu-id="12199-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12199-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="12199-105">Column</span></span></th>
<th><span data-ttu-id="12199-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="12199-106">Data Type</span></span></th>
<th><span data-ttu-id="12199-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="12199-107">Key/Index</span></span></th>
<th><span data-ttu-id="12199-108">Details</span><span class="sxs-lookup"><span data-stu-id="12199-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12199-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="12199-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="12199-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="12199-111">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="12199-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="12199-112">Zeitpunkt der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="12199-112">Time of session request.</span></span> <span data-ttu-id="12199-113">Wird zusammen mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="12199-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="12199-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="12199-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12199-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="12199-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-116">int</span><span class="sxs-lookup"><span data-stu-id="12199-116">int</span></span></p></td>
<td><p><span data-ttu-id="12199-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="12199-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="12199-118">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="12199-118">ID number to identify the session.</span></span> <span data-ttu-id="12199-119">Wird zusammen mit <strong>SessionIdTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="12199-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="12199-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle "Dialoge" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="12199-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12199-121"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="12199-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="12199-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12199-123">Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="12199-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12199-124"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="12199-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="12199-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12199-126">Eindeutige ID zum Unterscheiden zwischen Dateiübertragungen mit dem gleichen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="12199-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12199-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="12199-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-128">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="12199-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="12199-129">Primary</span><span class="sxs-lookup"><span data-stu-id="12199-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="12199-130">Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="12199-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12199-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="12199-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-132">Bit</span><span class="sxs-lookup"><span data-stu-id="12199-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12199-p103">Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="12199-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12199-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="12199-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-136">Bit</span><span class="sxs-lookup"><span data-stu-id="12199-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12199-p104">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="12199-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12199-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="12199-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="12199-140">Bit</span><span class="sxs-lookup"><span data-stu-id="12199-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12199-p105">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="12199-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

