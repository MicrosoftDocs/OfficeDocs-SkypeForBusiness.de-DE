---
title: 'Lync Server 2013: Tabelle "MCU"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb0e54f1f7a8e94b4d87fee9f79cd4228b3fd49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="76d47-102">Tabelle "MCU" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76d47-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76d47-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="76d47-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="76d47-104">Die Tabelle "MCU" ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="76d47-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="76d47-105">Jeder Datensatz speichert Informationen zu einem Konferenzdienst.</span><span class="sxs-lookup"><span data-stu-id="76d47-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="76d47-106">Hierzu können die Sofortnachrichten-Konferenzdienst und die Telefonkonferenzdienst (die als Prozesse auf Front-End-Servern ausgeführt werden) sowie die Webkonferenzdienst und A/V-Konferenzdienst gehören.</span><span class="sxs-lookup"><span data-stu-id="76d47-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76d47-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="76d47-107">Column</span></span></th>
<th><span data-ttu-id="76d47-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="76d47-108">Data Type</span></span></th>
<th><span data-ttu-id="76d47-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="76d47-109">Key/Index</span></span></th>
<th><span data-ttu-id="76d47-110">Details</span><span class="sxs-lookup"><span data-stu-id="76d47-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76d47-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="76d47-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="76d47-112">int</span><span class="sxs-lookup"><span data-stu-id="76d47-112">int</span></span></p></td>
<td><p><span data-ttu-id="76d47-113">Primary</span><span class="sxs-lookup"><span data-stu-id="76d47-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="76d47-114">Eindeutige Zahl, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="76d47-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76d47-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="76d47-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="76d47-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="76d47-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76d47-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="76d47-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="76d47-118">inyint</span><span class="sxs-lookup"><span data-stu-id="76d47-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="76d47-119"> Fremd</span><span class="sxs-lookup"><span data-stu-id="76d47-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="76d47-120">Typ des Konferenzservers, beispielsweise conf: Chat (für IMS) oder conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="76d47-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="76d47-121">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="76d47-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

