---
title: 'Lync Server 2013: tblSiopWhiteList'
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
ms.openlocfilehash: 4233989b9b8e00afdda389f468539da2ac7f61f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="3258f-102">tblSiopWhiteList in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3258f-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3258f-103">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="3258f-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="3258f-104">Bei "tblSiopWhiteList" handelt es sich um die Liste der registrierten Add-Ins, die mit Knoten verknüpft werden können.</span><span class="sxs-lookup"><span data-stu-id="3258f-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="3258f-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="3258f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3258f-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="3258f-106">Column</span></span></th>
<th><span data-ttu-id="3258f-107">Typ</span><span class="sxs-lookup"><span data-stu-id="3258f-107">Type</span></span></th>
<th><span data-ttu-id="3258f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3258f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3258f-109">siopID</span><span class="sxs-lookup"><span data-stu-id="3258f-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="3258f-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3258f-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="3258f-111">GUID des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="3258f-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3258f-112">siopName</span><span class="sxs-lookup"><span data-stu-id="3258f-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="3258f-113">nvarchar (50), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3258f-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="3258f-114">Anzeigename des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="3258f-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3258f-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="3258f-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="3258f-116">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3258f-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="3258f-117">URL des Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="3258f-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="3258f-118">Key</span><span class="sxs-lookup"><span data-stu-id="3258f-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3258f-119">Spalte</span><span class="sxs-lookup"><span data-stu-id="3258f-119">Column</span></span></th>
<th><span data-ttu-id="3258f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3258f-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3258f-121">siopID</span><span class="sxs-lookup"><span data-stu-id="3258f-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="3258f-122">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="3258f-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

