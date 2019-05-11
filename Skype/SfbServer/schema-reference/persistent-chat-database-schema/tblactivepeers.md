---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: "\"TblActivePeers\" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste."
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929875"
---
# <a name="tblactivepeers"></a><span data-ttu-id="55742-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="55742-103">tblActivePeers</span></span>
 
<span data-ttu-id="55742-104">"TblActivePeers" enthält die aktuellen Peer-zu-Peer-Verbindungen zwischen Chat-Dienste.</span><span class="sxs-lookup"><span data-stu-id="55742-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="55742-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="55742-105">**Columns**</span></span>

|<span data-ttu-id="55742-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="55742-106">**Column**</span></span>|<span data-ttu-id="55742-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="55742-107">**Type**</span></span>|<span data-ttu-id="55742-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="55742-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="55742-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="55742-109">aplServerID</span></span>  <br/> |<span data-ttu-id="55742-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="55742-110">int, not null</span></span>  <br/> |<span data-ttu-id="55742-111">ID des Servers, der den Eintrag bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="55742-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="55742-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="55742-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="55742-113">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="55742-113">int, not null</span></span>  <br/> |<span data-ttu-id="55742-114">ID des Peers, die mit der bereitstellende Server verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="55742-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="55742-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="55742-115">**Keys**</span></span>

|<span data-ttu-id="55742-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="55742-116">**Column**</span></span>|<span data-ttu-id="55742-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="55742-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55742-118">\<AplServerID aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="55742-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="55742-119">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="55742-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="55742-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="55742-120">aplServerID</span></span>  <br/> |<span data-ttu-id="55742-121">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="55742-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="55742-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="55742-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="55742-123">Fremdschlüssel mit Abfrage der Tabelle "tblserveridentity.ServerID".</span><span class="sxs-lookup"><span data-stu-id="55742-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

