---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: TblPrincipalType enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle.
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212439"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="3f76a-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="3f76a-103">tblPrincipalType</span></span>
 
<span data-ttu-id="3f76a-104">TblPrincipalType enthält Prinzipaltypen zur Kategorisierung in der TblPrincipal-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3f76a-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="3f76a-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="3f76a-105">**Columns**</span></span>

|<span data-ttu-id="3f76a-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3f76a-106">**Column**</span></span>|<span data-ttu-id="3f76a-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3f76a-107">**Type**</span></span>|<span data-ttu-id="3f76a-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3f76a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f76a-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="3f76a-109">ptypeID</span></span>  <br/> |<span data-ttu-id="3f76a-110">Smallint, nicht null</span><span class="sxs-lookup"><span data-stu-id="3f76a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="3f76a-111">Prinzipaltyp-ID</span><span class="sxs-lookup"><span data-stu-id="3f76a-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="3f76a-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="3f76a-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="3f76a-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="3f76a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="3f76a-114">Beschreibung des Typs.</span><span class="sxs-lookup"><span data-stu-id="3f76a-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="3f76a-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="3f76a-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="3f76a-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="3f76a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3f76a-117">True, wenn der Typ den Prinzipalen entspricht, die zu internen Zwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f76a-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="3f76a-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="3f76a-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="3f76a-119">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="3f76a-119">bit, not null</span></span>  <br/> |<span data-ttu-id="3f76a-120">True, wenn der Typ einen Benutzertyp handelt.</span><span class="sxs-lookup"><span data-stu-id="3f76a-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="3f76a-121">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="3f76a-121">**Key**</span></span>

|<span data-ttu-id="3f76a-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3f76a-122">**Column**</span></span>|<span data-ttu-id="3f76a-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3f76a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f76a-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="3f76a-124">ptypeID</span></span>  <br/> |<span data-ttu-id="3f76a-125">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="3f76a-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="3f76a-126">**Prinzipalwerte**</span><span class="sxs-lookup"><span data-stu-id="3f76a-126">**Principal Values**</span></span>

|<span data-ttu-id="3f76a-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="3f76a-127">**ID**</span></span>|<span data-ttu-id="3f76a-128">**Rolle**</span><span class="sxs-lookup"><span data-stu-id="3f76a-128">**Role**</span></span>|<span data-ttu-id="3f76a-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3f76a-129">**Description**</span></span>|<span data-ttu-id="3f76a-130">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="3f76a-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f76a-131">1</span><span class="sxs-lookup"><span data-stu-id="3f76a-131">1</span></span>  <br/> |<span data-ttu-id="3f76a-132">Beliebig</span><span class="sxs-lookup"><span data-stu-id="3f76a-132">Any</span></span>  <br/> |<span data-ttu-id="3f76a-133">Generische Principal mit kein bekannter Typ.</span><span class="sxs-lookup"><span data-stu-id="3f76a-133">Generic principal with no known type.</span></span> <span data-ttu-id="3f76a-134">In der TblPrincipal-Tabelle verwendet nicht.</span><span class="sxs-lookup"><span data-stu-id="3f76a-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="3f76a-135">2</span><span class="sxs-lookup"><span data-stu-id="3f76a-135">2</span></span>  <br/> |<span data-ttu-id="3f76a-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="3f76a-136">AnyUser</span></span>  <br/> |<span data-ttu-id="3f76a-137">Generische Prinzipal vom Benutzertyp.</span><span class="sxs-lookup"><span data-stu-id="3f76a-137">Generic principal of user type.</span></span> <span data-ttu-id="3f76a-138">In der TblPrincipal-Tabelle verwendet nicht.</span><span class="sxs-lookup"><span data-stu-id="3f76a-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="3f76a-139">Ja</span><span class="sxs-lookup"><span data-stu-id="3f76a-139">Yes</span></span>  <br/> |
|<span data-ttu-id="3f76a-140">3</span><span class="sxs-lookup"><span data-stu-id="3f76a-140">3</span></span>  <br/> |<span data-ttu-id="3f76a-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="3f76a-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="3f76a-142">Generische Prinzipal semantische-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="3f76a-142">Generic principal with group semantic.</span></span> <span data-ttu-id="3f76a-143">In der TblPrincipal-Tabelle verwendet nicht.</span><span class="sxs-lookup"><span data-stu-id="3f76a-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="3f76a-144">4</span><span class="sxs-lookup"><span data-stu-id="3f76a-144">4</span></span>  <br/> |<span data-ttu-id="3f76a-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="3f76a-145">SystemUser</span></span>  <br/> |<span data-ttu-id="3f76a-146">Intern von Persistent Chat Server verwendeter Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="3f76a-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="3f76a-147">5</span><span class="sxs-lookup"><span data-stu-id="3f76a-147">5</span></span>  <br/> |<span data-ttu-id="3f76a-148">User</span><span class="sxs-lookup"><span data-stu-id="3f76a-148">User</span></span>  <br/> |<span data-ttu-id="3f76a-149">Regelmäßiger Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3f76a-149">Regular user.</span></span>  <br/> |<span data-ttu-id="3f76a-150">Ja</span><span class="sxs-lookup"><span data-stu-id="3f76a-150">Yes</span></span>  <br/> |
|<span data-ttu-id="3f76a-151">8</span><span class="sxs-lookup"><span data-stu-id="3f76a-151">8</span></span>  <br/> |<span data-ttu-id="3f76a-152">DC</span><span class="sxs-lookup"><span data-stu-id="3f76a-152">DC</span></span>  <br/> |<span data-ttu-id="3f76a-153">Active Directory-Domänendienste-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="3f76a-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="3f76a-154">9</span><span class="sxs-lookup"><span data-stu-id="3f76a-154">9</span></span>  <br/> |<span data-ttu-id="3f76a-155">Gruppe</span><span class="sxs-lookup"><span data-stu-id="3f76a-155">Group</span></span>  <br/> |<span data-ttu-id="3f76a-156">Active Directory-Sicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="3f76a-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="3f76a-157">10</span><span class="sxs-lookup"><span data-stu-id="3f76a-157">10</span></span>  <br/> |<span data-ttu-id="3f76a-158">Ordner</span><span class="sxs-lookup"><span data-stu-id="3f76a-158">Folder</span></span>  <br/> |<span data-ttu-id="3f76a-159">Active Directory-Container oder Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="3f76a-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="3f76a-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f76a-160">See also</span></span>

[<span data-ttu-id="3f76a-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="3f76a-161">tblPrincipal</span></span>](tblprincipal.md)
