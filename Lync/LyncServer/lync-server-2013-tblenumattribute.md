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
ms.openlocfilehash: f3b015d1148c3c820c27cdbe48e191bd09d2f55e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509352"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="a2fe3-102">tblEnumAttribute in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fe3-102">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2fe3-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a2fe3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a2fe3-104">"EnumAttribute" ist eine hardkodierte Tabelle, mit den Attributen "Visibility" und "Behavior", die in der "Node"-Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2fe3-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="a2fe3-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="a2fe3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2fe3-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="a2fe3-106">Column</span></span></th>
<th><span data-ttu-id="a2fe3-107">Typ</span><span class="sxs-lookup"><span data-stu-id="a2fe3-107">Type</span></span></th>
<th><span data-ttu-id="a2fe3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2fe3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2fe3-109">AttributeID</span><span class="sxs-lookup"><span data-stu-id="a2fe3-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a2fe3-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-111">ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="a2fe3-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2fe3-112">AttributeName</span><span class="sxs-lookup"><span data-stu-id="a2fe3-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-113">nvarchar (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a2fe3-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="a2fe3-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a2fe3-115">Key</span><span class="sxs-lookup"><span data-stu-id="a2fe3-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2fe3-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="a2fe3-116">Column</span></span></th>
<th><span data-ttu-id="a2fe3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2fe3-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2fe3-118">AttributeID</span><span class="sxs-lookup"><span data-stu-id="a2fe3-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="a2fe3-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="a2fe3-120">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="a2fe3-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2fe3-121">AttributeID</span><span class="sxs-lookup"><span data-stu-id="a2fe3-121">attributeID</span></span></th>
<th><span data-ttu-id="a2fe3-122">AttributeName</span><span class="sxs-lookup"><span data-stu-id="a2fe3-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2fe3-123">1</span><span class="sxs-lookup"><span data-stu-id="a2fe3-123">1</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-124">Sicht.</span><span class="sxs-lookup"><span data-stu-id="a2fe3-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2fe3-125">2</span><span class="sxs-lookup"><span data-stu-id="a2fe3-125">2</span></span></p></td>
<td><p><span data-ttu-id="a2fe3-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="a2fe3-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a2fe3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2fe3-127">See Also</span></span>


[<span data-ttu-id="a2fe3-128">tblNode in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2fe3-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

