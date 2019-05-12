---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: TblPrincipalAffiliations enthält die prinzipalzuordnungen, die Mitgliedschaften in Standorten, einschließlich Active Directory-Domänendienste-Sicherheitsgruppen, in Active Directory-Containern und in Domänen beschreiben.
ms.openlocfilehash: fb1bd8eb7291ba001a5c23240c2de70aaff048b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929819"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="2295c-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="2295c-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="2295c-104">TblPrincipalAffiliations enthält die prinzipalzuordnungen, die Mitgliedschaften in Standorten, einschließlich Active Directory-Domänendienste-Sicherheitsgruppen, in Active Directory-Containern und in Domänen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2295c-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="2295c-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="2295c-105">**Columns**</span></span>

|<span data-ttu-id="2295c-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2295c-106">**Column**</span></span>|<span data-ttu-id="2295c-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2295c-107">**Type**</span></span>|<span data-ttu-id="2295c-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2295c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2295c-109">principalID</span><span class="sxs-lookup"><span data-stu-id="2295c-109">principalID</span></span>  <br/> |<span data-ttu-id="2295c-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2295c-110">int, not null</span></span>  <br/> |<span data-ttu-id="2295c-111">Die ID des zugeordneten Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="2295c-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="2295c-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="2295c-112">affiliationID</span></span>  <br/> |<span data-ttu-id="2295c-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2295c-113">int, not null</span></span>  <br/> |<span data-ttu-id="2295c-114">ID des Prinzipals, der die Zuordnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="2295c-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="2295c-115">Jedes Sicherheitsprinzipal (mit Ausnahme der System-Benutzer-Typen) hat ein Self Zugehörigkeit sowie.</span><span class="sxs-lookup"><span data-stu-id="2295c-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="2295c-116">Index</span><span class="sxs-lookup"><span data-stu-id="2295c-116">index</span></span>  <br/> |<span data-ttu-id="2295c-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2295c-117">int, not null</span></span>  <br/> |<span data-ttu-id="2295c-118">Index.</span><span class="sxs-lookup"><span data-stu-id="2295c-118">Index.</span></span> <span data-ttu-id="2295c-119">Der Wert für Self zugehörigkeiten ist-1, und für die anderen zugehörigkeiten erhöht sequenziell von 1 innerhalb der einzelnen \<PrincipalID AffiliationId\> Bucket.</span><span class="sxs-lookup"><span data-stu-id="2295c-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="2295c-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="2295c-120">updatedBy</span></span>  <br/> |<span data-ttu-id="2295c-121">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="2295c-121">int, not null</span></span>  <br/> |<span data-ttu-id="2295c-122">Prinzipal, die das neueste Update haben.</span><span class="sxs-lookup"><span data-stu-id="2295c-122">Principal that did the latest update.</span></span> <span data-ttu-id="2295c-123">Dies ist in der Regel 1 fest, was bedeutet, Active Directory-Synchronisierung dass.</span><span class="sxs-lookup"><span data-stu-id="2295c-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="2295c-124">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="2295c-124">**Keys**</span></span>

|<span data-ttu-id="2295c-125">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="2295c-125">**Columns**</span></span>|<span data-ttu-id="2295c-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2295c-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2295c-127">\<PrincipalID, Index, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="2295c-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="2295c-128">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="2295c-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2295c-129">principalID</span><span class="sxs-lookup"><span data-stu-id="2295c-129">principalID</span></span>  <br/> |<span data-ttu-id="2295c-130">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2295c-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="2295c-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="2295c-131">affiliationID</span></span>  <br/> |<span data-ttu-id="2295c-132">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2295c-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

