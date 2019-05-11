---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: "\"tbllastinviteid\" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929903"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="01886-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="01886-103">tblLastInviteId</span></span>
 
<span data-ttu-id="01886-104">"tbllastinviteid" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="01886-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="01886-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="01886-105">**Columns**</span></span>

|<span data-ttu-id="01886-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="01886-106">**Column**</span></span>|<span data-ttu-id="01886-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="01886-107">**Type**</span></span>|<span data-ttu-id="01886-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01886-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="01886-109">prinID</span><span class="sxs-lookup"><span data-stu-id="01886-109">prinID</span></span>  <br/> |<span data-ttu-id="01886-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="01886-110">int, not null</span></span>  <br/> |<span data-ttu-id="01886-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="01886-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="01886-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="01886-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="01886-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="01886-113">int, not null</span></span>  <br/> |<span data-ttu-id="01886-114">Zuletzt verwendete Invite-ID.</span><span class="sxs-lookup"><span data-stu-id="01886-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="01886-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="01886-115">**Keys**</span></span>

|<span data-ttu-id="01886-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="01886-116">**Column**</span></span>|<span data-ttu-id="01886-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01886-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="01886-118">prinID</span><span class="sxs-lookup"><span data-stu-id="01886-118">prinID</span></span>  <br/> |<span data-ttu-id="01886-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="01886-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="01886-120">prinID</span><span class="sxs-lookup"><span data-stu-id="01886-120">prinID</span></span>  <br/> |<span data-ttu-id="01886-121">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="01886-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="01886-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01886-122">See also</span></span>

[<span data-ttu-id="01886-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="01886-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
