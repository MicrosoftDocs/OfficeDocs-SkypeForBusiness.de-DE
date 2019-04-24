---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: "\"TblActivePeers\" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste."
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212677"
---
# <a name="tblactivepeers"></a><span data-ttu-id="a8606-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="a8606-103">tblActivePeers</span></span>
 
<span data-ttu-id="a8606-104">"TblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste.</span><span class="sxs-lookup"><span data-stu-id="a8606-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="a8606-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a8606-105">**Columns**</span></span>

|<span data-ttu-id="a8606-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a8606-106">**Column**</span></span>|<span data-ttu-id="a8606-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="a8606-107">**Type**</span></span>|<span data-ttu-id="a8606-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a8606-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a8606-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a8606-109">aplServerID</span></span>  <br/> |<span data-ttu-id="a8606-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="a8606-110">int, not null</span></span>  <br/> |<span data-ttu-id="a8606-111">ID des Servers, der den Eintrag bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="a8606-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="a8606-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a8606-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="a8606-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="a8606-113">int, not null</span></span>  <br/> |<span data-ttu-id="a8606-114">ID des Peers, die mit der bereitstellende Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a8606-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="a8606-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="a8606-115">**Keys**</span></span>

|<span data-ttu-id="a8606-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a8606-116">**Column**</span></span>|<span data-ttu-id="a8606-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a8606-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8606-118">\<AplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="a8606-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="a8606-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="a8606-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a8606-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="a8606-120">aplServerID</span></span>  <br/> |<span data-ttu-id="a8606-121">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="a8606-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="a8606-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="a8606-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="a8606-123">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="a8606-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

