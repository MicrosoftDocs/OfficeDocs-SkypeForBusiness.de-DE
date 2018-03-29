---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="1ff6c-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="1ff6c-103">tblAdminLock</span></span>
 
<span data-ttu-id="1ff6c-104">TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1ff6c-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="1ff6c-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="1ff6c-105">**Columns**</span></span>

|<span data-ttu-id="1ff6c-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1ff6c-106">**Column**</span></span>|<span data-ttu-id="1ff6c-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1ff6c-107">**Type**</span></span>|<span data-ttu-id="1ff6c-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1ff6c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ff6c-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="1ff6c-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="1ff6c-110">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="1ff6c-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="1ff6c-111">Ablaufdatum und-Uhrzeit zu sperren.</span><span class="sxs-lookup"><span data-stu-id="1ff6c-111">Lock expiration date and time.</span></span> <span data-ttu-id="1ff6c-112">Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.</span><span class="sxs-lookup"><span data-stu-id="1ff6c-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="1ff6c-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="1ff6c-113">lockServerID</span></span>  <br/> |<span data-ttu-id="1ff6c-114">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="1ff6c-114">int, not null</span></span>  <br/> |<span data-ttu-id="1ff6c-115">ID des Servers, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="1ff6c-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="1ff6c-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="1ff6c-116">lockActorID</span></span>  <br/> |<span data-ttu-id="1ff6c-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="1ff6c-117">int, not null</span></span>  <br/> |<span data-ttu-id="1ff6c-118">ID des Prinzipals, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="1ff6c-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

