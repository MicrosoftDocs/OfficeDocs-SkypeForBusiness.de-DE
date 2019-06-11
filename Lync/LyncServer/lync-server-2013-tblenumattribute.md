---
title: 'Lync Server 2013: tblEnumAttribute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662f5d0ea9b55f8e3f5320b2e385157bef8bce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="10dee-102">tblEnumAttribute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dee-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10dee-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="10dee-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="10dee-104">tblEnumAttribute ist eine hart codierte Tabelle, die die Sichtbarkeits-und Verhaltensattribute enthält, die in der Knoten Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10dee-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="10dee-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="10dee-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10dee-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="10dee-106">Column</span></span></th>
<th><span data-ttu-id="10dee-107">Typ</span><span class="sxs-lookup"><span data-stu-id="10dee-107">Type</span></span></th>
<th><span data-ttu-id="10dee-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10dee-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10dee-109">AttributeID</span><span class="sxs-lookup"><span data-stu-id="10dee-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="10dee-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="10dee-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="10dee-111">Die ID des Attributs.</span><span class="sxs-lookup"><span data-stu-id="10dee-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10dee-112">AttributeName</span><span class="sxs-lookup"><span data-stu-id="10dee-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="10dee-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="10dee-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="10dee-114">Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="10dee-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="10dee-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="10dee-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10dee-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="10dee-116">Column</span></span></th>
<th><span data-ttu-id="10dee-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10dee-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10dee-118">AttributeID</span><span class="sxs-lookup"><span data-stu-id="10dee-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="10dee-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="10dee-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="10dee-120">Tabellenwerte</span><span class="sxs-lookup"><span data-stu-id="10dee-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10dee-121">AttributeID</span><span class="sxs-lookup"><span data-stu-id="10dee-121">attributeID</span></span></th>
<th><span data-ttu-id="10dee-122">AttributeName</span><span class="sxs-lookup"><span data-stu-id="10dee-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10dee-123">1</span><span class="sxs-lookup"><span data-stu-id="10dee-123">1</span></span></p></td>
<td><p><span data-ttu-id="10dee-124">Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="10dee-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10dee-125">2</span><span class="sxs-lookup"><span data-stu-id="10dee-125">2</span></span></p></td>
<td><p><span data-ttu-id="10dee-126">Verhalten.</span><span class="sxs-lookup"><span data-stu-id="10dee-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="10dee-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10dee-127">See Also</span></span>


[<span data-ttu-id="10dee-128">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dee-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

