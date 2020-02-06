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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern in Active Directory-Domänendiensten).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812013"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="4b2e7-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="4b2e7-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="4b2e7-104">tblSkippedAffiliations enthält die Zuordnungen, die nicht gelesen werden konnten (in der Regel aufgrund von Zugriffsfehlern in Active Directory-Domänendiensten).</span><span class="sxs-lookup"><span data-stu-id="4b2e7-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="4b2e7-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-105">**Columns**</span></span>

|<span data-ttu-id="4b2e7-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-106">**Column**</span></span>|<span data-ttu-id="4b2e7-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-107">**Type**</span></span>|<span data-ttu-id="4b2e7-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b2e7-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4b2e7-109">prinID</span></span>  <br/> |<span data-ttu-id="4b2e7-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4b2e7-110">int, not null</span></span>  <br/> |<span data-ttu-id="4b2e7-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="4b2e7-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="4b2e7-112">affDescription</span></span>  <br/> |<span data-ttu-id="4b2e7-113">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4b2e7-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="4b2e7-114">Eine Zeichenfolge, die die Zuordnung kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="4b2e7-115">Das Format lautet: GUID: _{0}_ URI: _{1}_>-ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="4b2e7-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="4b2e7-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="4b2e7-116">updatedBy</span></span>  <br/> |<span data-ttu-id="4b2e7-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="4b2e7-117">int, not null</span></span>  <br/> |<span data-ttu-id="4b2e7-118">Die ID des Prinzipals, der diese Zeile aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="4b2e7-119">Es ist immer 1 (Systembenutzer), da die Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="4b2e7-120">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-120">**Keys**</span></span>

|<span data-ttu-id="4b2e7-121">**Spalte (n)**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-121">**Column(s)**</span></span>|<span data-ttu-id="4b2e7-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4b2e7-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4b2e7-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="4b2e7-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="4b2e7-124">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="4b2e7-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4b2e7-125">prinID</span><span class="sxs-lookup"><span data-stu-id="4b2e7-125">prinID</span></span>  <br/> |<span data-ttu-id="4b2e7-126">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4b2e7-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

