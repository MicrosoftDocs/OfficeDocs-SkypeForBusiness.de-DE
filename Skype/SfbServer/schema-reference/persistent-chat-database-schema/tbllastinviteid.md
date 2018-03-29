---
title: "\"tbllastinviteid\""
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: "\"tbllastinviteid\" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="10221-103">"tbllastinviteid"</span><span class="sxs-lookup"><span data-stu-id="10221-103">tblLastInviteId</span></span>
 
<span data-ttu-id="10221-104">"tbllastinviteid" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="10221-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="10221-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="10221-105">**Columns**</span></span>

|<span data-ttu-id="10221-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="10221-106">**Column**</span></span>|<span data-ttu-id="10221-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="10221-107">**Type**</span></span>|<span data-ttu-id="10221-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="10221-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10221-109">prinID</span><span class="sxs-lookup"><span data-stu-id="10221-109">prinID</span></span>  <br/> |<span data-ttu-id="10221-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="10221-110">int, not null</span></span>  <br/> |<span data-ttu-id="10221-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="10221-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="10221-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="10221-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="10221-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="10221-113">int, not null</span></span>  <br/> |<span data-ttu-id="10221-114">Zuletzt verwendete Invite-ID.</span><span class="sxs-lookup"><span data-stu-id="10221-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="10221-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="10221-115">**Keys**</span></span>

|<span data-ttu-id="10221-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="10221-116">**Column**</span></span>|<span data-ttu-id="10221-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="10221-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10221-118">prinID</span><span class="sxs-lookup"><span data-stu-id="10221-118">prinID</span></span>  <br/> |<span data-ttu-id="10221-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="10221-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="10221-120">prinID</span><span class="sxs-lookup"><span data-stu-id="10221-120">prinID</span></span>  <br/> |<span data-ttu-id="10221-121">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="10221-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="10221-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10221-122">See also</span></span>

#### 

[<span data-ttu-id="10221-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="10221-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

