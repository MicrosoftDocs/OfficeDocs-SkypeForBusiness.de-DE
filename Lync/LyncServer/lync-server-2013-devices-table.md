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
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="99194-102">Devices-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99194-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99194-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="99194-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="99194-104">Die Tabelle Devices ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="99194-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="99194-105">Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).</span><span class="sxs-lookup"><span data-stu-id="99194-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99194-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="99194-106">Column</span></span></th>
<th><span data-ttu-id="99194-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="99194-107">Data Type</span></span></th>
<th><span data-ttu-id="99194-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="99194-108">Key/Index</span></span></th>
<th><span data-ttu-id="99194-109">Details</span><span class="sxs-lookup"><span data-stu-id="99194-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99194-110"><strong>DeviceID</strong></span><span class="sxs-lookup"><span data-stu-id="99194-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="99194-111">int</span><span class="sxs-lookup"><span data-stu-id="99194-111">int</span></span></p></td>
<td><p><span data-ttu-id="99194-112">Primary</span><span class="sxs-lookup"><span data-stu-id="99194-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="99194-113">Eindeutige Nummer, die diese Hardware Version kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="99194-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99194-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="99194-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="99194-115">int</span><span class="sxs-lookup"><span data-stu-id="99194-115">int</span></span></p></td>
<td><p><span data-ttu-id="99194-116">Fremd</span><span class="sxs-lookup"><span data-stu-id="99194-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="99194-117">Hersteller des Geräts.</span><span class="sxs-lookup"><span data-stu-id="99194-117">Manufacturer of this device.</span></span> <span data-ttu-id="99194-118">Weitere Informationen finden Sie <a href="lync-server-2013-manufacturers-table.md">in der Tabelle "Hersteller" in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="99194-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99194-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="99194-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="99194-120">int</span><span class="sxs-lookup"><span data-stu-id="99194-120">int</span></span></p></td>
<td><p><span data-ttu-id="99194-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="99194-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="99194-122">Hardware Version dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="99194-122">Hardware version of this device.</span></span> <span data-ttu-id="99194-123">Weitere Informationen finden Sie <a href="lync-server-2013-hardwareversions-table.md">in der HardwareVersions-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="99194-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99194-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="99194-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="99194-125">bigint</span><span class="sxs-lookup"><span data-stu-id="99194-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="99194-126">Mac-Adresse</span><span class="sxs-lookup"><span data-stu-id="99194-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

