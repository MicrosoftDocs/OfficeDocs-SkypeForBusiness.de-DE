---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern in Active Directory-Domänendiensten).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295153"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="98eeb-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="98eeb-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="98eeb-104">tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern in Active Directory-Domänendiensten).</span><span class="sxs-lookup"><span data-stu-id="98eeb-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="98eeb-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="98eeb-105">**Columns**</span></span>

|<span data-ttu-id="98eeb-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="98eeb-106">**Column**</span></span>|<span data-ttu-id="98eeb-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="98eeb-107">**Type**</span></span>|<span data-ttu-id="98eeb-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="98eeb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98eeb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="98eeb-109">prinID</span></span>  <br/> |<span data-ttu-id="98eeb-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="98eeb-110">int, not null</span></span>  <br/> |<span data-ttu-id="98eeb-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="98eeb-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="98eeb-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="98eeb-112">affDescription</span></span>  <br/> |<span data-ttu-id="98eeb-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="98eeb-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="98eeb-114">Eine Zeichenfolge, die die Zuordnung kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="98eeb-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="98eeb-115">Das Format lautet: GUID: _{0}_ URI: _{1}_>-ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="98eeb-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="98eeb-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="98eeb-116">updatedBy</span></span>  <br/> |<span data-ttu-id="98eeb-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="98eeb-117">int, not null</span></span>  <br/> |<span data-ttu-id="98eeb-118">Die ID des Prinzipals, der diese Zeile aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="98eeb-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="98eeb-119">Es ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.</span><span class="sxs-lookup"><span data-stu-id="98eeb-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="98eeb-120">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="98eeb-120">**Keys**</span></span>

|<span data-ttu-id="98eeb-121">**Spalte (n)**</span><span class="sxs-lookup"><span data-stu-id="98eeb-121">**Column(s)**</span></span>|<span data-ttu-id="98eeb-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="98eeb-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98eeb-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="98eeb-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="98eeb-124">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="98eeb-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="98eeb-125">prinID</span><span class="sxs-lookup"><span data-stu-id="98eeb-125">prinID</span></span>  <br/> |<span data-ttu-id="98eeb-126">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="98eeb-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

