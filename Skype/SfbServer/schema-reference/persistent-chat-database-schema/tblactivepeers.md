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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884167"
---
# <a name="tblactivepeers"></a><span data-ttu-id="f6b4e-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="f6b4e-103">tblActivePeers</span></span>
 
<span data-ttu-id="f6b4e-104">"TblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste.</span><span class="sxs-lookup"><span data-stu-id="f6b4e-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="f6b4e-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-105">**Columns**</span></span>

|<span data-ttu-id="f6b4e-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-106">**Column**</span></span>|<span data-ttu-id="f6b4e-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-107">**Type**</span></span>|<span data-ttu-id="f6b4e-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6b4e-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f6b4e-109">aplServerID</span></span>  <br/> |<span data-ttu-id="f6b4e-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="f6b4e-110">int, not null</span></span>  <br/> |<span data-ttu-id="f6b4e-111">ID des Servers, der den Eintrag bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="f6b4e-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="f6b4e-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f6b4e-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="f6b4e-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="f6b4e-113">int, not null</span></span>  <br/> |<span data-ttu-id="f6b4e-114">ID des Peers, die mit der bereitstellende Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f6b4e-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="f6b4e-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-115">**Keys**</span></span>

|<span data-ttu-id="f6b4e-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-116">**Column**</span></span>|<span data-ttu-id="f6b4e-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6b4e-118">\<AplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="f6b4e-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="f6b4e-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f6b4e-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f6b4e-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="f6b4e-120">aplServerID</span></span>  <br/> |<span data-ttu-id="f6b4e-121">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="f6b4e-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="f6b4e-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="f6b4e-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="f6b4e-123">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="f6b4e-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

