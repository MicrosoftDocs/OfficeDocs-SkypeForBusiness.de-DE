---
title: "\"lastchatid\""
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
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a><span data-ttu-id="07b5f-103">"lastchatid"</span><span class="sxs-lookup"><span data-stu-id="07b5f-103">tblLastChatId</span></span>
 
<span data-ttu-id="07b5f-104">"lastchatid" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="07b5f-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="07b5f-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="07b5f-105">**Columns**</span></span>

|<span data-ttu-id="07b5f-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="07b5f-106">**Column**</span></span>|<span data-ttu-id="07b5f-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="07b5f-107">**Type**</span></span>|<span data-ttu-id="07b5f-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="07b5f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07b5f-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="07b5f-109">nodeID</span></span>  <br/> |<span data-ttu-id="07b5f-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="07b5f-110">int, not null</span></span>  <br/> |<span data-ttu-id="07b5f-111">Knoten-ID (nur Chatroom-Typ).</span><span class="sxs-lookup"><span data-stu-id="07b5f-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="07b5f-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="07b5f-112">lastChatID</span></span>  <br/> |<span data-ttu-id="07b5f-113">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="07b5f-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="07b5f-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="07b5f-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="07b5f-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="07b5f-115">**Keys**</span></span>

|<span data-ttu-id="07b5f-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="07b5f-116">**Column**</span></span>|<span data-ttu-id="07b5f-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="07b5f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07b5f-118">\<NodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="07b5f-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="07b5f-119">Primärschlüssel (nur NodeID ist ausreichend für die Verarbeitung).</span><span class="sxs-lookup"><span data-stu-id="07b5f-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="07b5f-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="07b5f-120">nodeID</span></span>  <br/> |<span data-ttu-id="07b5f-121">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="07b5f-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07b5f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07b5f-122">See also</span></span>

#### 

[<span data-ttu-id="07b5f-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="07b5f-123">tblChat</span></span>](tblchat.md)

