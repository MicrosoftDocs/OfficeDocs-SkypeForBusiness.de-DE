---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295398"
---
# <a name="tbllastchatid"></a><span data-ttu-id="02ce2-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="02ce2-103">tblLastChatId</span></span>
 
<span data-ttu-id="02ce2-104">tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.</span><span class="sxs-lookup"><span data-stu-id="02ce2-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="02ce2-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="02ce2-105">**Columns**</span></span>

|<span data-ttu-id="02ce2-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="02ce2-106">**Column**</span></span>|<span data-ttu-id="02ce2-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="02ce2-107">**Type**</span></span>|<span data-ttu-id="02ce2-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="02ce2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="02ce2-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="02ce2-109">nodeID</span></span>  <br/> |<span data-ttu-id="02ce2-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="02ce2-110">int, not null</span></span>  <br/> |<span data-ttu-id="02ce2-111">Knoten-ID (nur Chatroom-Typ).</span><span class="sxs-lookup"><span data-stu-id="02ce2-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="02ce2-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="02ce2-112">lastChatID</span></span>  <br/> |<span data-ttu-id="02ce2-113">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="02ce2-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="02ce2-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="02ce2-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="02ce2-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="02ce2-115">**Keys**</span></span>

|<span data-ttu-id="02ce2-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="02ce2-116">**Column**</span></span>|<span data-ttu-id="02ce2-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="02ce2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="02ce2-118">\<Knoten-lastChatID\></span><span class="sxs-lookup"><span data-stu-id="02ce2-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="02ce2-119">Primärschlüssel (nur Knoten-Nr ist für die Verarbeitung ausreichend).</span><span class="sxs-lookup"><span data-stu-id="02ce2-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="02ce2-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="02ce2-120">nodeID</span></span>  <br/> |<span data-ttu-id="02ce2-121">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="02ce2-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="02ce2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02ce2-122">See also</span></span>

[<span data-ttu-id="02ce2-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="02ce2-123">tblChat</span></span>](tblchat.md)
