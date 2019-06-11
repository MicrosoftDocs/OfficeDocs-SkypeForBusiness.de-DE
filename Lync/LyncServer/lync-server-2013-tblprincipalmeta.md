---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9b067b9d04ecb32a3e43dbbd1f8435c00fa0c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="3b6f8-102">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b6f8-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b6f8-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="3b6f8-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="3b6f8-104">tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="3b6f8-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="3b6f8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b6f8-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="3b6f8-106">Column</span></span></th>
<th><span data-ttu-id="3b6f8-107">Typ</span><span class="sxs-lookup"><span data-stu-id="3b6f8-107">Type</span></span></th>
<th><span data-ttu-id="3b6f8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b6f8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b6f8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3b6f8-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3b6f8-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b6f8-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="3b6f8-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-113">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3b6f8-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-114">"True", wenn Haupt Zuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b6f8-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="3b6f8-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3b6f8-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-117">"True", wenn Prinzipal Attribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b6f8-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="3b6f8-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="3b6f8-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-120">"True", wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b6f8-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="3b6f8-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-122">int</span><span class="sxs-lookup"><span data-stu-id="3b6f8-122">int</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-123">Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b6f8-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="3b6f8-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-125">datetime</span><span class="sxs-lookup"><span data-stu-id="3b6f8-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-126">Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="3b6f8-127">Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b6f8-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="3b6f8-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-129">datetime</span><span class="sxs-lookup"><span data-stu-id="3b6f8-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-130">Zeitstempel für die nächste geplante Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="3b6f8-131">Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3b6f8-132">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="3b6f8-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b6f8-133">Spalte</span><span class="sxs-lookup"><span data-stu-id="3b6f8-133">Column</span></span></th>
<th><span data-ttu-id="3b6f8-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b6f8-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b6f8-135">prinID</span><span class="sxs-lookup"><span data-stu-id="3b6f8-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-136">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="3b6f8-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b6f8-137">prinID</span><span class="sxs-lookup"><span data-stu-id="3b6f8-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="3b6f8-138">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3b6f8-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

