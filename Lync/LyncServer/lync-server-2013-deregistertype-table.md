---
title: 'Lync Server 2013: DeRegisterType-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97d25ded1a281df0774644cd0d69f5e12d9c85a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="d6e90-102">DeRegisterType-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6e90-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6e90-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d6e90-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d6e90-104">Die Tabelle "deregistertype" ist eine statische Tabelle, in der die Liste der möglichen Benutzer deregister-Typen wie "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d6e90-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6e90-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="d6e90-105">Column</span></span></th>
<th><span data-ttu-id="d6e90-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d6e90-106">Data Type</span></span></th>
<th><span data-ttu-id="d6e90-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="d6e90-107">Key/Index</span></span></th>
<th><span data-ttu-id="d6e90-108">Details</span><span class="sxs-lookup"><span data-stu-id="d6e90-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6e90-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d6e90-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d6e90-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d6e90-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d6e90-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d6e90-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6e90-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="d6e90-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="d6e90-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6e90-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d6e90-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="d6e90-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d6e90-115">0-unbekannt</span><span class="sxs-lookup"><span data-stu-id="d6e90-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="d6e90-116">1-Client initiierte Deregistrierung</span><span class="sxs-lookup"><span data-stu-id="d6e90-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="d6e90-117">2 – Registrierung abgelaufen</span><span class="sxs-lookup"><span data-stu-id="d6e90-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="d6e90-118">3 – Client stürzte ab</span><span class="sxs-lookup"><span data-stu-id="d6e90-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="d6e90-119">4 – Benutzerattribute geändert</span><span class="sxs-lookup"><span data-stu-id="d6e90-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="d6e90-120">5 – bevorzugte Registrierungsstelle geändert</span><span class="sxs-lookup"><span data-stu-id="d6e90-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="d6e90-121">6 – Legacy-Client im Survival-Modus</span><span class="sxs-lookup"><span data-stu-id="d6e90-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

