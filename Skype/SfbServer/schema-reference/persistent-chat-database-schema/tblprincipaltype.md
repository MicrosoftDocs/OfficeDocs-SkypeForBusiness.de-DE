---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295244"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="86245-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="86245-103">tblPrincipalType</span></span>
 
<span data-ttu-id="86245-104">tblPrincipalType enthält Prinzipaltypen, um zu kategorisieren, was in der tblPrincipal-Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="86245-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="86245-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="86245-105">**Columns**</span></span>

|<span data-ttu-id="86245-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="86245-106">**Column**</span></span>|<span data-ttu-id="86245-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="86245-107">**Type**</span></span>|<span data-ttu-id="86245-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="86245-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="86245-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="86245-109">ptypeID</span></span>  <br/> |<span data-ttu-id="86245-110">smallint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="86245-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="86245-111">Prinzipaltyp-ID.</span><span class="sxs-lookup"><span data-stu-id="86245-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="86245-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="86245-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="86245-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="86245-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="86245-114">Beschreibung des Typs.</span><span class="sxs-lookup"><span data-stu-id="86245-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="86245-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="86245-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="86245-116">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="86245-116">bit, not null</span></span>  <br/> |<span data-ttu-id="86245-117">"True", wenn der Typ den Prinzipalen entspricht, die für interne Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="86245-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="86245-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="86245-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="86245-119">Bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="86245-119">bit, not null</span></span>  <br/> |<span data-ttu-id="86245-120">"True", wenn es sich bei dem Typ um einen Benutzertyp handelt.</span><span class="sxs-lookup"><span data-stu-id="86245-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="86245-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="86245-121">**Key**</span></span>

|<span data-ttu-id="86245-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="86245-122">**Column**</span></span>|<span data-ttu-id="86245-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="86245-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86245-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="86245-124">ptypeID</span></span>  <br/> |<span data-ttu-id="86245-125">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="86245-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="86245-126">**Prinzipal Werte**</span><span class="sxs-lookup"><span data-stu-id="86245-126">**Principal Values**</span></span>

|<span data-ttu-id="86245-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="86245-127">**ID**</span></span>|<span data-ttu-id="86245-128">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="86245-128">**Role**</span></span>|<span data-ttu-id="86245-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="86245-129">**Description**</span></span>|<span data-ttu-id="86245-130">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="86245-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="86245-131">1</span><span class="sxs-lookup"><span data-stu-id="86245-131">1</span></span>  <br/> |<span data-ttu-id="86245-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="86245-132">Any</span></span>  <br/> |<span data-ttu-id="86245-133">Generischer Prinzipal ohne bekannten Typ.</span><span class="sxs-lookup"><span data-stu-id="86245-133">Generic principal with no known type.</span></span> <span data-ttu-id="86245-134">Wird in der tblPrincipal-Tabelle nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="86245-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="86245-135">2</span><span class="sxs-lookup"><span data-stu-id="86245-135">2</span></span>  <br/> |<span data-ttu-id="86245-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="86245-136">AnyUser</span></span>  <br/> |<span data-ttu-id="86245-137">Generisches Prinzipal des Benutzertyps.</span><span class="sxs-lookup"><span data-stu-id="86245-137">Generic principal of user type.</span></span> <span data-ttu-id="86245-138">Wird in der tblPrincipal-Tabelle nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="86245-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="86245-139">Ja</span><span class="sxs-lookup"><span data-stu-id="86245-139">Yes</span></span>  <br/> |
|<span data-ttu-id="86245-140">3</span><span class="sxs-lookup"><span data-stu-id="86245-140">3</span></span>  <br/> |<span data-ttu-id="86245-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="86245-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="86245-142">Generischer Prinzipal mit Gruppen Semantik</span><span class="sxs-lookup"><span data-stu-id="86245-142">Generic principal with group semantic.</span></span> <span data-ttu-id="86245-143">Wird in der tblPrincipal-Tabelle nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="86245-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="86245-144">4</span><span class="sxs-lookup"><span data-stu-id="86245-144">4</span></span>  <br/> |<span data-ttu-id="86245-145">Multiswitch</span><span class="sxs-lookup"><span data-stu-id="86245-145">SystemUser</span></span>  <br/> |<span data-ttu-id="86245-146">Prinzipal, der intern vom beständigen Chat Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86245-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="86245-147">5</span><span class="sxs-lookup"><span data-stu-id="86245-147">5</span></span>  <br/> |<span data-ttu-id="86245-148">User</span><span class="sxs-lookup"><span data-stu-id="86245-148">User</span></span>  <br/> |<span data-ttu-id="86245-149">Normaler Benutzer.</span><span class="sxs-lookup"><span data-stu-id="86245-149">Regular user.</span></span>  <br/> |<span data-ttu-id="86245-150">Ja</span><span class="sxs-lookup"><span data-stu-id="86245-150">Yes</span></span>  <br/> |
|<span data-ttu-id="86245-151">8</span><span class="sxs-lookup"><span data-stu-id="86245-151">8</span></span>  <br/> |<span data-ttu-id="86245-152">DC</span><span class="sxs-lookup"><span data-stu-id="86245-152">DC</span></span>  <br/> |<span data-ttu-id="86245-153">Active Directory-Domänendienste-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="86245-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="86245-154">9</span><span class="sxs-lookup"><span data-stu-id="86245-154">9</span></span>  <br/> |<span data-ttu-id="86245-155">Gruppe</span><span class="sxs-lookup"><span data-stu-id="86245-155">Group</span></span>  <br/> |<span data-ttu-id="86245-156">Active Directory-Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="86245-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="86245-157">10</span><span class="sxs-lookup"><span data-stu-id="86245-157">10</span></span>  <br/> |<span data-ttu-id="86245-158">Ordner</span><span class="sxs-lookup"><span data-stu-id="86245-158">Folder</span></span>  <br/> |<span data-ttu-id="86245-159">Active Directory-Container oder-Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="86245-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="86245-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86245-160">See also</span></span>

[<span data-ttu-id="86245-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="86245-161">tblPrincipal</span></span>](tblprincipal.md)
