---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902236"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="587d5-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="587d5-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="587d5-104">Principalmemberdifference enthält Änderungen der Gruppenmitgliedschaften (sowohl hinzugefügte als auch entfernte Mitglieder), die von der Active Directory Domain Services Sync später noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="587d5-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="587d5-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="587d5-105">**Columns**</span></span>

|<span data-ttu-id="587d5-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="587d5-106">**Column**</span></span>|<span data-ttu-id="587d5-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="587d5-107">**Type**</span></span>|<span data-ttu-id="587d5-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="587d5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="587d5-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="587d5-109">prinGuid</span></span>  <br/> |<span data-ttu-id="587d5-110">GUID, nicht null</span><span class="sxs-lookup"><span data-stu-id="587d5-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="587d5-111">Prinzipal-GUID der geänderten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="587d5-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="587d5-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="587d5-112">memberADPath</span></span>  <br/> |<span data-ttu-id="587d5-113">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="587d5-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="587d5-114">Distinguished Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="587d5-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="587d5-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="587d5-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="587d5-116">Bit, nicht null</span><span class="sxs-lookup"><span data-stu-id="587d5-116">bit, not null</span></span>  <br/> |<span data-ttu-id="587d5-117">False, wenn das Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="587d5-117">False if the member was added.</span></span> <span data-ttu-id="587d5-118">True, wenn das Element entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="587d5-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="587d5-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="587d5-119">**Key**</span></span>

|<span data-ttu-id="587d5-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="587d5-120">**Column**</span></span>|<span data-ttu-id="587d5-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="587d5-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="587d5-122">\<PrinGuid memberADPath\></span><span class="sxs-lookup"><span data-stu-id="587d5-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="587d5-123">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="587d5-123">Primary key.</span></span>  <br/> |
   

