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
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504852"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="1d7c9-103">"tbllastinviteid"</span><span class="sxs-lookup"><span data-stu-id="1d7c9-103">tblLastInviteId</span></span>
 
<span data-ttu-id="1d7c9-104">"tbllastinviteid" enthält die letzte einladungs-ID, die generierte (und in der TblPrincipalInvites-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="1d7c9-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="1d7c9-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-105">**Columns**</span></span>

|<span data-ttu-id="1d7c9-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-106">**Column**</span></span>|<span data-ttu-id="1d7c9-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-107">**Type**</span></span>|<span data-ttu-id="1d7c9-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d7c9-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1d7c9-109">prinID</span></span>  <br/> |<span data-ttu-id="1d7c9-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="1d7c9-110">int, not null</span></span>  <br/> |<span data-ttu-id="1d7c9-111">Prinzipal-ID.</span><span class="sxs-lookup"><span data-stu-id="1d7c9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="1d7c9-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="1d7c9-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="1d7c9-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="1d7c9-113">int, not null</span></span>  <br/> |<span data-ttu-id="1d7c9-114">Zuletzt verwendete Invite-ID.</span><span class="sxs-lookup"><span data-stu-id="1d7c9-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="1d7c9-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-115">**Keys**</span></span>

|<span data-ttu-id="1d7c9-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-116">**Column**</span></span>|<span data-ttu-id="1d7c9-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1d7c9-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d7c9-118">prinID</span><span class="sxs-lookup"><span data-stu-id="1d7c9-118">prinID</span></span>  <br/> |<span data-ttu-id="1d7c9-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="1d7c9-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1d7c9-120">prinID</span><span class="sxs-lookup"><span data-stu-id="1d7c9-120">prinID</span></span>  <br/> |<span data-ttu-id="1d7c9-121">Fremdschlüssel mit Abfrage der tblPrincipal.prinID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1d7c9-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1d7c9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d7c9-122">See also</span></span>

[<span data-ttu-id="1d7c9-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="1d7c9-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)