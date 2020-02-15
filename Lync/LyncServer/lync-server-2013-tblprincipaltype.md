---
title: 'Lync Server 2013: tblPrincipalType'
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
ms.openlocfilehash: 4da3af65a20d13ce4d4f1078e5ef76cbc67f402c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="f2be2-102">tblPrincipalType in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2be2-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2be2-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f2be2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f2be2-104">tblPrincipalType enthält Prinzipaltypen zur Kategorisierung des Inhalts der tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f2be2-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="f2be2-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="f2be2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2be2-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="f2be2-106">Column</span></span></th>
<th><span data-ttu-id="f2be2-107">Typ</span><span class="sxs-lookup"><span data-stu-id="f2be2-107">Type</span></span></th>
<th><span data-ttu-id="f2be2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2be2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f2be2-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="f2be2-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f2be2-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f2be2-111">Prinzipaltyp-ID</span><span class="sxs-lookup"><span data-stu-id="f2be2-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2be2-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="f2be2-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="f2be2-113">nvarchar (256), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f2be2-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f2be2-114">Beschreibung des Typs.</span><span class="sxs-lookup"><span data-stu-id="f2be2-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="f2be2-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="f2be2-116">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f2be2-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f2be2-117">TRUE, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2be2-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2be2-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="f2be2-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="f2be2-119">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="f2be2-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f2be2-120">TRUE, wenn es sich beim Typ um einen Benutzertyp handelt.</span><span class="sxs-lookup"><span data-stu-id="f2be2-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f2be2-121">Key</span><span class="sxs-lookup"><span data-stu-id="f2be2-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2be2-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="f2be2-122">Column</span></span></th>
<th><span data-ttu-id="f2be2-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2be2-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f2be2-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="f2be2-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="f2be2-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="f2be2-126">Prinzipalwerte</span><span class="sxs-lookup"><span data-stu-id="f2be2-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2be2-127">ID</span><span class="sxs-lookup"><span data-stu-id="f2be2-127">ID</span></span></th>
<th><span data-ttu-id="f2be2-128">Rolle</span><span class="sxs-lookup"><span data-stu-id="f2be2-128">Role</span></span></th>
<th><span data-ttu-id="f2be2-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2be2-129">Description</span></span></th>
<th><span data-ttu-id="f2be2-130">Benutzer</span><span class="sxs-lookup"><span data-stu-id="f2be2-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-131">1 </span><span class="sxs-lookup"><span data-stu-id="f2be2-131">1</span></span></p></td>
<td><p><span data-ttu-id="f2be2-132">Any</span><span class="sxs-lookup"><span data-stu-id="f2be2-132">Any</span></span></p></td>
<td><p><span data-ttu-id="f2be2-p101">Allgemeiner Prinzipal ohne bekannten Typ. Keine Verwendung in tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f2be2-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2be2-135">2 </span><span class="sxs-lookup"><span data-stu-id="f2be2-135">2</span></span></p></td>
<td><p><span data-ttu-id="f2be2-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="f2be2-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="f2be2-p102">Allgemeiner Prinzipal vom Typ Benutzer. Keine Verwendung in tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f2be2-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="f2be2-139">Ja</span><span class="sxs-lookup"><span data-stu-id="f2be2-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-140">3 </span><span class="sxs-lookup"><span data-stu-id="f2be2-140">3</span></span></p></td>
<td><p><span data-ttu-id="f2be2-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="f2be2-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="f2be2-p103">Allgemeiner Prinzipal mit Gruppensemantik. Keine Verwendung in tblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f2be2-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2be2-144">4 </span><span class="sxs-lookup"><span data-stu-id="f2be2-144">4</span></span></p></td>
<td><p><span data-ttu-id="f2be2-145">Multiswitch</span><span class="sxs-lookup"><span data-stu-id="f2be2-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="f2be2-146">Prinzipal, der intern vom Server für beständigen Chat verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f2be2-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-147">5 </span><span class="sxs-lookup"><span data-stu-id="f2be2-147">5</span></span></p></td>
<td><p><span data-ttu-id="f2be2-148">Benutzer</span><span class="sxs-lookup"><span data-stu-id="f2be2-148">User</span></span></p></td>
<td><p><span data-ttu-id="f2be2-149">Regelmäßiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f2be2-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="f2be2-150">Ja</span><span class="sxs-lookup"><span data-stu-id="f2be2-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2be2-151">8 </span><span class="sxs-lookup"><span data-stu-id="f2be2-151">8</span></span></p></td>
<td><p><span data-ttu-id="f2be2-152">Gleichstrom</span><span class="sxs-lookup"><span data-stu-id="f2be2-152">DC</span></span></p></td>
<td><p><span data-ttu-id="f2be2-153">Active Directory-Domänendienste Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="f2be2-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2be2-154">9 </span><span class="sxs-lookup"><span data-stu-id="f2be2-154">9</span></span></p></td>
<td><p><span data-ttu-id="f2be2-155">Group</span><span class="sxs-lookup"><span data-stu-id="f2be2-155">Group</span></span></p></td>
<td><p><span data-ttu-id="f2be2-156">Active Directory-Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="f2be2-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2be2-157">10 </span><span class="sxs-lookup"><span data-stu-id="f2be2-157">10</span></span></p></td>
<td><p><span data-ttu-id="f2be2-158">Ordner</span><span class="sxs-lookup"><span data-stu-id="f2be2-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="f2be2-159">Active Directory-Container oder Organisationseinheit</span><span class="sxs-lookup"><span data-stu-id="f2be2-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f2be2-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2be2-160">See Also</span></span>


[<span data-ttu-id="f2be2-161">tblPrincipal in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2be2-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

