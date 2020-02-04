---
title: 'Lync Server 2013: Dateiübertragungen (Ansicht)'
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
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="7587f-102">Dateiübertragungen (Ansicht) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7587f-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7587f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7587f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7587f-104">Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen.</span><span class="sxs-lookup"><span data-stu-id="7587f-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="7587f-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7587f-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7587f-106">Die Dateiübertragungen-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> sowie die unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="7587f-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7587f-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="7587f-107">Column</span></span></th>
<th><span data-ttu-id="7587f-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="7587f-108">Data Type</span></span></th>
<th><span data-ttu-id="7587f-109">Details</span><span class="sxs-lookup"><span data-stu-id="7587f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7587f-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="7587f-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="7587f-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7587f-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7587f-112">Der Name der übertragenen Datei.</span><span class="sxs-lookup"><span data-stu-id="7587f-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7587f-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="7587f-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="7587f-114">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="7587f-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7587f-115">Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7587f-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7587f-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="7587f-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="7587f-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="7587f-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7587f-118">Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="7587f-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7587f-119"><strong>Annehmen</strong></span><span class="sxs-lookup"><span data-stu-id="7587f-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="7587f-120">bit</span><span class="sxs-lookup"><span data-stu-id="7587f-120">bit</span></span></p></td>
<td><p><span data-ttu-id="7587f-121">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="7587f-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="7587f-122">Ist "true", ist "ablehnen" und "Abbrechen" NULL.</span><span class="sxs-lookup"><span data-stu-id="7587f-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7587f-123"><strong>Ablehnen</strong></span><span class="sxs-lookup"><span data-stu-id="7587f-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="7587f-124">bit</span><span class="sxs-lookup"><span data-stu-id="7587f-124">bit</span></span></p></td>
<td><p><span data-ttu-id="7587f-125">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="7587f-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="7587f-126">Ist "true", ist "akzeptieren" und "Abbrechen" NULL.</span><span class="sxs-lookup"><span data-stu-id="7587f-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7587f-127"><strong>Abbrechen</strong></span><span class="sxs-lookup"><span data-stu-id="7587f-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="7587f-128">bit</span><span class="sxs-lookup"><span data-stu-id="7587f-128">bit</span></span></p></td>
<td><p><span data-ttu-id="7587f-129">Kann "wahr" oder "Null" sein.</span><span class="sxs-lookup"><span data-stu-id="7587f-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="7587f-130">Ist "true", ist "annehmen und ablehnen" NULL.</span><span class="sxs-lookup"><span data-stu-id="7587f-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

