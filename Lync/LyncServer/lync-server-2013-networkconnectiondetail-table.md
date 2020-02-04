---
title: 'Lync Server 2013: NetworkConnectionDetail-Tabelle'
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
ms.openlocfilehash: 2035fff89437c10732c704eee47c145b45d9db96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="6a06a-102">NetworkConnectionDetail-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a06a-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a06a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6a06a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6a06a-104">Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindungs Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a06a-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="6a06a-105">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6a06a-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a06a-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="6a06a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6a06a-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="6a06a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6a06a-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="6a06a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6a06a-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="6a06a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a06a-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="6a06a-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6a06a-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="6a06a-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6a06a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="6a06a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6a06a-113">Eindeutiger Bezeichner für den Netzwerkverbindungstyp.</span><span class="sxs-lookup"><span data-stu-id="6a06a-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a06a-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="6a06a-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="6a06a-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6a06a-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6a06a-116">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="6a06a-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="6a06a-117">Der Netzwerkverbindungstyp, der dem NetworkConnectionDetailKey-Element entspricht.</span><span class="sxs-lookup"><span data-stu-id="6a06a-117">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="6a06a-118">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6a06a-118">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="6a06a-119">0-verkabelt</span><span class="sxs-lookup"><span data-stu-id="6a06a-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="6a06a-120">1 – WiFi</span><span class="sxs-lookup"><span data-stu-id="6a06a-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="6a06a-121">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="6a06a-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

