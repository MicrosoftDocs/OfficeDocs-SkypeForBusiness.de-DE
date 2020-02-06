---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity enthält die aktiven Chat Server im persistent Chat Serverpool.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812273"
---
# <a name="tblserveridentity"></a><span data-ttu-id="84d2d-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="84d2d-103">tblServerIdentity</span></span>
 
<span data-ttu-id="84d2d-104">tblServerIdentity enthält die aktiven Chat Server im persistent Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="84d2d-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="84d2d-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="84d2d-105">**Columns**</span></span>

|<span data-ttu-id="84d2d-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="84d2d-106">**Column**</span></span>|<span data-ttu-id="84d2d-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="84d2d-107">**Type**</span></span>|<span data-ttu-id="84d2d-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="84d2d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84d2d-109">ServerID</span><span class="sxs-lookup"><span data-stu-id="84d2d-109">serverID</span></span>  <br/> |<span data-ttu-id="84d2d-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="84d2d-110">int, not null</span></span>  <br/> |<span data-ttu-id="84d2d-111">Server-ID.</span><span class="sxs-lookup"><span data-stu-id="84d2d-111">Server ID.</span></span> <span data-ttu-id="84d2d-112">Entspricht der Instanz-ID des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="84d2d-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="84d2d-113">ServerAddress</span><span class="sxs-lookup"><span data-stu-id="84d2d-113">serverAddress</span></span>  <br/> |<span data-ttu-id="84d2d-114">nvarchar (256); nicht NULL</span><span class="sxs-lookup"><span data-stu-id="84d2d-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="84d2d-115">Server Adresse unter Verwendung der Windows Communication Foundation-Adresse.</span><span class="sxs-lookup"><span data-stu-id="84d2d-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="84d2d-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="84d2d-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="84d2d-117">datetime</span><span class="sxs-lookup"><span data-stu-id="84d2d-117">datetime</span></span>  <br/> |<span data-ttu-id="84d2d-118">Der letzte Zeitpunkt, zu dem der Kanal Server diese Zeile aktualisiert hat, um zu beweisen, dass er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="84d2d-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="84d2d-119">**Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="84d2d-119">**Key**</span></span>

|<span data-ttu-id="84d2d-120">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="84d2d-120">**Column**</span></span>|<span data-ttu-id="84d2d-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="84d2d-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84d2d-122">ServerID</span><span class="sxs-lookup"><span data-stu-id="84d2d-122">serverID</span></span>  <br/> |<span data-ttu-id="84d2d-123">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="84d2d-123">Primary key.</span></span>  <br/> |
   

