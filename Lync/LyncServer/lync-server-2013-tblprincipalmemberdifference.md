---
title: 'Lync Server 2013: principalmemberdifference'
description: 'Lync Server 2013: principalmemberdifference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573221"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="c3ee0-103">principalmemberdifference in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3ee0-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3ee0-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c3ee0-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c3ee0-105">principalmemberdifference enthält Änderungen an Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die noch nicht von den späteren Active Directory-Domänendienste Synchronisierungs Schritten verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="c3ee0-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="c3ee0-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="c3ee0-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3ee0-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="c3ee0-107">Column</span></span></th>
<th><span data-ttu-id="c3ee0-108">Typ</span><span class="sxs-lookup"><span data-stu-id="c3ee0-108">Type</span></span></th>
<th><span data-ttu-id="c3ee0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3ee0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3ee0-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c3ee0-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-111">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c3ee0-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-112">Prinzipal-GUID der geänderten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="c3ee0-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3ee0-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="c3ee0-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c3ee0-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-115">Distinguished Name (DN) des Mitglieds.</span><span class="sxs-lookup"><span data-stu-id="c3ee0-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3ee0-116">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="c3ee0-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-117">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c3ee0-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-p101">FALSE, wenn das Mitglied hinzugefügt wurde. TRUE, wenn das Mitglied entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="c3ee0-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c3ee0-120">Key</span><span class="sxs-lookup"><span data-stu-id="c3ee0-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3ee0-121">Spalte</span><span class="sxs-lookup"><span data-stu-id="c3ee0-121">Column</span></span></th>
<th><span data-ttu-id="c3ee0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3ee0-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3ee0-123">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="c3ee0-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="c3ee0-124">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="c3ee0-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

