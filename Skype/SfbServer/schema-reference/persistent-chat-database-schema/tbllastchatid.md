---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: "\"lastchatid\" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212565"
---
# <a name="tbllastchatid"></a><span data-ttu-id="134bc-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="134bc-103">tblLastChatId</span></span>
 
<span data-ttu-id="134bc-104">"lastchatid" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="134bc-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="134bc-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="134bc-105">**Columns**</span></span>

|<span data-ttu-id="134bc-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="134bc-106">**Column**</span></span>|<span data-ttu-id="134bc-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="134bc-107">**Type**</span></span>|<span data-ttu-id="134bc-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="134bc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="134bc-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="134bc-109">nodeID</span></span>  <br/> |<span data-ttu-id="134bc-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="134bc-110">int, not null</span></span>  <br/> |<span data-ttu-id="134bc-111">Knoten-ID (nur Chatroom-Typ).</span><span class="sxs-lookup"><span data-stu-id="134bc-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="134bc-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="134bc-112">lastChatID</span></span>  <br/> |<span data-ttu-id="134bc-113">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="134bc-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="134bc-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="134bc-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="134bc-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="134bc-115">**Keys**</span></span>

|<span data-ttu-id="134bc-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="134bc-116">**Column**</span></span>|<span data-ttu-id="134bc-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="134bc-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="134bc-118">\<NodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="134bc-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="134bc-119">Primärschlüssel (nur NodeID ist ausreichend für die Verarbeitung).</span><span class="sxs-lookup"><span data-stu-id="134bc-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="134bc-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="134bc-120">nodeID</span></span>  <br/> |<span data-ttu-id="134bc-121">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="134bc-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="134bc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="134bc-122">See also</span></span>

[<span data-ttu-id="134bc-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="134bc-123">tblChat</span></span>](tblchat.md)
