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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814583"
---
# <a name="tbllastchatid"></a><span data-ttu-id="7fc9d-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="7fc9d-103">tblLastChatId</span></span>
 
<span data-ttu-id="7fc9d-104">tblLastChatId enthält die letzte Chat-ID, die für jeden Benutzer generiert (und in der tblChat-Tabelle verwendet) wurde.</span><span class="sxs-lookup"><span data-stu-id="7fc9d-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="7fc9d-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-105">**Columns**</span></span>

|<span data-ttu-id="7fc9d-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-106">**Column**</span></span>|<span data-ttu-id="7fc9d-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-107">**Type**</span></span>|<span data-ttu-id="7fc9d-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7fc9d-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="7fc9d-109">nodeID</span></span>  <br/> |<span data-ttu-id="7fc9d-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7fc9d-110">int, not null</span></span>  <br/> |<span data-ttu-id="7fc9d-111">Knoten-ID (nur Chatroom-Typ).</span><span class="sxs-lookup"><span data-stu-id="7fc9d-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="7fc9d-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="7fc9d-112">lastChatID</span></span>  <br/> |<span data-ttu-id="7fc9d-113">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="7fc9d-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="7fc9d-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="7fc9d-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="7fc9d-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-115">**Keys**</span></span>

|<span data-ttu-id="7fc9d-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-116">**Column**</span></span>|<span data-ttu-id="7fc9d-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7fc9d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7fc9d-118">\<Knoten-lastChatID\></span><span class="sxs-lookup"><span data-stu-id="7fc9d-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="7fc9d-119">Primärschlüssel (nur Knoten-Nr ist für die Verarbeitung ausreichend).</span><span class="sxs-lookup"><span data-stu-id="7fc9d-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="7fc9d-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="7fc9d-120">nodeID</span></span>  <br/> |<span data-ttu-id="7fc9d-121">Fremdschlüssel mit Lookup in der tblNode. Node-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7fc9d-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7fc9d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fc9d-122">See also</span></span>

[<span data-ttu-id="7fc9d-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="7fc9d-123">tblChat</span></span>](tblchat.md)
