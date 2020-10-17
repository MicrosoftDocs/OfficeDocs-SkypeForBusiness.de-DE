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
ms.openlocfilehash: b184d863ff9d0404fbc05b90a88f7c203499262a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523822"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="46b90-102">tblLastChatId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46b90-102">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46b90-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="46b90-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="46b90-104">"LastChatId" enthält die zuletzt generierte (und in der tblChat-Tabelle verwendete) Chat-ID für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="46b90-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="46b90-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="46b90-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46b90-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="46b90-106">Column</span></span></th>
<th><span data-ttu-id="46b90-107">Typ</span><span class="sxs-lookup"><span data-stu-id="46b90-107">Type</span></span></th>
<th><span data-ttu-id="46b90-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46b90-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46b90-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="46b90-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="46b90-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="46b90-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="46b90-111">Knoten-ID (nur Chatroom).</span><span class="sxs-lookup"><span data-stu-id="46b90-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b90-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="46b90-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="46b90-113">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="46b90-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="46b90-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="46b90-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="46b90-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="46b90-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46b90-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="46b90-116">Column</span></span></th>
<th><span data-ttu-id="46b90-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46b90-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46b90-118">&lt;Knoten-lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="46b90-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="46b90-119">Primärschlüssel (für die Verarbeitung genügt nodeID).</span><span class="sxs-lookup"><span data-stu-id="46b90-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46b90-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="46b90-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="46b90-121">Fremdschlüssel mit Abfrage der Tabelle "Node.nodeID".</span><span class="sxs-lookup"><span data-stu-id="46b90-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="46b90-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46b90-122">See Also</span></span>


[<span data-ttu-id="46b90-123">tblChat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46b90-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

