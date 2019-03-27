---
title: tblLastInviteId
ms.reviewer: ''
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
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873937"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="c9f8d-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c9f8d-103">tblLastInviteId</span></span>
 
<span data-ttu-id="c9f8d-104">"tbllastinviteid" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="c9f8d-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-105">**Columns**</span></span>

|<span data-ttu-id="c9f8d-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-106">**Column**</span></span>|<span data-ttu-id="c9f8d-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-107">**Type**</span></span>|<span data-ttu-id="c9f8d-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9f8d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c9f8d-109">prinID</span></span>  <br/> |<span data-ttu-id="c9f8d-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="c9f8d-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9f8d-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c9f8d-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="c9f8d-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="c9f8d-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="c9f8d-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9f8d-114">Zuletzt verwendete Invite-ID.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="c9f8d-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-115">**Keys**</span></span>

|<span data-ttu-id="c9f8d-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-116">**Column**</span></span>|<span data-ttu-id="c9f8d-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c9f8d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f8d-118">prinID</span><span class="sxs-lookup"><span data-stu-id="c9f8d-118">prinID</span></span>  <br/> |<span data-ttu-id="c9f8d-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9f8d-120">prinID</span><span class="sxs-lookup"><span data-stu-id="c9f8d-120">prinID</span></span>  <br/> |<span data-ttu-id="c9f8d-121">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9f8d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9f8d-122">See also</span></span>

[<span data-ttu-id="c9f8d-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c9f8d-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
