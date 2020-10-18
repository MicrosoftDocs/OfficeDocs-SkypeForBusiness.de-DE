---
title: 'Lync Server 2013: tblActivePeers'
description: 'Lync Server 2013: tblActivePeers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f274f82a280883e38e8e02409305982b64c18e4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573741"
---
# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="9d5d0-103">tblActivePeers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d5d0-103">tblActivePeers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d5d0-104">_**Letztes Änderungsstand des Themas:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="9d5d0-104">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="9d5d0-105">"tblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten.</span><span class="sxs-lookup"><span data-stu-id="9d5d0-105">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="9d5d0-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="9d5d0-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d5d0-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="9d5d0-107">Column</span></span></th>
<th><span data-ttu-id="9d5d0-108">Typ</span><span class="sxs-lookup"><span data-stu-id="9d5d0-108">Type</span></span></th>
<th><span data-ttu-id="9d5d0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d5d0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d5d0-110">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9d5d0-110">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="9d5d0-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-112">ID des Servers, der den Eintrag bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="9d5d0-112">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d5d0-113">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9d5d0-113">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="9d5d0-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-115">ID des Peers, mit dem der bereitstellende Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="9d5d0-115">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9d5d0-116">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="9d5d0-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d5d0-117">Spalte</span><span class="sxs-lookup"><span data-stu-id="9d5d0-117">Column</span></span></th>
<th><span data-ttu-id="9d5d0-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d5d0-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d5d0-119">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="9d5d0-119">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-120">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="9d5d0-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d5d0-121">aplServerID</span><span class="sxs-lookup"><span data-stu-id="9d5d0-121">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-122">Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".</span><span class="sxs-lookup"><span data-stu-id="9d5d0-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d5d0-123">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="9d5d0-123">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="9d5d0-124">Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".</span><span class="sxs-lookup"><span data-stu-id="9d5d0-124">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

