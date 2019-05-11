---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: "\"lastchatid\" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer."
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929966"
---
# <a name="tbllastchatid"></a><span data-ttu-id="57085-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="57085-103">tblLastChatId</span></span>
 
<span data-ttu-id="57085-104">"lastchatid" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="57085-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="57085-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="57085-105">**Columns**</span></span>

|<span data-ttu-id="57085-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="57085-106">**Column**</span></span>|<span data-ttu-id="57085-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="57085-107">**Type**</span></span>|<span data-ttu-id="57085-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="57085-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57085-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="57085-109">nodeID</span></span>  <br/> |<span data-ttu-id="57085-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="57085-110">int, not null</span></span>  <br/> |<span data-ttu-id="57085-111">Knoten-ID (nur Chatroom-Typ).</span><span class="sxs-lookup"><span data-stu-id="57085-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="57085-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="57085-112">lastChatID</span></span>  <br/> |<span data-ttu-id="57085-113">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="57085-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="57085-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="57085-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="57085-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="57085-115">**Keys**</span></span>

|<span data-ttu-id="57085-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="57085-116">**Column**</span></span>|<span data-ttu-id="57085-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="57085-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57085-118">\<NodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="57085-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="57085-119">Primärschlüssel (nur NodeID ist ausreichend für die Verarbeitung).</span><span class="sxs-lookup"><span data-stu-id="57085-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="57085-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="57085-120">nodeID</span></span>  <br/> |<span data-ttu-id="57085-121">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="57085-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="57085-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57085-122">See also</span></span>

[<span data-ttu-id="57085-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="57085-123">tblChat</span></span>](tblchat.md)
