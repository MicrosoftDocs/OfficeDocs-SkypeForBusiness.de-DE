---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2379622ee5b1121367c35b4baac98d6c79d61023
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="95008-102">tblServerIdentity in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95008-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95008-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="95008-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="95008-104">tblServerIdentity enthält die aktiven Chat Server im persistent Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="95008-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="95008-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="95008-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95008-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="95008-106">Column</span></span></th>
<th><span data-ttu-id="95008-107">Typ</span><span class="sxs-lookup"><span data-stu-id="95008-107">Type</span></span></th>
<th><span data-ttu-id="95008-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95008-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95008-109">ServerID</span><span class="sxs-lookup"><span data-stu-id="95008-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="95008-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="95008-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="95008-111">Server-ID.</span><span class="sxs-lookup"><span data-stu-id="95008-111">Server ID.</span></span> <span data-ttu-id="95008-112">Entspricht der Instanz-ID des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="95008-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95008-113">ServerAddress</span><span class="sxs-lookup"><span data-stu-id="95008-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="95008-114">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="95008-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="95008-115">Server Adresse unter Verwendung der Windows Communication Foundation-Adresse.</span><span class="sxs-lookup"><span data-stu-id="95008-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95008-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="95008-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="95008-117">datetime</span><span class="sxs-lookup"><span data-stu-id="95008-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="95008-118">Der letzte Zeitpunkt, zu dem der Kanal Server diese Zeile aktualisiert hat, um zu beweisen, dass er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="95008-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="95008-119">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="95008-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95008-120">Spalte</span><span class="sxs-lookup"><span data-stu-id="95008-120">Column</span></span></th>
<th><span data-ttu-id="95008-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95008-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95008-122">ServerID</span><span class="sxs-lookup"><span data-stu-id="95008-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="95008-123">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="95008-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

