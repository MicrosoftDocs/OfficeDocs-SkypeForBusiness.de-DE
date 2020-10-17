---
title: 'Lync Server 2013: tblPrincipalType'
description: 'Lync Server 2013: tblPrincipalType.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549861"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="70bb8-103">tblPrincipalType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70bb8-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70bb8-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="70bb8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="70bb8-105">tblPrincipalType enthält Prinzipaltypen zur Kategorisierung des Inhalts der tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="70bb8-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="70bb8-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="70bb8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70bb8-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="70bb8-107">Column</span></span></th>
<th><span data-ttu-id="70bb8-108">Typ</span><span class="sxs-lookup"><span data-stu-id="70bb8-108">Type</span></span></th>
<th><span data-ttu-id="70bb8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70bb8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-110">ptypeID</span><span class="sxs-lookup"><span data-stu-id="70bb8-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="70bb8-111">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="70bb8-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="70bb8-112">Prinzipaltyp-ID</span><span class="sxs-lookup"><span data-stu-id="70bb8-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70bb8-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="70bb8-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="70bb8-114">nvarchar (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="70bb8-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="70bb8-115">Beschreibung des Typs.</span><span class="sxs-lookup"><span data-stu-id="70bb8-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="70bb8-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="70bb8-117">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="70bb8-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="70bb8-118">TRUE, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70bb8-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70bb8-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="70bb8-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="70bb8-120">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="70bb8-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="70bb8-121">TRUE, wenn es sich beim Typ um einen Benutzertyp handelt.</span><span class="sxs-lookup"><span data-stu-id="70bb8-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="70bb8-122">Key</span><span class="sxs-lookup"><span data-stu-id="70bb8-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70bb8-123">Spalte</span><span class="sxs-lookup"><span data-stu-id="70bb8-123">Column</span></span></th>
<th><span data-ttu-id="70bb8-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70bb8-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-125">ptypeID</span><span class="sxs-lookup"><span data-stu-id="70bb8-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="70bb8-126">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="70bb8-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="70bb8-127">Prinzipalwerte</span><span class="sxs-lookup"><span data-stu-id="70bb8-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70bb8-128">ID</span><span class="sxs-lookup"><span data-stu-id="70bb8-128">ID</span></span></th>
<th><span data-ttu-id="70bb8-129">Rolle</span><span class="sxs-lookup"><span data-stu-id="70bb8-129">Role</span></span></th>
<th><span data-ttu-id="70bb8-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70bb8-130">Description</span></span></th>
<th><span data-ttu-id="70bb8-131">Benutzer</span><span class="sxs-lookup"><span data-stu-id="70bb8-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-132">1</span><span class="sxs-lookup"><span data-stu-id="70bb8-132">1</span></span></p></td>
<td><p><span data-ttu-id="70bb8-133">Beliebig</span><span class="sxs-lookup"><span data-stu-id="70bb8-133">Any</span></span></p></td>
<td><p><span data-ttu-id="70bb8-p101">Allgemeiner Prinzipal ohne bekannten Typ. Keine Verwendung in tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="70bb8-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70bb8-136">2</span><span class="sxs-lookup"><span data-stu-id="70bb8-136">2</span></span></p></td>
<td><p><span data-ttu-id="70bb8-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="70bb8-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="70bb8-p102">Allgemeiner Prinzipal vom Typ Benutzer. Keine Verwendung in tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="70bb8-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="70bb8-140">Ja</span><span class="sxs-lookup"><span data-stu-id="70bb8-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-141">3</span><span class="sxs-lookup"><span data-stu-id="70bb8-141">3</span></span></p></td>
<td><p><span data-ttu-id="70bb8-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="70bb8-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="70bb8-p103">Allgemeiner Prinzipal mit Gruppensemantik. Keine Verwendung in tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="70bb8-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70bb8-145">4 </span><span class="sxs-lookup"><span data-stu-id="70bb8-145">4</span></span></p></td>
<td><p><span data-ttu-id="70bb8-146">Multiswitch</span><span class="sxs-lookup"><span data-stu-id="70bb8-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="70bb8-147">Prinzipal, der intern vom Server für beständigen Chat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70bb8-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-148">5 </span><span class="sxs-lookup"><span data-stu-id="70bb8-148">5</span></span></p></td>
<td><p><span data-ttu-id="70bb8-149">Benutzer</span><span class="sxs-lookup"><span data-stu-id="70bb8-149">User</span></span></p></td>
<td><p><span data-ttu-id="70bb8-150">Regelmäßiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="70bb8-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="70bb8-151">Ja</span><span class="sxs-lookup"><span data-stu-id="70bb8-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70bb8-152">8 </span><span class="sxs-lookup"><span data-stu-id="70bb8-152">8</span></span></p></td>
<td><p><span data-ttu-id="70bb8-153">Gleichstrom</span><span class="sxs-lookup"><span data-stu-id="70bb8-153">DC</span></span></p></td>
<td><p><span data-ttu-id="70bb8-154">Active Directory-Domänendienste Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="70bb8-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70bb8-155">9 </span><span class="sxs-lookup"><span data-stu-id="70bb8-155">9</span></span></p></td>
<td><p><span data-ttu-id="70bb8-156">Gruppe</span><span class="sxs-lookup"><span data-stu-id="70bb8-156">Group</span></span></p></td>
<td><p><span data-ttu-id="70bb8-157">Active Directory-Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="70bb8-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70bb8-158">10 </span><span class="sxs-lookup"><span data-stu-id="70bb8-158">10</span></span></p></td>
<td><p><span data-ttu-id="70bb8-159">Ordner</span><span class="sxs-lookup"><span data-stu-id="70bb8-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="70bb8-160">Active Directory-Container oder Organisationseinheit</span><span class="sxs-lookup"><span data-stu-id="70bb8-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="70bb8-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70bb8-161">See Also</span></span>


[<span data-ttu-id="70bb8-162">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70bb8-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

