---
title: 'Lync Server 2013: Devices-Tabelle'
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
ms.openlocfilehash: c5fdc4c3b20bdd60d2c8013b79a15bdfd30b56af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536932"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="2ab3f-102">Devices-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ab3f-102">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ab3f-103">_**Letztes Änderungsstand des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="2ab3f-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="2ab3f-p101">Bei der Devices-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz speichert Informationen über ein Gerät (Telefonapparat).</span><span class="sxs-lookup"><span data-stu-id="2ab3f-p101">The Devices table is a supporting table. Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ab3f-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="2ab3f-106">Column</span></span></th>
<th><span data-ttu-id="2ab3f-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2ab3f-107">Data Type</span></span></th>
<th><span data-ttu-id="2ab3f-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="2ab3f-108">Key/Index</span></span></th>
<th><span data-ttu-id="2ab3f-109">Details</span><span class="sxs-lookup"><span data-stu-id="2ab3f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab3f-110"><strong>DeviceID</strong></span><span class="sxs-lookup"><span data-stu-id="2ab3f-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ab3f-111">int</span><span class="sxs-lookup"><span data-stu-id="2ab3f-111">int</span></span></p></td>
<td><p><span data-ttu-id="2ab3f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="2ab3f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ab3f-113">Eindeutige Zahl, die diese Hardwareversion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2ab3f-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab3f-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="2ab3f-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ab3f-115">int</span><span class="sxs-lookup"><span data-stu-id="2ab3f-115">int</span></span></p></td>
<td><p><span data-ttu-id="2ab3f-116">Fremd</span><span class="sxs-lookup"><span data-stu-id="2ab3f-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2ab3f-117">Hersteller dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="2ab3f-117">Manufacturer of this device.</span></span> <span data-ttu-id="2ab3f-118">Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle Hersteller in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2ab3f-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ab3f-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="2ab3f-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ab3f-120">int</span><span class="sxs-lookup"><span data-stu-id="2ab3f-120">int</span></span></p></td>
<td><p><span data-ttu-id="2ab3f-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="2ab3f-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2ab3f-122">Hardwareversion dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="2ab3f-122">Hardware version of this device.</span></span> <span data-ttu-id="2ab3f-123">Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der Hardware Versions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2ab3f-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab3f-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="2ab3f-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="2ab3f-125">bigint</span><span class="sxs-lookup"><span data-stu-id="2ab3f-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ab3f-126">MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="2ab3f-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

