---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: TblPrincipalAffiliations enthält die prinzipalzuordnungen, die Mitgliedschaften in Standorten, einschließlich Active Directory-Domänendienste-Sicherheitsgruppen, in Active Directory-Containern und in Domänen beschreiben.
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="588ea-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="588ea-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="588ea-104">TblPrincipalAffiliations enthält die prinzipalzuordnungen, die Mitgliedschaften in Standorten, einschließlich Active Directory-Domänendienste-Sicherheitsgruppen, in Active Directory-Containern und in Domänen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="588ea-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="588ea-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="588ea-105">**Columns**</span></span>

|<span data-ttu-id="588ea-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="588ea-106">**Column**</span></span>|<span data-ttu-id="588ea-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="588ea-107">**Type**</span></span>|<span data-ttu-id="588ea-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="588ea-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="588ea-109">principalID</span><span class="sxs-lookup"><span data-stu-id="588ea-109">principalID</span></span>  <br/> |<span data-ttu-id="588ea-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="588ea-110">int, not null</span></span>  <br/> |<span data-ttu-id="588ea-111">Die ID des zugeordneten Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="588ea-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="588ea-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="588ea-112">affiliationID</span></span>  <br/> |<span data-ttu-id="588ea-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="588ea-113">int, not null</span></span>  <br/> |<span data-ttu-id="588ea-114">ID des Prinzipals, der die Zuordnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="588ea-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="588ea-115">Jedes Sicherheitsprinzipal (mit Ausnahme der System-Benutzer-Typen) hat ein Self Zugehörigkeit sowie.</span><span class="sxs-lookup"><span data-stu-id="588ea-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="588ea-116">Index</span><span class="sxs-lookup"><span data-stu-id="588ea-116">index</span></span>  <br/> |<span data-ttu-id="588ea-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="588ea-117">int, not null</span></span>  <br/> |<span data-ttu-id="588ea-118">Index.</span><span class="sxs-lookup"><span data-stu-id="588ea-118">Index.</span></span> <span data-ttu-id="588ea-119">Der Wert für Self zugehörigkeiten ist-1, und für die anderen zugehörigkeiten erhöht sequenziell von 1 innerhalb der einzelnen \<PrincipalID AffiliationId\> Bucket.</span><span class="sxs-lookup"><span data-stu-id="588ea-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="588ea-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="588ea-120">updatedBy</span></span>  <br/> |<span data-ttu-id="588ea-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="588ea-121">int, not null</span></span>  <br/> |<span data-ttu-id="588ea-122">Prinzipal, die das neueste Update haben.</span><span class="sxs-lookup"><span data-stu-id="588ea-122">Principal that did the latest update.</span></span> <span data-ttu-id="588ea-123">Dies ist in der Regel 1 fest, was bedeutet, Active Directory-Synchronisierung dass.</span><span class="sxs-lookup"><span data-stu-id="588ea-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="588ea-124">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="588ea-124">**Keys**</span></span>

|<span data-ttu-id="588ea-125">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="588ea-125">**Columns**</span></span>|<span data-ttu-id="588ea-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="588ea-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="588ea-127">\<PrincipalID, Index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="588ea-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="588ea-128">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="588ea-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="588ea-129">principalID</span><span class="sxs-lookup"><span data-stu-id="588ea-129">principalID</span></span>  <br/> |<span data-ttu-id="588ea-130">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="588ea-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="588ea-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="588ea-131">affiliationID</span></span>  <br/> |<span data-ttu-id="588ea-132">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="588ea-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

