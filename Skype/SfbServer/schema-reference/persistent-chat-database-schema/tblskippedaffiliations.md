---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: "\"Skippedaffiliations\" enthält die zugehörigkeiten, die (gewöhnlich aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten."
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212607"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="d9223-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="d9223-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="d9223-104">"Skippedaffiliations" enthält die zugehörigkeiten, die (gewöhnlich aufgrund von Active Directory-Domänendienste-Zugriffsfehlern) nicht gelesen werden konnten.</span><span class="sxs-lookup"><span data-stu-id="d9223-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="d9223-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d9223-105">**Columns**</span></span>

|<span data-ttu-id="d9223-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d9223-106">**Column**</span></span>|<span data-ttu-id="d9223-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d9223-107">**Type**</span></span>|<span data-ttu-id="d9223-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d9223-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d9223-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d9223-109">prinID</span></span>  <br/> |<span data-ttu-id="d9223-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d9223-110">int, not null</span></span>  <br/> |<span data-ttu-id="d9223-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="d9223-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d9223-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="d9223-112">affDescription</span></span>  <br/> |<span data-ttu-id="d9223-113">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="d9223-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d9223-114">Eine Zeichenfolge, die die Zuordnung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d9223-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="d9223-115">Das Format lautet: Guid: _{0}_ Uri: _{1}_>-Id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="d9223-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="d9223-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="d9223-116">updatedBy</span></span>  <br/> |<span data-ttu-id="d9223-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d9223-117">int, not null</span></span>  <br/> |<span data-ttu-id="d9223-118">ID des Prinzipals, der diese Zeile aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d9223-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="d9223-119">Es ist immer 1 (Systembenutzer), da Active Directory-Synchronisierung die einzige Quelle für diese Einträge ist.</span><span class="sxs-lookup"><span data-stu-id="d9223-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="d9223-120">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="d9223-120">**Keys**</span></span>

|<span data-ttu-id="d9223-121">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d9223-121">**Column(s)**</span></span>|<span data-ttu-id="d9223-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d9223-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9223-123">\<PrinID affDescription\></span><span class="sxs-lookup"><span data-stu-id="d9223-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="d9223-124">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d9223-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d9223-125">prinID</span><span class="sxs-lookup"><span data-stu-id="d9223-125">prinID</span></span>  <br/> |<span data-ttu-id="d9223-126">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d9223-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

