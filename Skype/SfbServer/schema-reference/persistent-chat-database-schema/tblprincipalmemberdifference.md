---
title: tblPrincipalMemberDifference
ms.reviewer: ''
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
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885554"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="85907-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="85907-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="85907-104">Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="85907-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="85907-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="85907-105">**Columns**</span></span>

|<span data-ttu-id="85907-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="85907-106">**Column**</span></span>|<span data-ttu-id="85907-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="85907-107">**Type**</span></span>|<span data-ttu-id="85907-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="85907-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85907-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="85907-109">prinGuid</span></span>  <br/> |<span data-ttu-id="85907-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="85907-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="85907-111">Prinzipal-GUID der geänderten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="85907-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="85907-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="85907-112">memberADPath</span></span>  <br/> |<span data-ttu-id="85907-113">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="85907-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="85907-114">Distinguished Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="85907-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="85907-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="85907-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="85907-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="85907-116">bit, not null</span></span>  <br/> |<span data-ttu-id="85907-117">False, wenn das Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="85907-117">False if the member was added.</span></span> <span data-ttu-id="85907-118">True, wenn das Element entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="85907-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="85907-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="85907-119">**Key**</span></span>

|<span data-ttu-id="85907-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="85907-120">**Column**</span></span>|<span data-ttu-id="85907-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="85907-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85907-122">\<PrinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="85907-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="85907-123">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="85907-123">Primary key.</span></span>  <br/> |
   

