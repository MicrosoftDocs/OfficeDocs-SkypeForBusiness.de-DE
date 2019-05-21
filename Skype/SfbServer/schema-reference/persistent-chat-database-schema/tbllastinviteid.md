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
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295356"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="a3d36-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="a3d36-103">tblLastInviteId</span></span>
 
<span data-ttu-id="a3d36-104">tblLastInviteId enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle verwendet) wurde.</span><span class="sxs-lookup"><span data-stu-id="a3d36-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="a3d36-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a3d36-105">**Columns**</span></span>

|<span data-ttu-id="a3d36-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a3d36-106">**Column**</span></span>|<span data-ttu-id="a3d36-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a3d36-107">**Type**</span></span>|<span data-ttu-id="a3d36-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a3d36-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3d36-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a3d36-109">prinID</span></span>  <br/> |<span data-ttu-id="a3d36-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a3d36-110">int, not null</span></span>  <br/> |<span data-ttu-id="a3d36-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="a3d36-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a3d36-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="a3d36-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="a3d36-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="a3d36-113">int, not null</span></span>  <br/> |<span data-ttu-id="a3d36-114">Zuletzt verwendete Einladungs-ID.</span><span class="sxs-lookup"><span data-stu-id="a3d36-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="a3d36-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a3d36-115">**Keys**</span></span>

|<span data-ttu-id="a3d36-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a3d36-116">**Column**</span></span>|<span data-ttu-id="a3d36-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a3d36-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3d36-118">prinID</span><span class="sxs-lookup"><span data-stu-id="a3d36-118">prinID</span></span>  <br/> |<span data-ttu-id="a3d36-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="a3d36-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a3d36-120">prinID</span><span class="sxs-lookup"><span data-stu-id="a3d36-120">prinID</span></span>  <br/> |<span data-ttu-id="a3d36-121">Fremdschlüssel mit Lookup in der tblPrincipal. prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a3d36-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a3d36-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3d36-122">See also</span></span>

[<span data-ttu-id="a3d36-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="a3d36-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
