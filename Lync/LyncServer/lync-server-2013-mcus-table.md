---
title: 'Lync Server 2013: Mcus-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="bfdce-102">Mcus-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfdce-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfdce-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bfdce-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bfdce-104">Die Tabelle "MCU" ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bfdce-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="bfdce-105">In jedem Datensatz werden Informationen zu einem Konferenzdienst gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bfdce-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="bfdce-106">Dazu gehören der Chat-Konferenzdienst und der Telefonie-Konferenzdienst (der als Prozesse auf Front-End-Servern ausgeführt wird) sowie der Webkonferenzdienst und ein/V-Konferenzdienst.</span><span class="sxs-lookup"><span data-stu-id="bfdce-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfdce-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="bfdce-107">Column</span></span></th>
<th><span data-ttu-id="bfdce-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="bfdce-108">Data Type</span></span></th>
<th><span data-ttu-id="bfdce-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="bfdce-109">Key/Index</span></span></th>
<th><span data-ttu-id="bfdce-110">Details</span><span class="sxs-lookup"><span data-stu-id="bfdce-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfdce-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="bfdce-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdce-112">int</span><span class="sxs-lookup"><span data-stu-id="bfdce-112">int</span></span></p></td>
<td><p><span data-ttu-id="bfdce-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bfdce-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="bfdce-114">Eindeutige Nummer, die diesen Konferenzserver identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bfdce-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfdce-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="bfdce-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdce-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bfdce-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfdce-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="bfdce-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdce-118">inyint</span><span class="sxs-lookup"><span data-stu-id="bfdce-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="bfdce-119"> Fremd</span><span class="sxs-lookup"><span data-stu-id="bfdce-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="bfdce-120">Konferenz Servertyp wie conf: Chat (für IMS) oder conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="bfdce-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="bfdce-121">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bfdce-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

