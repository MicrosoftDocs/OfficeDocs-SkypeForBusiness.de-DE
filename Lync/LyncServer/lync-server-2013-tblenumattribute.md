---
title: 'Lync Server 2013: tblEnumAttribute'
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
ms.openlocfilehash: 73ac5a7cf26c97b31daf5785a90fac102c50e480
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="b3a72-102">tblEnumAttribute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3a72-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3a72-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b3a72-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b3a72-104">tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3a72-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="b3a72-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="b3a72-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3a72-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="b3a72-106">Column</span></span></th>
<th><span data-ttu-id="b3a72-107">Typ</span><span class="sxs-lookup"><span data-stu-id="b3a72-107">Type</span></span></th>
<th><span data-ttu-id="b3a72-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3a72-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3a72-109">AttributeID</span><span class="sxs-lookup"><span data-stu-id="b3a72-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="b3a72-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b3a72-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b3a72-111">Die ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="b3a72-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3a72-112">AttributeName</span><span class="sxs-lookup"><span data-stu-id="b3a72-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="b3a72-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b3a72-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b3a72-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="b3a72-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b3a72-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b3a72-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3a72-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="b3a72-116">Column</span></span></th>
<th><span data-ttu-id="b3a72-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3a72-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3a72-118">AttributeID</span><span class="sxs-lookup"><span data-stu-id="b3a72-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="b3a72-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="b3a72-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="b3a72-120">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="b3a72-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3a72-121">AttributeID</span><span class="sxs-lookup"><span data-stu-id="b3a72-121">attributeID</span></span></th>
<th><span data-ttu-id="b3a72-122">AttributeName</span><span class="sxs-lookup"><span data-stu-id="b3a72-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3a72-123">1</span><span class="sxs-lookup"><span data-stu-id="b3a72-123">1</span></span></p></td>
<td><p><span data-ttu-id="b3a72-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="b3a72-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3a72-125">2</span><span class="sxs-lookup"><span data-stu-id="b3a72-125">2</span></span></p></td>
<td><p><span data-ttu-id="b3a72-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b3a72-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b3a72-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3a72-127">See Also</span></span>


[<span data-ttu-id="b3a72-128">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3a72-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

