---
title: 'Lync Server 2013: File Transfers-Ansicht'
description: 'Lync Server 2013: File Transfers-Ansicht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2b084274a4d5daa093f2269617214f703ac03e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552621"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="2863b-103">Filetransfers-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2863b-103">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2863b-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2863b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2863b-105">In der Filetransfer-Ansicht werden Informationen zu Peer-to-Peer-Dateiübertragungssitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2863b-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="2863b-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2863b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2863b-107">Die Dateitransfers-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> zusätzlich zu den unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="2863b-107">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2863b-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="2863b-108">Column</span></span></th>
<th><span data-ttu-id="2863b-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2863b-109">Data Type</span></span></th>
<th><span data-ttu-id="2863b-110">Details</span><span class="sxs-lookup"><span data-stu-id="2863b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2863b-111"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="2863b-111"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="2863b-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2863b-112">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2863b-113">Name der übertragenen Datei.</span><span class="sxs-lookup"><span data-stu-id="2863b-113">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2863b-114"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="2863b-114"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="2863b-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="2863b-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="2863b-116">Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2863b-116">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2863b-117"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="2863b-117"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="2863b-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="2863b-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2863b-119">Eindeutiger Bezeichner zum Unterscheiden zwischen Dateiübertragungen mit demselben Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="2863b-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2863b-120"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="2863b-120"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="2863b-121">Bit</span><span class="sxs-lookup"><span data-stu-id="2863b-121">bit</span></span></p></td>
<td><p><span data-ttu-id="2863b-p102">Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="2863b-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2863b-124"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="2863b-124"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="2863b-125">Bit</span><span class="sxs-lookup"><span data-stu-id="2863b-125">bit</span></span></p></td>
<td><p><span data-ttu-id="2863b-p103">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="2863b-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2863b-128"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="2863b-128"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="2863b-129">Bit</span><span class="sxs-lookup"><span data-stu-id="2863b-129">bit</span></span></p></td>
<td><p><span data-ttu-id="2863b-p104">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="2863b-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

