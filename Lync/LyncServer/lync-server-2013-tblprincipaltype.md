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
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="7fa2d-102">tblPrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa2d-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fa2d-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7fa2d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7fa2d-104">tblPrincipalType enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="7fa2d-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="7fa2d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fa2d-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="7fa2d-106">Column</span></span></th>
<th><span data-ttu-id="7fa2d-107">Typ</span><span class="sxs-lookup"><span data-stu-id="7fa2d-107">Type</span></span></th>
<th><span data-ttu-id="7fa2d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fa2d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="7fa2d-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7fa2d-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-111">Prinzipaltyp-ID.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fa2d-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="7fa2d-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7fa2d-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-114">Beschreibung des Typs.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="7fa2d-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7fa2d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-117">"True", wenn der Typ den Prinzipalen entspricht, die für interne Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fa2d-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="7fa2d-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7fa2d-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-120">"True", wenn es sich bei dem Typ um einen Benutzertyp handelt.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7fa2d-121">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7fa2d-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fa2d-122">Spalte</span><span class="sxs-lookup"><span data-stu-id="7fa2d-122">Column</span></span></th>
<th><span data-ttu-id="7fa2d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fa2d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="7fa2d-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="7fa2d-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="7fa2d-126">Prinzipal Werte</span><span class="sxs-lookup"><span data-stu-id="7fa2d-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fa2d-127">ID</span><span class="sxs-lookup"><span data-stu-id="7fa2d-127">ID</span></span></th>
<th><span data-ttu-id="7fa2d-128">Rolle</span><span class="sxs-lookup"><span data-stu-id="7fa2d-128">Role</span></span></th>
<th><span data-ttu-id="7fa2d-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fa2d-129">Description</span></span></th>
<th><span data-ttu-id="7fa2d-130">User</span><span class="sxs-lookup"><span data-stu-id="7fa2d-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-131">1</span><span class="sxs-lookup"><span data-stu-id="7fa2d-131">1</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="7fa2d-132">Any</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-133">Generischer Prinzipal ohne bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-133">Generic principal with no known type.</span></span> <span data-ttu-id="7fa2d-134">Wird in der tblPrincipal-Tabelle nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fa2d-135">2</span><span class="sxs-lookup"><span data-stu-id="7fa2d-135">2</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="7fa2d-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-137">Generisches Prinzipal des Benutzertyps.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-137">Generic principal of user type.</span></span> <span data-ttu-id="7fa2d-138">Wird in der tblPrincipal-Tabelle nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-139">Ja</span><span class="sxs-lookup"><span data-stu-id="7fa2d-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-140">3</span><span class="sxs-lookup"><span data-stu-id="7fa2d-140">3</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="7fa2d-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-142">Generischer Prinzipal mit Gruppen Semantik</span><span class="sxs-lookup"><span data-stu-id="7fa2d-142">Generic principal with group semantic.</span></span> <span data-ttu-id="7fa2d-143">Wird in der tblPrincipal-Tabelle nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fa2d-144">4</span><span class="sxs-lookup"><span data-stu-id="7fa2d-144">4</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-145">Multiswitch</span><span class="sxs-lookup"><span data-stu-id="7fa2d-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-146">Prinzipal, der intern vom beständigen Chat Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-147">5</span><span class="sxs-lookup"><span data-stu-id="7fa2d-147">5</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-148">Benutzer</span><span class="sxs-lookup"><span data-stu-id="7fa2d-148">User</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-149">Normaler Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-150">Ja</span><span class="sxs-lookup"><span data-stu-id="7fa2d-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fa2d-151">8</span><span class="sxs-lookup"><span data-stu-id="7fa2d-151">8</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-152">DC</span><span class="sxs-lookup"><span data-stu-id="7fa2d-152">DC</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-153">Active Directory-Domänendienste-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fa2d-154">9</span><span class="sxs-lookup"><span data-stu-id="7fa2d-154">9</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-155">Gruppe</span><span class="sxs-lookup"><span data-stu-id="7fa2d-155">Group</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-156">Active Directory-Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fa2d-157">10</span><span class="sxs-lookup"><span data-stu-id="7fa2d-157">10</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-158">Ordner</span><span class="sxs-lookup"><span data-stu-id="7fa2d-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="7fa2d-159">Active Directory-Container oder-Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="7fa2d-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7fa2d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fa2d-160">See Also</span></span>


[<span data-ttu-id="7fa2d-161">tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fa2d-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

