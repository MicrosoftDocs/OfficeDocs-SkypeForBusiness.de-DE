---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899526"
---
# <a name="tblserveridentity"></a><span data-ttu-id="f0b67-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="f0b67-103">tblServerIdentity</span></span>
 
<span data-ttu-id="f0b67-104">TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="f0b67-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="f0b67-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="f0b67-105">**Columns**</span></span>

|<span data-ttu-id="f0b67-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f0b67-106">**Column**</span></span>|<span data-ttu-id="f0b67-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f0b67-107">**Type**</span></span>|<span data-ttu-id="f0b67-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0b67-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0b67-109">serverID</span><span class="sxs-lookup"><span data-stu-id="f0b67-109">serverID</span></span>  <br/> |<span data-ttu-id="f0b67-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="f0b67-110">int, not null</span></span>  <br/> |<span data-ttu-id="f0b67-111">Server-ID</span><span class="sxs-lookup"><span data-stu-id="f0b67-111">Server ID.</span></span> <span data-ttu-id="f0b67-112">Die Instanz-ID entspricht aus dem zentralen Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f0b67-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="f0b67-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="f0b67-113">serverAddress</span></span>  <br/> |<span data-ttu-id="f0b67-114">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="f0b67-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f0b67-115">Serveradresse mit der Windows Communication Foundation-Adresse.</span><span class="sxs-lookup"><span data-stu-id="f0b67-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="f0b67-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="f0b67-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="f0b67-117">datetime</span><span class="sxs-lookup"><span data-stu-id="f0b67-117">datetime</span></span>  <br/> |<span data-ttu-id="f0b67-118">Der letzte Zeitpunkt, die den Kanalserver aktualisiert diese Zeile zum Nachweis übergeben, die er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0b67-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="f0b67-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="f0b67-119">**Key**</span></span>

|<span data-ttu-id="f0b67-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f0b67-120">**Column**</span></span>|<span data-ttu-id="f0b67-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0b67-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0b67-122">serverID</span><span class="sxs-lookup"><span data-stu-id="f0b67-122">serverID</span></span>  <br/> |<span data-ttu-id="f0b67-123">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f0b67-123">Primary key.</span></span>  <br/> |
   

