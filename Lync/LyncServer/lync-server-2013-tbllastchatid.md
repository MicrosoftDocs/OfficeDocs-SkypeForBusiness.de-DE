---
title: 'Lync Server 2013: tblLastChatId'
description: 'Lync Server 2013: tblLastChatId.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547601"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="1a7ff-103">tblLastChatId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a7ff-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a7ff-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1a7ff-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1a7ff-105">"LastChatId" enthält die zuletzt generierte (und in der tblChat-Tabelle verwendete) Chat-ID für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="1a7ff-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a7ff-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a7ff-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="1a7ff-107">Column</span></span></th>
<th><span data-ttu-id="1a7ff-108">Typ</span><span class="sxs-lookup"><span data-stu-id="1a7ff-108">Type</span></span></th>
<th><span data-ttu-id="1a7ff-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a7ff-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a7ff-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="1a7ff-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1a7ff-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1a7ff-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1a7ff-112">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="1a7ff-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a7ff-113">lastChatID</span><span class="sxs-lookup"><span data-stu-id="1a7ff-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="1a7ff-114">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="1a7ff-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1a7ff-115">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="1a7ff-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1a7ff-116">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1a7ff-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a7ff-117">Spalte</span><span class="sxs-lookup"><span data-stu-id="1a7ff-117">Column</span></span></th>
<th><span data-ttu-id="1a7ff-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a7ff-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a7ff-119">&lt;Knoten-lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="1a7ff-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="1a7ff-120">Primärschlüssel (für die Verarbeitung genügt nodeID).</span><span class="sxs-lookup"><span data-stu-id="1a7ff-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a7ff-121">nodeID</span><span class="sxs-lookup"><span data-stu-id="1a7ff-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="1a7ff-122">Fremdschlüssel mit Abfrage der Tabelle "Node.nodeID".</span><span class="sxs-lookup"><span data-stu-id="1a7ff-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="1a7ff-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a7ff-123">See Also</span></span>


[<span data-ttu-id="1a7ff-124">tblChat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a7ff-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

