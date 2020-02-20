---
title: 'Lync Server 2013: tblLastChatId'
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
ms.openlocfilehash: 542b9f2006572edab4c9ca0adb29836174bc7aa7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="9481b-102">tblLastChatId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9481b-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9481b-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9481b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9481b-104">"LastChatId" enthält die zuletzt generierte (und in der tblChat-Tabelle verwendete) Chat-ID für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9481b-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="9481b-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="9481b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9481b-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="9481b-106">Column</span></span></th>
<th><span data-ttu-id="9481b-107">Typ</span><span class="sxs-lookup"><span data-stu-id="9481b-107">Type</span></span></th>
<th><span data-ttu-id="9481b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9481b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9481b-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="9481b-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9481b-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="9481b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9481b-111">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="9481b-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9481b-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="9481b-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="9481b-113">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="9481b-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="9481b-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="9481b-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9481b-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="9481b-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9481b-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="9481b-116">Column</span></span></th>
<th><span data-ttu-id="9481b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9481b-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9481b-118">&lt;Knoten-lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="9481b-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9481b-119">Primärschlüssel (für die Verarbeitung genügt nodeID).</span><span class="sxs-lookup"><span data-stu-id="9481b-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9481b-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="9481b-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9481b-121">Fremdschlüssel mit Abfrage der Tabelle "Node.nodeID".</span><span class="sxs-lookup"><span data-stu-id="9481b-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="9481b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9481b-122">See Also</span></span>


[<span data-ttu-id="9481b-123">tblChat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9481b-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

