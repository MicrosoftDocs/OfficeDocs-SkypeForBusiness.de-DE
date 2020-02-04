---
title: 'Lync Server 2013: DeRegisterType-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65c94513a3578f8608da555cdd0b3e2273b8a7da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="a7a23-102">DeRegisterType-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7a23-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7a23-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a7a23-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a7a23-104">Die Tabelle "deregistertype" ist eine statische Tabelle, in der die Liste der möglichen Benutzer deregister-Typen wie "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="a7a23-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7a23-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="a7a23-105">Column</span></span></th>
<th><span data-ttu-id="a7a23-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a7a23-106">Data Type</span></span></th>
<th><span data-ttu-id="a7a23-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="a7a23-107">Key/Index</span></span></th>
<th><span data-ttu-id="a7a23-108">Details</span><span class="sxs-lookup"><span data-stu-id="a7a23-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7a23-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a7a23-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a7a23-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7a23-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7a23-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a7a23-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7a23-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="a7a23-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="a7a23-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7a23-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a7a23-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="a7a23-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7a23-115">0-unbekannt</span><span class="sxs-lookup"><span data-stu-id="a7a23-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="a7a23-116">1-Client initiierte Deregistrierung</span><span class="sxs-lookup"><span data-stu-id="a7a23-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="a7a23-117">2 – Registrierung abgelaufen</span><span class="sxs-lookup"><span data-stu-id="a7a23-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="a7a23-118">3 – Client stürzte ab</span><span class="sxs-lookup"><span data-stu-id="a7a23-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="a7a23-119">4 – Benutzerattribute geändert</span><span class="sxs-lookup"><span data-stu-id="a7a23-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="a7a23-120">5 – bevorzugte Registrierungsstelle geändert</span><span class="sxs-lookup"><span data-stu-id="a7a23-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="a7a23-121">6 – Legacy-Client im Survival-Modus</span><span class="sxs-lookup"><span data-stu-id="a7a23-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

