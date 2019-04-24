---
title: tblPrincipalAffiliations
ms.reviewer: ''
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
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212502"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="64fcc-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="64fcc-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="64fcc-104">TblPrincipalAffiliations enthält die prinzipalzuordnungen, die Mitgliedschaften in Standorten, einschließlich Active Directory-Domänendienste-Sicherheitsgruppen, in Active Directory-Containern und in Domänen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="64fcc-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="64fcc-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="64fcc-105">**Columns**</span></span>

|<span data-ttu-id="64fcc-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="64fcc-106">**Column**</span></span>|<span data-ttu-id="64fcc-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="64fcc-107">**Type**</span></span>|<span data-ttu-id="64fcc-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="64fcc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64fcc-109">principalID</span><span class="sxs-lookup"><span data-stu-id="64fcc-109">principalID</span></span>  <br/> |<span data-ttu-id="64fcc-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="64fcc-110">int, not null</span></span>  <br/> |<span data-ttu-id="64fcc-111">Die ID des zugeordneten Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="64fcc-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="64fcc-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="64fcc-112">affiliationID</span></span>  <br/> |<span data-ttu-id="64fcc-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="64fcc-113">int, not null</span></span>  <br/> |<span data-ttu-id="64fcc-114">ID des Prinzipals, der die Zuordnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="64fcc-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="64fcc-115">Jedes Sicherheitsprinzipal (mit Ausnahme der System-Benutzer-Typen) hat ein Self Zugehörigkeit sowie.</span><span class="sxs-lookup"><span data-stu-id="64fcc-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="64fcc-116">Index</span><span class="sxs-lookup"><span data-stu-id="64fcc-116">index</span></span>  <br/> |<span data-ttu-id="64fcc-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="64fcc-117">int, not null</span></span>  <br/> |<span data-ttu-id="64fcc-118">Index.</span><span class="sxs-lookup"><span data-stu-id="64fcc-118">Index.</span></span> <span data-ttu-id="64fcc-119">Der Wert für Self zugehörigkeiten ist-1, und für die anderen zugehörigkeiten erhöht sequenziell von 1 innerhalb der einzelnen \<PrincipalID AffiliationId\> Bucket.</span><span class="sxs-lookup"><span data-stu-id="64fcc-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="64fcc-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="64fcc-120">updatedBy</span></span>  <br/> |<span data-ttu-id="64fcc-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="64fcc-121">int, not null</span></span>  <br/> |<span data-ttu-id="64fcc-122">Prinzipal, die das neueste Update haben.</span><span class="sxs-lookup"><span data-stu-id="64fcc-122">Principal that did the latest update.</span></span> <span data-ttu-id="64fcc-123">Dies ist in der Regel 1 fest, was bedeutet, Active Directory-Synchronisierung dass.</span><span class="sxs-lookup"><span data-stu-id="64fcc-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="64fcc-124">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="64fcc-124">**Keys**</span></span>

|<span data-ttu-id="64fcc-125">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="64fcc-125">**Columns**</span></span>|<span data-ttu-id="64fcc-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="64fcc-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64fcc-127">\<PrincipalID, Index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="64fcc-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="64fcc-128">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="64fcc-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="64fcc-129">principalID</span><span class="sxs-lookup"><span data-stu-id="64fcc-129">principalID</span></span>  <br/> |<span data-ttu-id="64fcc-130">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="64fcc-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="64fcc-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="64fcc-131">affiliationID</span></span>  <br/> |<span data-ttu-id="64fcc-132">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="64fcc-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

