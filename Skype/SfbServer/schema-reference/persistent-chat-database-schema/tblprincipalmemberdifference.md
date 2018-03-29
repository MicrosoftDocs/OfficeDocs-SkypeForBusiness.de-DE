---
title: Principalmemberdifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="cc69b-103">Principalmemberdifference</span><span class="sxs-lookup"><span data-stu-id="cc69b-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="cc69b-104">Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="cc69b-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="cc69b-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="cc69b-105">**Columns**</span></span>

|<span data-ttu-id="cc69b-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cc69b-106">**Column**</span></span>|<span data-ttu-id="cc69b-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="cc69b-107">**Type**</span></span>|<span data-ttu-id="cc69b-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cc69b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cc69b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="cc69b-109">prinGuid</span></span>  <br/> |<span data-ttu-id="cc69b-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="cc69b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="cc69b-111">Prinzipal-GUID der geänderten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="cc69b-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="cc69b-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="cc69b-112">memberADPath</span></span>  <br/> |<span data-ttu-id="cc69b-113">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc69b-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="cc69b-114">Distinguished Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="cc69b-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="cc69b-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="cc69b-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="cc69b-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="cc69b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="cc69b-117">False, wenn das Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc69b-117">False if the member was added.</span></span> <span data-ttu-id="cc69b-118">True, wenn das Element entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc69b-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="cc69b-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="cc69b-119">**Key**</span></span>

|<span data-ttu-id="cc69b-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cc69b-120">**Column**</span></span>|<span data-ttu-id="cc69b-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cc69b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc69b-122">\<PrinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="cc69b-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="cc69b-123">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="cc69b-123">Primary key.</span></span>  <br/> |
   

