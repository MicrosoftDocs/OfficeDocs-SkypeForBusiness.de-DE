---
title: 'Lync Server 2013: FileTransfers-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e53e59e3ed1391adebff8b7c4046ef3c23aa21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="bae29-102">FileTransfers-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bae29-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bae29-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bae29-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bae29-104">Jeder Datensatz stellt eine Dateiübertragungssitzung dar.</span><span class="sxs-lookup"><span data-stu-id="bae29-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bae29-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="bae29-105">Column</span></span></th>
<th><span data-ttu-id="bae29-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="bae29-106">Data Type</span></span></th>
<th><span data-ttu-id="bae29-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="bae29-107">Key/Index</span></span></th>
<th><span data-ttu-id="bae29-108">Details</span><span class="sxs-lookup"><span data-stu-id="bae29-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bae29-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-110">datetime</span><span class="sxs-lookup"><span data-stu-id="bae29-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="bae29-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="bae29-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bae29-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="bae29-112">Time of session request.</span></span> <span data-ttu-id="bae29-113">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bae29-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bae29-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bae29-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae29-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-116">int</span><span class="sxs-lookup"><span data-stu-id="bae29-116">int</span></span></p></td>
<td><p><span data-ttu-id="bae29-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="bae29-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bae29-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bae29-118">ID number to identify the session.</span></span> <span data-ttu-id="bae29-119">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bae29-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bae29-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bae29-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae29-121"><strong>Dateiname</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bae29-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bae29-123">Der Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="bae29-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae29-124"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="bae29-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bae29-126">Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="bae29-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae29-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-128">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="bae29-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="bae29-129">Primary</span><span class="sxs-lookup"><span data-stu-id="bae29-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="bae29-130">Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bae29-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae29-131"><strong>Annehmen</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-132">bit</span><span class="sxs-lookup"><span data-stu-id="bae29-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bae29-133">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="bae29-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="bae29-134">Ist "true", ist "ablehnen" und "Abbrechen" NULL.</span><span class="sxs-lookup"><span data-stu-id="bae29-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae29-135"><strong>Ablehnen</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-136">bit</span><span class="sxs-lookup"><span data-stu-id="bae29-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bae29-137">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="bae29-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="bae29-138">Ist "true", ist "akzeptieren" und "Abbrechen" NULL.</span><span class="sxs-lookup"><span data-stu-id="bae29-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae29-139"><strong>Abbrechen</strong></span><span class="sxs-lookup"><span data-stu-id="bae29-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="bae29-140">bit</span><span class="sxs-lookup"><span data-stu-id="bae29-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bae29-141">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="bae29-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="bae29-142">Ist "true", ist "annehmen und ablehnen" NULL.</span><span class="sxs-lookup"><span data-stu-id="bae29-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

