---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924808"
---
# <a name="tblserveridentity"></a><span data-ttu-id="48beb-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="48beb-103">tblServerIdentity</span></span>
 
<span data-ttu-id="48beb-104">TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="48beb-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="48beb-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="48beb-105">**Columns**</span></span>

|<span data-ttu-id="48beb-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="48beb-106">**Column**</span></span>|<span data-ttu-id="48beb-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="48beb-107">**Type**</span></span>|<span data-ttu-id="48beb-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48beb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48beb-109">serverID</span><span class="sxs-lookup"><span data-stu-id="48beb-109">serverID</span></span>  <br/> |<span data-ttu-id="48beb-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="48beb-110">int, not null</span></span>  <br/> |<span data-ttu-id="48beb-111">Server-ID</span><span class="sxs-lookup"><span data-stu-id="48beb-111">Server ID.</span></span> <span data-ttu-id="48beb-112">Die Instanz-ID entspricht aus dem zentralen Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="48beb-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="48beb-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="48beb-113">serverAddress</span></span>  <br/> |<span data-ttu-id="48beb-114">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="48beb-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="48beb-115">Serveradresse mit der Windows Communication Foundation-Adresse.</span><span class="sxs-lookup"><span data-stu-id="48beb-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="48beb-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="48beb-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="48beb-117">datetime</span><span class="sxs-lookup"><span data-stu-id="48beb-117">datetime</span></span>  <br/> |<span data-ttu-id="48beb-118">Der letzte Zeitpunkt, die den Kanalserver aktualisiert diese Zeile zum Nachweis übergeben, die er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48beb-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="48beb-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="48beb-119">**Key**</span></span>

|<span data-ttu-id="48beb-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="48beb-120">**Column**</span></span>|<span data-ttu-id="48beb-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48beb-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48beb-122">serverID</span><span class="sxs-lookup"><span data-stu-id="48beb-122">serverID</span></span>  <br/> |<span data-ttu-id="48beb-123">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="48beb-123">Primary key.</span></span>  <br/> |
   

