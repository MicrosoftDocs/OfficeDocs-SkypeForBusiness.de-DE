---
title: 'Lync Server 2013: tblEnumAttribute'
description: 'Lync Server 2013: tblEnumAttribute.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca979a68e758ad47b691ac704f24c68c1841938a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571391"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="e4e84-103">tblEnumAttribute in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4e84-103">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4e84-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e4e84-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e4e84-105">"EnumAttribute" ist eine hardkodierte Tabelle, mit den Attributen "Visibility" und "Behavior", die in der "Node"-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4e84-105">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="e4e84-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="e4e84-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4e84-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="e4e84-107">Column</span></span></th>
<th><span data-ttu-id="e4e84-108">Typ</span><span class="sxs-lookup"><span data-stu-id="e4e84-108">Type</span></span></th>
<th><span data-ttu-id="e4e84-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4e84-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4e84-110">AttributeID</span><span class="sxs-lookup"><span data-stu-id="e4e84-110">attributeID</span></span></p></td>
<td><p><span data-ttu-id="e4e84-111">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e4e84-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e4e84-112">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="e4e84-112">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e84-113">AttributeName</span><span class="sxs-lookup"><span data-stu-id="e4e84-113">attributeName</span></span></p></td>
<td><p><span data-ttu-id="e4e84-114">nvarchar (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e4e84-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e4e84-115">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="e4e84-115">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e4e84-116">Key</span><span class="sxs-lookup"><span data-stu-id="e4e84-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4e84-117">Spalte</span><span class="sxs-lookup"><span data-stu-id="e4e84-117">Column</span></span></th>
<th><span data-ttu-id="e4e84-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4e84-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4e84-119">AttributeID</span><span class="sxs-lookup"><span data-stu-id="e4e84-119">attributeID</span></span></p></td>
<td><p><span data-ttu-id="e4e84-120">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="e4e84-120">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="e4e84-121">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="e4e84-121">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4e84-122">AttributeID</span><span class="sxs-lookup"><span data-stu-id="e4e84-122">attributeID</span></span></th>
<th><span data-ttu-id="e4e84-123">AttributeName</span><span class="sxs-lookup"><span data-stu-id="e4e84-123">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4e84-124">1</span><span class="sxs-lookup"><span data-stu-id="e4e84-124">1</span></span></p></td>
<td><p><span data-ttu-id="e4e84-125">Sicht.</span><span class="sxs-lookup"><span data-stu-id="e4e84-125">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4e84-126">2</span><span class="sxs-lookup"><span data-stu-id="e4e84-126">2</span></span></p></td>
<td><p><span data-ttu-id="e4e84-127">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e4e84-127">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e4e84-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4e84-128">See Also</span></span>


[<span data-ttu-id="e4e84-129">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4e84-129">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

