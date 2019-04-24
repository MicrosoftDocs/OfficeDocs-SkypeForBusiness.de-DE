---
title: tblAdminLock
ms.reviewer: ''
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
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212663"
---
# <a name="tbladminlock"></a><span data-ttu-id="d2f0d-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="d2f0d-103">tblAdminLock</span></span>
 
<span data-ttu-id="d2f0d-104">TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d2f0d-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="d2f0d-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="d2f0d-105">**Columns**</span></span>

|<span data-ttu-id="d2f0d-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d2f0d-106">**Column**</span></span>|<span data-ttu-id="d2f0d-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="d2f0d-107">**Type**</span></span>|<span data-ttu-id="d2f0d-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d2f0d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2f0d-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="d2f0d-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="d2f0d-110">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="d2f0d-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="d2f0d-111">Ablaufdatum und-Uhrzeit zu sperren.</span><span class="sxs-lookup"><span data-stu-id="d2f0d-111">Lock expiration date and time.</span></span> <span data-ttu-id="d2f0d-112">Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.</span><span class="sxs-lookup"><span data-stu-id="d2f0d-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="d2f0d-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="d2f0d-113">lockServerID</span></span>  <br/> |<span data-ttu-id="d2f0d-114">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d2f0d-114">int, not null</span></span>  <br/> |<span data-ttu-id="d2f0d-115">ID des Servers, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="d2f0d-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="d2f0d-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="d2f0d-116">lockActorID</span></span>  <br/> |<span data-ttu-id="d2f0d-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="d2f0d-117">int, not null</span></span>  <br/> |<span data-ttu-id="d2f0d-118">ID des Prinzipals, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="d2f0d-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

