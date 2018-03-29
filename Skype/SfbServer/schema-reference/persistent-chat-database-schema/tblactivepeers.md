---
title: tblActivePeers
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
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="f11e0-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="f11e0-103">tblActivePeers</span></span>
 
<span data-ttu-id="f11e0-104">"TblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste.</span><span class="sxs-lookup"><span data-stu-id="f11e0-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="f11e0-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="f11e0-105">**Columns**</span></span>

|<span data-ttu-id="f11e0-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f11e0-106">**Column**</span></span>|<span data-ttu-id="f11e0-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f11e0-107">**Type**</span></span>|<span data-ttu-id="f11e0-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f11e0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f11e0-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f11e0-109">aplServerID</span></span>  <br/> |<span data-ttu-id="f11e0-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="f11e0-110">int, not null</span></span>  <br/> |<span data-ttu-id="f11e0-111">ID des Servers, der den Eintrag bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="f11e0-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="f11e0-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f11e0-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="f11e0-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="f11e0-113">int, not null</span></span>  <br/> |<span data-ttu-id="f11e0-114">ID des Peers, die mit der bereitstellende Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f11e0-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="f11e0-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f11e0-115">**Keys**</span></span>

|<span data-ttu-id="f11e0-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f11e0-116">**Column**</span></span>|<span data-ttu-id="f11e0-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f11e0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f11e0-118">\<AplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="f11e0-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="f11e0-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f11e0-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f11e0-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f11e0-120">aplServerID</span></span>  <br/> |<span data-ttu-id="f11e0-121">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="f11e0-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="f11e0-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f11e0-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="f11e0-123">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="f11e0-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

