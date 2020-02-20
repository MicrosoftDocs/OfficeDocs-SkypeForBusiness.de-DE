---
title: 'Lync Server 2013: tblActivePeers'
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
ms.openlocfilehash: 2ad7e0cff95cde5be9f869c59305c05a657f799f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="e50fb-102">tblActivePeers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e50fb-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e50fb-103">_**Letztes Änderungsstand des Themas:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="e50fb-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="e50fb-104">"tblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chatdiensten.</span><span class="sxs-lookup"><span data-stu-id="e50fb-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="e50fb-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="e50fb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e50fb-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="e50fb-106">Column</span></span></th>
<th><span data-ttu-id="e50fb-107">Typ</span><span class="sxs-lookup"><span data-stu-id="e50fb-107">Type</span></span></th>
<th><span data-ttu-id="e50fb-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e50fb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e50fb-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e50fb-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="e50fb-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e50fb-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e50fb-111">ID des Servers, der den Eintrag bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="e50fb-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e50fb-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e50fb-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="e50fb-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e50fb-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e50fb-114">ID des Peers, mit dem der bereitstellende Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="e50fb-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e50fb-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e50fb-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e50fb-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="e50fb-116">Column</span></span></th>
<th><span data-ttu-id="e50fb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e50fb-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e50fb-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="e50fb-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e50fb-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="e50fb-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e50fb-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e50fb-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="e50fb-121">Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".</span><span class="sxs-lookup"><span data-stu-id="e50fb-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e50fb-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e50fb-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="e50fb-123">Fremdschlüssel mit Abfrage der Tabelle "tblServerIdentity.serverID".</span><span class="sxs-lookup"><span data-stu-id="e50fb-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

