---
title: 'Lync Server 2013: Device-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d6c53a8a1197b47b2ec91cff97c1e403b91d1c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="76c47-102">Gerätetabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76c47-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76c47-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="76c47-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="76c47-p101">Bei der Device-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Aufnahme- oder Darstellungsgeräte gespeichert sind. Jeder Datensatz in der Tabelle steht für ein Gerät.</span><span class="sxs-lookup"><span data-stu-id="76c47-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76c47-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="76c47-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="76c47-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="76c47-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76c47-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="76c47-111">int</span><span class="sxs-lookup"><span data-stu-id="76c47-111">int</span></span></p></td>
<td><p><span data-ttu-id="76c47-112">Primary</span><span class="sxs-lookup"><span data-stu-id="76c47-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="76c47-113">Eindeutige Zahl, die dieses Gerät identifiziert.</span><span class="sxs-lookup"><span data-stu-id="76c47-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76c47-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="76c47-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="76c47-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="76c47-116">DeviceName + DeviceType ist unique</span><span class="sxs-lookup"><span data-stu-id="76c47-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="76c47-117">Gerätename</span><span class="sxs-lookup"><span data-stu-id="76c47-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76c47-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="76c47-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="76c47-119">Bit</span><span class="sxs-lookup"><span data-stu-id="76c47-119">bit</span></span></p></td>
<td><p><span data-ttu-id="76c47-120">DeviceName + DeviceType ist unique</span><span class="sxs-lookup"><span data-stu-id="76c47-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="76c47-p102">Gerätetyp. 1 ist ein Aufnahmegerät, 0 ist ein Darstellungsgerät.</span><span class="sxs-lookup"><span data-stu-id="76c47-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

