---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61c2744c6a2cdf8b857161d3476885992c4d74e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="e6b40-102">tblSkippedAffiliations in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6b40-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6b40-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e6b40-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e6b40-104">tblSkippedAffiliations enthält die Zugehörigkeiten, die nicht gelesen werden konnten (in der Regel aufgrund von Active Directory-Domänendienste Zugriffsfehlern).</span><span class="sxs-lookup"><span data-stu-id="e6b40-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="e6b40-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="e6b40-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6b40-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="e6b40-106">Column</span></span></th>
<th><span data-ttu-id="e6b40-107">Typ</span><span class="sxs-lookup"><span data-stu-id="e6b40-107">Type</span></span></th>
<th><span data-ttu-id="e6b40-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6b40-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6b40-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e6b40-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="e6b40-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e6b40-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e6b40-111">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="e6b40-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6b40-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="e6b40-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="e6b40-113">nvarchar (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e6b40-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e6b40-114">Zeichenfolge, die die Zuordnung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e6b40-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="e6b40-115">Das Format lautet: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="e6b40-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6b40-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e6b40-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="e6b40-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e6b40-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e6b40-p101">ID des Prinzipals, der diese Zeile aktualisiert hat. Der Wert ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.</span><span class="sxs-lookup"><span data-stu-id="e6b40-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e6b40-120">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e6b40-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6b40-121">Spalte (n)</span><span class="sxs-lookup"><span data-stu-id="e6b40-121">Column(s)</span></span></th>
<th><span data-ttu-id="e6b40-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6b40-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6b40-123">&lt;prinID, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="e6b40-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="e6b40-124">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="e6b40-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6b40-125">prinID</span><span class="sxs-lookup"><span data-stu-id="e6b40-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="e6b40-126">Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e6b40-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

