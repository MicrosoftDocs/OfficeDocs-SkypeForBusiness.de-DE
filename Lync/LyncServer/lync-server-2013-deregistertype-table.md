---
title: 'Lync Server 2013: deregistertype-Tabelle'
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
ms.openlocfilehash: 915a5d0a2c5c4a5f38063b56dc133d2558aa65ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="6863b-102">Deregistertype-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6863b-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6863b-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6863b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6863b-104">Bei der DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die eine Liste der möglichen Typen für eine Aufhebung der Registrierung von Benutzern speichert, wie zum Beispiel "Aufhebung der Registrierung durch den Client", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".</span><span class="sxs-lookup"><span data-stu-id="6863b-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6863b-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="6863b-105">Column</span></span></th>
<th><span data-ttu-id="6863b-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6863b-106">Data Type</span></span></th>
<th><span data-ttu-id="6863b-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="6863b-107">Key/Index</span></span></th>
<th><span data-ttu-id="6863b-108">Details</span><span class="sxs-lookup"><span data-stu-id="6863b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6863b-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="6863b-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="6863b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="6863b-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6863b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="6863b-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6863b-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="6863b-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="6863b-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6863b-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6863b-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="6863b-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="6863b-115">0 -- Unbekannt</span><span class="sxs-lookup"><span data-stu-id="6863b-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="6863b-116">1 -- Aufhebung der Registrierung durch den Client</span><span class="sxs-lookup"><span data-stu-id="6863b-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="6863b-117">2 -- Registrierung abgelaufen</span><span class="sxs-lookup"><span data-stu-id="6863b-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="6863b-118">3 – Clientabsturz</span><span class="sxs-lookup"><span data-stu-id="6863b-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="6863b-119">4 -- Benutzerattribute geändert</span><span class="sxs-lookup"><span data-stu-id="6863b-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="6863b-120">5 – Bevorzugte Registrierungsstelle geändert</span><span class="sxs-lookup"><span data-stu-id="6863b-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="6863b-121">6 -- Legacyclient In Survival Mode</span><span class="sxs-lookup"><span data-stu-id="6863b-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

