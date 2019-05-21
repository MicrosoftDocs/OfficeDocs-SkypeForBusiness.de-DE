---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations enthält die Haupt Zuordnungen, die Mitgliedschaften an Speicherorten beschreiben, einschließlich Sicherheitsgruppen für Active Directory-Domänendienste, in Active Directory-Containern in Domänen.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295314"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="0dd07-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="0dd07-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="0dd07-104">tblPrincipalAffiliations enthält die Haupt Zuordnungen, die Mitgliedschaften an Speicherorten beschreiben, einschließlich Sicherheitsgruppen für Active Directory-Domänendienste, in Active Directory-Containern in Domänen.</span><span class="sxs-lookup"><span data-stu-id="0dd07-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="0dd07-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="0dd07-105">**Columns**</span></span>

|<span data-ttu-id="0dd07-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="0dd07-106">**Column**</span></span>|<span data-ttu-id="0dd07-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="0dd07-107">**Type**</span></span>|<span data-ttu-id="0dd07-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0dd07-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0dd07-109">Prinzipal-Nr</span><span class="sxs-lookup"><span data-stu-id="0dd07-109">principalID</span></span>  <br/> |<span data-ttu-id="0dd07-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="0dd07-110">int, not null</span></span>  <br/> |<span data-ttu-id="0dd07-111">Die ID des verbundenen Prinzipals.</span><span class="sxs-lookup"><span data-stu-id="0dd07-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="0dd07-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="0dd07-112">affiliationID</span></span>  <br/> |<span data-ttu-id="0dd07-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="0dd07-113">int, not null</span></span>  <br/> |<span data-ttu-id="0dd07-114">Die ID des Prinzipals, der die Zuordnung darstellt.</span><span class="sxs-lookup"><span data-stu-id="0dd07-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="0dd07-115">Jeder Prinzipal (mit Ausnahme von System-User-Typen) hat ebenfalls eine Selbstzuordnung.</span><span class="sxs-lookup"><span data-stu-id="0dd07-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="0dd07-116">Index</span><span class="sxs-lookup"><span data-stu-id="0dd07-116">index</span></span>  <br/> |<span data-ttu-id="0dd07-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="0dd07-117">int, not null</span></span>  <br/> |<span data-ttu-id="0dd07-118">Index.</span><span class="sxs-lookup"><span data-stu-id="0dd07-118">Index.</span></span> <span data-ttu-id="0dd07-119">Der Wert für Self-Affiliations ist-1, und für die anderen Zuordnungen wird er sequenziell von 1 innerhalb der einzelnen \<Prinzipal-affiliationId\> -Buckets erhöht.</span><span class="sxs-lookup"><span data-stu-id="0dd07-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="0dd07-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="0dd07-120">updatedBy</span></span>  <br/> |<span data-ttu-id="0dd07-121">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="0dd07-121">int, not null</span></span>  <br/> |<span data-ttu-id="0dd07-122">Prinzipal, der das neueste Update durchführte.</span><span class="sxs-lookup"><span data-stu-id="0dd07-122">Principal that did the latest update.</span></span> <span data-ttu-id="0dd07-123">Dies ist normalerweise 1, was bedeutet, dass die Active Directory-Synchronisierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="0dd07-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="0dd07-124">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="0dd07-124">**Keys**</span></span>

|<span data-ttu-id="0dd07-125">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="0dd07-125">**Columns**</span></span>|<span data-ttu-id="0dd07-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0dd07-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0dd07-127">\<Prinzipal-, Index-, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="0dd07-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="0dd07-128">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="0dd07-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0dd07-129">Prinzipal-Nr</span><span class="sxs-lookup"><span data-stu-id="0dd07-129">principalID</span></span>  <br/> |<span data-ttu-id="0dd07-130">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0dd07-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="0dd07-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="0dd07-131">affiliationID</span></span>  <br/> |<span data-ttu-id="0dd07-132">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0dd07-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

