---
title: 'Lync Server 2013: Device-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974898f6c3fa96dd9356a0a9eed1e3fab09d288b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="447c3-102">Device-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="447c3-102">Device table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="447c3-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="447c3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="447c3-104">Die Gerätetabelle ist eine unterstützende Tabelle, in der Informationen zu den verschiedenen Aufnahme-oder Render-Geräten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="447c3-104">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="447c3-105">Jeder Datensatz in der Tabelle steht für ein Gerät.</span><span class="sxs-lookup"><span data-stu-id="447c3-105">Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="447c3-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="447c3-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="447c3-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="447c3-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="447c3-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="447c3-111">int</span><span class="sxs-lookup"><span data-stu-id="447c3-111">int</span></span></p></td>
<td><p><span data-ttu-id="447c3-112">Primary</span><span class="sxs-lookup"><span data-stu-id="447c3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="447c3-113">Eindeutige Nummer, die dieses Gerät kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="447c3-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="447c3-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="447c3-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="447c3-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="447c3-116">DeviceName + DeviceType ist eindeutig</span><span class="sxs-lookup"><span data-stu-id="447c3-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="447c3-117">Gerätename.</span><span class="sxs-lookup"><span data-stu-id="447c3-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="447c3-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="447c3-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="447c3-119">bit</span><span class="sxs-lookup"><span data-stu-id="447c3-119">bit</span></span></p></td>
<td><p><span data-ttu-id="447c3-120">DeviceName + DeviceType ist eindeutig</span><span class="sxs-lookup"><span data-stu-id="447c3-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="447c3-121">Gerätetyp.</span><span class="sxs-lookup"><span data-stu-id="447c3-121">Device type.</span></span> <span data-ttu-id="447c3-122">1 ist ein Aufnahmegerät, 0 ist ein Render-Gerät.</span><span class="sxs-lookup"><span data-stu-id="447c3-122">1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

