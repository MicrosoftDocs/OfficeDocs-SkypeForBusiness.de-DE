---
title: tblServerIdentity
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
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a><span data-ttu-id="3035b-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="3035b-103">tblServerIdentity</span></span>
 
<span data-ttu-id="3035b-104">TblServerIdentity enthält die aktiven Chatserver im Pool Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="3035b-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="3035b-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="3035b-105">**Columns**</span></span>

|<span data-ttu-id="3035b-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3035b-106">**Column**</span></span>|<span data-ttu-id="3035b-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="3035b-107">**Type**</span></span>|<span data-ttu-id="3035b-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3035b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3035b-109">serverID</span><span class="sxs-lookup"><span data-stu-id="3035b-109">serverID</span></span>  <br/> |<span data-ttu-id="3035b-110">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="3035b-110">int, not null</span></span>  <br/> |<span data-ttu-id="3035b-111">Server-ID</span><span class="sxs-lookup"><span data-stu-id="3035b-111">Server ID.</span></span> <span data-ttu-id="3035b-112">Die Instanz-ID entspricht aus dem zentralen Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="3035b-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="3035b-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="3035b-113">serverAddress</span></span>  <br/> |<span data-ttu-id="3035b-114">Nvarchar (256), nicht null</span><span class="sxs-lookup"><span data-stu-id="3035b-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="3035b-115">Serveradresse mit der Windows Communication Foundation-Adresse.</span><span class="sxs-lookup"><span data-stu-id="3035b-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="3035b-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="3035b-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="3035b-117">datetime</span><span class="sxs-lookup"><span data-stu-id="3035b-117">datetime</span></span>  <br/> |<span data-ttu-id="3035b-118">Der letzte Zeitpunkt, die den Kanalserver aktualisiert diese Zeile zum Nachweis übergeben, die er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3035b-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="3035b-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="3035b-119">**Key**</span></span>

|<span data-ttu-id="3035b-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3035b-120">**Column**</span></span>|<span data-ttu-id="3035b-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="3035b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3035b-122">serverID</span><span class="sxs-lookup"><span data-stu-id="3035b-122">serverID</span></span>  <br/> |<span data-ttu-id="3035b-123">Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="3035b-123">Primary key.</span></span>  <br/> |
   

