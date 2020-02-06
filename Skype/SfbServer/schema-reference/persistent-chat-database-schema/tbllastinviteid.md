---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814573"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="67cba-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="67cba-103">tblLastInviteId</span></span>
 
<span data-ttu-id="67cba-104">tblLastInviteId enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.</span><span class="sxs-lookup"><span data-stu-id="67cba-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="67cba-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="67cba-105">**Columns**</span></span>

|<span data-ttu-id="67cba-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="67cba-106">**Column**</span></span>|<span data-ttu-id="67cba-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="67cba-107">**Type**</span></span>|<span data-ttu-id="67cba-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="67cba-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67cba-109">prinID</span><span class="sxs-lookup"><span data-stu-id="67cba-109">prinID</span></span>  <br/> |<span data-ttu-id="67cba-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="67cba-110">int, not null</span></span>  <br/> |<span data-ttu-id="67cba-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="67cba-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="67cba-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="67cba-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="67cba-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="67cba-113">int, not null</span></span>  <br/> |<span data-ttu-id="67cba-114">Zuletzt verwendete Einladungs-ID.</span><span class="sxs-lookup"><span data-stu-id="67cba-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="67cba-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="67cba-115">**Keys**</span></span>

|<span data-ttu-id="67cba-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="67cba-116">**Column**</span></span>|<span data-ttu-id="67cba-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="67cba-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67cba-118">prinID</span><span class="sxs-lookup"><span data-stu-id="67cba-118">prinID</span></span>  <br/> |<span data-ttu-id="67cba-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="67cba-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="67cba-120">prinID</span><span class="sxs-lookup"><span data-stu-id="67cba-120">prinID</span></span>  <br/> |<span data-ttu-id="67cba-121">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="67cba-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="67cba-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67cba-122">See also</span></span>

[<span data-ttu-id="67cba-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="67cba-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
