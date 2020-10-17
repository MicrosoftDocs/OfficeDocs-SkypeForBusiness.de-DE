---
title: 'Lync Server 2013: tblSiopWhiteList'
description: 'Lync Server 2013: tblSiopWhiteList.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbb58c0818a6f36959732f210b8eb53bbfe223d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563861"
---
# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="7cd5d-103">tblSiopWhiteList in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cd5d-103">tblSiopWhiteList in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cd5d-104">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="7cd5d-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="7cd5d-105">Bei "tblSiopWhiteList" handelt es sich um die Liste der registrierten Add-Ins, die mit Knoten verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-105">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="7cd5d-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="7cd5d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cd5d-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="7cd5d-107">Column</span></span></th>
<th><span data-ttu-id="7cd5d-108">Typ</span><span class="sxs-lookup"><span data-stu-id="7cd5d-108">Type</span></span></th>
<th><span data-ttu-id="7cd5d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cd5d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cd5d-110">siopID</span><span class="sxs-lookup"><span data-stu-id="7cd5d-110">siopID</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-111">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7cd5d-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-112">GUID des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-112">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cd5d-113">siopName</span><span class="sxs-lookup"><span data-stu-id="7cd5d-113">siopName</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-114">nvarchar (50), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7cd5d-114">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-115">Anzeigename des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-115">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cd5d-116">siopUrl</span><span class="sxs-lookup"><span data-stu-id="7cd5d-116">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-117">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7cd5d-117">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-118">URL des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="7cd5d-118">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7cd5d-119">Key</span><span class="sxs-lookup"><span data-stu-id="7cd5d-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cd5d-120">Spalte</span><span class="sxs-lookup"><span data-stu-id="7cd5d-120">Column</span></span></th>
<th><span data-ttu-id="7cd5d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cd5d-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cd5d-122">siopID</span><span class="sxs-lookup"><span data-stu-id="7cd5d-122">siopID</span></span></p></td>
<td><p><span data-ttu-id="7cd5d-123">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7cd5d-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

