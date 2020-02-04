---
title: 'Lync Server 2013: tblConfig'
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
ms.openlocfilehash: 8b0e383791eafbe017e5163156ba53cdad581cb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="cb4db-102">tblConfig in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb4db-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb4db-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cb4db-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cb4db-104">tblConfig enthält eine nicht unterstützte Konfiguration für beständigen Chat Server in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="cb4db-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="cb4db-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="cb4db-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb4db-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="cb4db-106">Column</span></span></th>
<th><span data-ttu-id="cb4db-107">Typ</span><span class="sxs-lookup"><span data-stu-id="cb4db-107">Type</span></span></th>
<th><span data-ttu-id="cb4db-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb4db-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb4db-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="cb4db-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="cb4db-110">nvarchar (255); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cb4db-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="cb4db-111">Enthält &quot;Pool.&quot;</span><span class="sxs-lookup"><span data-stu-id="cb4db-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb4db-112">configContent</span><span class="sxs-lookup"><span data-stu-id="cb4db-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="cb4db-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="cb4db-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="cb4db-114">Konfigurationsinhalt.</span><span class="sxs-lookup"><span data-stu-id="cb4db-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb4db-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="cb4db-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="cb4db-116">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cb4db-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="cb4db-117">Eindeutige ID der Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="cb4db-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cb4db-118">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="cb4db-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb4db-119">Spalte</span><span class="sxs-lookup"><span data-stu-id="cb4db-119">Column</span></span></th>
<th><span data-ttu-id="cb4db-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb4db-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb4db-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="cb4db-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="cb4db-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="cb4db-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

