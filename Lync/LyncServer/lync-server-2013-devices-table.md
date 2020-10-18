---
title: 'Lync Server 2013: Devices-Tabelle'
description: 'Lync Server 2013: Devices-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763e1788e2874f9f9831c089ffe8fa077621b030
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576241"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="ac716-103">Devices-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac716-103">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac716-104">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ac716-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ac716-p101">Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).</span><span class="sxs-lookup"><span data-stu-id="ac716-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac716-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="ac716-107">Column</span></span></th>
<th><span data-ttu-id="ac716-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ac716-108">Data Type</span></span></th>
<th><span data-ttu-id="ac716-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="ac716-109">Key/Index</span></span></th>
<th><span data-ttu-id="ac716-110">Details</span><span class="sxs-lookup"><span data-stu-id="ac716-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac716-111"><strong>DeviceID</strong></span><span class="sxs-lookup"><span data-stu-id="ac716-111"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac716-112">int</span><span class="sxs-lookup"><span data-stu-id="ac716-112">int</span></span></p></td>
<td><p><span data-ttu-id="ac716-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ac716-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ac716-114">Eindeutige Zahl, die diese Hardwareversion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ac716-114">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac716-115"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="ac716-115"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac716-116">int</span><span class="sxs-lookup"><span data-stu-id="ac716-116">int</span></span></p></td>
<td><p><span data-ttu-id="ac716-117">Fremd</span><span class="sxs-lookup"><span data-stu-id="ac716-117">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac716-118">Hersteller dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="ac716-118">Manufacturer of this device.</span></span> <span data-ttu-id="ac716-119">Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle Hersteller in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac716-119">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac716-120"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ac716-120"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ac716-121">int</span><span class="sxs-lookup"><span data-stu-id="ac716-121">int</span></span></p></td>
<td><p><span data-ttu-id="ac716-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="ac716-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ac716-123">Hardwareversion dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="ac716-123">Hardware version of this device.</span></span> <span data-ttu-id="ac716-124">Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der Hardware Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ac716-124">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac716-125"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="ac716-125"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ac716-126">bigint</span><span class="sxs-lookup"><span data-stu-id="ac716-126">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac716-127">MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="ac716-127">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

