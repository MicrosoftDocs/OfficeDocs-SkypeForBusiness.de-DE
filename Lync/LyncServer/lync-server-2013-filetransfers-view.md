---
title: 'Lync Server 2013: File Transfers-Ansicht'
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
ms.openlocfilehash: e0fdfae0cefafc7ee6273af75e84e0ea6545188b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500872"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="5e676-102">Filetransfers-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e676-102">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e676-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5e676-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5e676-104">In der Filetransfer-Ansicht werden Informationen zu Peer-to-Peer-Dateiübertragungssitzungen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5e676-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="5e676-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5e676-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e676-106">Die Dateitransfers-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> zusätzlich zu den unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="5e676-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e676-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="5e676-107">Column</span></span></th>
<th><span data-ttu-id="5e676-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5e676-108">Data Type</span></span></th>
<th><span data-ttu-id="5e676-109">Details</span><span class="sxs-lookup"><span data-stu-id="5e676-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e676-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="5e676-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="5e676-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5e676-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5e676-112">Name der übertragenen Datei.</span><span class="sxs-lookup"><span data-stu-id="5e676-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e676-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="5e676-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="5e676-114">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="5e676-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5e676-115">Wird verwendet, um jede Nachricht zur Nachverfolgung als hiermit zugeordnet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5e676-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e676-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="5e676-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="5e676-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5e676-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5e676-118">Eindeutiger Bezeichner zum Unterscheiden zwischen Dateiübertragungen mit demselben Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="5e676-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e676-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="5e676-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="5e676-120">Bit</span><span class="sxs-lookup"><span data-stu-id="5e676-120">bit</span></span></p></td>
<td><p><span data-ttu-id="5e676-p102">Kann TRUE oder NULL sein. Falls TRUE erhalten Reject und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="5e676-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e676-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="5e676-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="5e676-124">Bit</span><span class="sxs-lookup"><span data-stu-id="5e676-124">bit</span></span></p></td>
<td><p><span data-ttu-id="5e676-p103">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Cancel den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="5e676-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e676-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="5e676-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="5e676-128">Bit</span><span class="sxs-lookup"><span data-stu-id="5e676-128">bit</span></span></p></td>
<td><p><span data-ttu-id="5e676-p104">Kann TRUE oder NULL sein. Falls TRUE erhalten Accept und Reject den Wert NULL.</span><span class="sxs-lookup"><span data-stu-id="5e676-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

