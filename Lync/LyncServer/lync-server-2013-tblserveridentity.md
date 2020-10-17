---
title: 'Lync Server 2013: tblServerIdentity'
description: 'Lync Server 2013: tblServerIdentity.'
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
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564531"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="5f2c7-103">tblServerIdentity in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f2c7-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f2c7-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5f2c7-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5f2c7-105">tblServerIdentity enthält die aktiven Chat Server im Serverpool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="5f2c7-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="5f2c7-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="5f2c7-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f2c7-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="5f2c7-107">Column</span></span></th>
<th><span data-ttu-id="5f2c7-108">Typ</span><span class="sxs-lookup"><span data-stu-id="5f2c7-108">Type</span></span></th>
<th><span data-ttu-id="5f2c7-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f2c7-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f2c7-110">ServerID</span><span class="sxs-lookup"><span data-stu-id="5f2c7-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5f2c7-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-112">Server-ID.</span><span class="sxs-lookup"><span data-stu-id="5f2c7-112">Server ID.</span></span> <span data-ttu-id="5f2c7-113">Entspricht der Instanz-ID aus dem zentralen Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="5f2c7-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2c7-114">ServerAddress</span><span class="sxs-lookup"><span data-stu-id="5f2c7-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-115">nvarchar (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5f2c7-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-116">Serveradresse mit der Windows Communication Foundation-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5f2c7-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2c7-117">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="5f2c7-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-118">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="5f2c7-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-119">Der letzte Zeitpunkt, zu dem der Kanalserver diese Zeile aktualisiert hat, um die Ausführung zu beweisen.</span><span class="sxs-lookup"><span data-stu-id="5f2c7-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5f2c7-120">Key</span><span class="sxs-lookup"><span data-stu-id="5f2c7-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f2c7-121">Spalte</span><span class="sxs-lookup"><span data-stu-id="5f2c7-121">Column</span></span></th>
<th><span data-ttu-id="5f2c7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f2c7-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f2c7-123">ServerID</span><span class="sxs-lookup"><span data-stu-id="5f2c7-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="5f2c7-124">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="5f2c7-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

