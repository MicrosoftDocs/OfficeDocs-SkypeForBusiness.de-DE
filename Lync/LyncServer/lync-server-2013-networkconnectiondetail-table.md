---
title: 'Lync Server 2013: NetworkConnectionDetail-Tabelle'
description: 'Lync Server 2013: NetworkConnectionDetail-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd0f429999b6629826a9f9369d154afe3c1af2f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561401"
---
# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="fadfc-103">NetworkConnectionDetail-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fadfc-103">NetworkConnectionDetail table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fadfc-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fadfc-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fadfc-105">Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu.</span><span class="sxs-lookup"><span data-stu-id="fadfc-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="fadfc-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fadfc-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fadfc-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="fadfc-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fadfc-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="fadfc-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fadfc-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="fadfc-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fadfc-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="fadfc-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fadfc-111"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="fadfc-111"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fadfc-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="fadfc-112">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fadfc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fadfc-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fadfc-114">Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</span><span class="sxs-lookup"><span data-stu-id="fadfc-114">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fadfc-115"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="fadfc-115"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="fadfc-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fadfc-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fadfc-117">Eigen</span><span class="sxs-lookup"><span data-stu-id="fadfc-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="fadfc-p102">Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fadfc-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="fadfc-120">0 – Wired</span><span class="sxs-lookup"><span data-stu-id="fadfc-120">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="fadfc-121">1 – WiFi</span><span class="sxs-lookup"><span data-stu-id="fadfc-121">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="fadfc-122">2 – Ethernet</span><span class="sxs-lookup"><span data-stu-id="fadfc-122">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

