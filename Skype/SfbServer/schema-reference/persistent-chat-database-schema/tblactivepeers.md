---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers enthält die aktuellen Peer-to-Peer-Verbindungen zwischen Chat Diensten.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814713"
---
# <a name="tblactivepeers"></a><span data-ttu-id="340a7-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="340a7-103">tblActivePeers</span></span>
 
<span data-ttu-id="340a7-104">tblActivePeers enthält die aktuellen Peer-to-Peer-Verbindungen zwischen Chat Diensten.</span><span class="sxs-lookup"><span data-stu-id="340a7-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="340a7-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="340a7-105">**Columns**</span></span>

|<span data-ttu-id="340a7-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="340a7-106">**Column**</span></span>|<span data-ttu-id="340a7-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="340a7-107">**Type**</span></span>|<span data-ttu-id="340a7-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="340a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="340a7-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="340a7-109">aplServerID</span></span>  <br/> |<span data-ttu-id="340a7-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="340a7-110">int, not null</span></span>  <br/> |<span data-ttu-id="340a7-111">Die ID des Servers, der den Eintrag gepostet hat.</span><span class="sxs-lookup"><span data-stu-id="340a7-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="340a7-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="340a7-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="340a7-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="340a7-113">int, not null</span></span>  <br/> |<span data-ttu-id="340a7-114">Die ID des Peers, mit dem der Buchungsserver verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="340a7-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="340a7-115">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="340a7-115">**Keys**</span></span>

|<span data-ttu-id="340a7-116">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="340a7-116">**Column**</span></span>|<span data-ttu-id="340a7-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="340a7-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="340a7-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="340a7-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="340a7-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="340a7-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="340a7-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="340a7-120">aplServerID</span></span>  <br/> |<span data-ttu-id="340a7-121">Fremdschlüssel mit Lookup in der tblServerIdentity. Server-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="340a7-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="340a7-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="340a7-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="340a7-123">Fremdschlüssel mit Lookup in der tblServerIdentity. Server-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="340a7-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

