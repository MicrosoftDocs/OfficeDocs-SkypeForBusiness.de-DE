---
title: 'Lync Server 2013: tblConfig'
description: 'Lync Server 2013: tblConfig.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8990e0b2c8724a5e90c36e706b92f9985f288772
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550431"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="bb252-103">tblConfig in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb252-103">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb252-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bb252-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bb252-105">tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="bb252-105">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="bb252-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="bb252-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb252-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="bb252-107">Column</span></span></th>
<th><span data-ttu-id="bb252-108">Typ</span><span class="sxs-lookup"><span data-stu-id="bb252-108">Type</span></span></th>
<th><span data-ttu-id="bb252-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb252-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb252-110">configLabel</span><span class="sxs-lookup"><span data-stu-id="bb252-110">configLabel</span></span></p></td>
<td><p><span data-ttu-id="bb252-111">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb252-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="bb252-112">Enthält &quot; Pool.&quot;</span><span class="sxs-lookup"><span data-stu-id="bb252-112">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb252-113">configContent</span><span class="sxs-lookup"><span data-stu-id="bb252-113">configContent</span></span></p></td>
<td><p><span data-ttu-id="bb252-114">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="bb252-114">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="bb252-115">Inhalt der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bb252-115">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb252-116">configPoolID</span><span class="sxs-lookup"><span data-stu-id="bb252-116">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="bb252-117">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="bb252-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bb252-118">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="bb252-118">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bb252-119">Key</span><span class="sxs-lookup"><span data-stu-id="bb252-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb252-120">Spalte</span><span class="sxs-lookup"><span data-stu-id="bb252-120">Column</span></span></th>
<th><span data-ttu-id="bb252-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb252-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb252-122">configLabel</span><span class="sxs-lookup"><span data-stu-id="bb252-122">configLabel</span></span></p></td>
<td><p><span data-ttu-id="bb252-123">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="bb252-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

