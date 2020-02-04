---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="b5aac-102">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5aac-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5aac-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b5aac-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b5aac-104">tblPrincipalMeta enthält die Prinzipale, die aus den Active Directory-Domänendiensten aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b5aac-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="b5aac-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="b5aac-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5aac-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="b5aac-106">Column</span></span></th>
<th><span data-ttu-id="b5aac-107">Typ</span><span class="sxs-lookup"><span data-stu-id="b5aac-107">Type</span></span></th>
<th><span data-ttu-id="b5aac-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5aac-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5aac-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b5aac-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="b5aac-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b5aac-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b5aac-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="b5aac-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5aac-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="b5aac-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="b5aac-113">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b5aac-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b5aac-114">"True", wenn Haupt Zuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b5aac-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5aac-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="b5aac-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="b5aac-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b5aac-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b5aac-117">"True", wenn Prinzipal Attribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b5aac-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5aac-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="b5aac-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="b5aac-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="b5aac-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b5aac-120">"True", wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="b5aac-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5aac-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="b5aac-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="b5aac-122">int</span><span class="sxs-lookup"><span data-stu-id="b5aac-122">int</span></span></p></td>
<td><p><span data-ttu-id="b5aac-123">Die Anzahl der Versuche, den Prinzipal von AD DS zu aktualisieren, die bisher geschehen sind.</span><span class="sxs-lookup"><span data-stu-id="b5aac-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5aac-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="b5aac-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="b5aac-125">datetime</span><span class="sxs-lookup"><span data-stu-id="b5aac-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5aac-126">Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b5aac-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="b5aac-127">Kann NULL sein, wenn noch keine Aktualisierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="b5aac-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5aac-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="b5aac-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="b5aac-129">datetime</span><span class="sxs-lookup"><span data-stu-id="b5aac-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5aac-130">Zeitstempel für die nächste geplante Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="b5aac-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="b5aac-131">Kann NULL sein, wenn keine weitere Aktualisierung geplant wurde.</span><span class="sxs-lookup"><span data-stu-id="b5aac-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b5aac-132">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="b5aac-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5aac-133">Spalte</span><span class="sxs-lookup"><span data-stu-id="b5aac-133">Column</span></span></th>
<th><span data-ttu-id="b5aac-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5aac-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5aac-135">prinID</span><span class="sxs-lookup"><span data-stu-id="b5aac-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="b5aac-136">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="b5aac-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5aac-137">prinID</span><span class="sxs-lookup"><span data-stu-id="b5aac-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="b5aac-138">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b5aac-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

