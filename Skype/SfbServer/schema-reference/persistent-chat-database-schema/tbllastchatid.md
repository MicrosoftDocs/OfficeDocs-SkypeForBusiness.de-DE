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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505089"
---
# <a name="tbllastchatid"></a><span data-ttu-id="afc5c-103">"lastchatid"</span><span class="sxs-lookup"><span data-stu-id="afc5c-103">tblLastChatId</span></span>
 
<span data-ttu-id="afc5c-104">"lastchatid" enthält die letzte Chat-ID, die generierte (und in der TblChat-Tabelle verwendete) für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="afc5c-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="afc5c-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="afc5c-105">**Columns**</span></span>

|<span data-ttu-id="afc5c-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="afc5c-106">**Column**</span></span>|<span data-ttu-id="afc5c-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="afc5c-107">**Type**</span></span>|<span data-ttu-id="afc5c-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="afc5c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afc5c-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="afc5c-109">nodeID</span></span>  <br/> |<span data-ttu-id="afc5c-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="afc5c-110">int, not null</span></span>  <br/> |<span data-ttu-id="afc5c-111">Knoten-ID (nur Chatroom-Typ).</span><span class="sxs-lookup"><span data-stu-id="afc5c-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="afc5c-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="afc5c-112">lastChatID</span></span>  <br/> |<span data-ttu-id="afc5c-113">Bigint, nicht null</span><span class="sxs-lookup"><span data-stu-id="afc5c-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="afc5c-114">Zuletzt verwendete Chat-ID.</span><span class="sxs-lookup"><span data-stu-id="afc5c-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="afc5c-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="afc5c-115">**Keys**</span></span>

|<span data-ttu-id="afc5c-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="afc5c-116">**Column**</span></span>|<span data-ttu-id="afc5c-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="afc5c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="afc5c-118">\<NodeID lastChatID\></span><span class="sxs-lookup"><span data-stu-id="afc5c-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="afc5c-119">Primärschlüssel (nur NodeID ist ausreichend für die Verarbeitung).</span><span class="sxs-lookup"><span data-stu-id="afc5c-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="afc5c-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="afc5c-120">nodeID</span></span>  <br/> |<span data-ttu-id="afc5c-121">Fremdschlüssel mit Abfrage der tblNode.nodeID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="afc5c-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="afc5c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afc5c-122">See also</span></span>

[<span data-ttu-id="afc5c-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="afc5c-123">tblChat</span></span>](tblchat.md)