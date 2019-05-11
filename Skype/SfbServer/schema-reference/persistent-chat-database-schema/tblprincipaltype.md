---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: TblPrincipalType enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle.
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924458"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="43059-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="43059-103">tblPrincipalType</span></span>
 
<span data-ttu-id="43059-104">TblPrincipalType enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43059-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="43059-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="43059-105">**Columns**</span></span>

|<span data-ttu-id="43059-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="43059-106">**Column**</span></span>|<span data-ttu-id="43059-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="43059-107">**Type**</span></span>|<span data-ttu-id="43059-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="43059-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="43059-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="43059-109">ptypeID</span></span>  <br/> |<span data-ttu-id="43059-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="43059-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="43059-111">Prinzipaltyp-ID</span><span class="sxs-lookup"><span data-stu-id="43059-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="43059-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="43059-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="43059-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="43059-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="43059-114">Beschreibung des Typs.</span><span class="sxs-lookup"><span data-stu-id="43059-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="43059-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="43059-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="43059-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="43059-116">bit, not null</span></span>  <br/> |<span data-ttu-id="43059-117">True, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43059-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="43059-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="43059-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="43059-119">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="43059-119">bit, not null</span></span>  <br/> |<span data-ttu-id="43059-120">True, wenn der Typ einen Benutzertyp handelt.</span><span class="sxs-lookup"><span data-stu-id="43059-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="43059-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="43059-121">**Key**</span></span>

|<span data-ttu-id="43059-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="43059-122">**Column**</span></span>|<span data-ttu-id="43059-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="43059-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43059-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="43059-124">ptypeID</span></span>  <br/> |<span data-ttu-id="43059-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="43059-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="43059-126">**Prinzipalwerte**</span><span class="sxs-lookup"><span data-stu-id="43059-126">**Principal Values**</span></span>

|<span data-ttu-id="43059-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="43059-127">**ID**</span></span>|<span data-ttu-id="43059-128">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="43059-128">**Role**</span></span>|<span data-ttu-id="43059-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="43059-129">**Description**</span></span>|<span data-ttu-id="43059-130">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="43059-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43059-131">1</span><span class="sxs-lookup"><span data-stu-id="43059-131">1</span></span>  <br/> |<span data-ttu-id="43059-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="43059-132">Any</span></span>  <br/> |<span data-ttu-id="43059-133">Generische Principal mit kein bekannter Typ.</span><span class="sxs-lookup"><span data-stu-id="43059-133">Generic principal with no known type.</span></span> <span data-ttu-id="43059-134">In der TblPrincipal-Tabelle verwendet nicht.</span><span class="sxs-lookup"><span data-stu-id="43059-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="43059-135">2</span><span class="sxs-lookup"><span data-stu-id="43059-135">2</span></span>  <br/> |<span data-ttu-id="43059-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="43059-136">AnyUser</span></span>  <br/> |<span data-ttu-id="43059-137">Generische Prinzipal vom Benutzertyp.</span><span class="sxs-lookup"><span data-stu-id="43059-137">Generic principal of user type.</span></span> <span data-ttu-id="43059-138">In der TblPrincipal-Tabelle verwendet nicht.</span><span class="sxs-lookup"><span data-stu-id="43059-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="43059-139">Ja</span><span class="sxs-lookup"><span data-stu-id="43059-139">Yes</span></span>  <br/> |
|<span data-ttu-id="43059-140">3</span><span class="sxs-lookup"><span data-stu-id="43059-140">3</span></span>  <br/> |<span data-ttu-id="43059-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="43059-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="43059-142">Generische Prinzipal semantische-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="43059-142">Generic principal with group semantic.</span></span> <span data-ttu-id="43059-143">In der TblPrincipal-Tabelle verwendet nicht.</span><span class="sxs-lookup"><span data-stu-id="43059-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="43059-144">4</span><span class="sxs-lookup"><span data-stu-id="43059-144">4</span></span>  <br/> |<span data-ttu-id="43059-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="43059-145">SystemUser</span></span>  <br/> |<span data-ttu-id="43059-146">Intern von Persistent Chat Server verwendeter Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="43059-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="43059-147">5</span><span class="sxs-lookup"><span data-stu-id="43059-147">5</span></span>  <br/> |<span data-ttu-id="43059-148">User</span><span class="sxs-lookup"><span data-stu-id="43059-148">User</span></span>  <br/> |<span data-ttu-id="43059-149">Regelmäßiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="43059-149">Regular user.</span></span>  <br/> |<span data-ttu-id="43059-150">Ja</span><span class="sxs-lookup"><span data-stu-id="43059-150">Yes</span></span>  <br/> |
|<span data-ttu-id="43059-151">8</span><span class="sxs-lookup"><span data-stu-id="43059-151">8</span></span>  <br/> |<span data-ttu-id="43059-152">DC</span><span class="sxs-lookup"><span data-stu-id="43059-152">DC</span></span>  <br/> |<span data-ttu-id="43059-153">Active Directory-Domänendienste-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="43059-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="43059-154">9</span><span class="sxs-lookup"><span data-stu-id="43059-154">9</span></span>  <br/> |<span data-ttu-id="43059-155">Gruppe</span><span class="sxs-lookup"><span data-stu-id="43059-155">Group</span></span>  <br/> |<span data-ttu-id="43059-156">Active Directory-Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="43059-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="43059-157">10</span><span class="sxs-lookup"><span data-stu-id="43059-157">10</span></span>  <br/> |<span data-ttu-id="43059-158">Ordner</span><span class="sxs-lookup"><span data-stu-id="43059-158">Folder</span></span>  <br/> |<span data-ttu-id="43059-159">Active Directory-Container oder Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="43059-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="43059-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43059-160">See also</span></span>

[<span data-ttu-id="43059-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="43059-161">tblPrincipal</span></span>](tblprincipal.md)
