---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929812"
---
# <a name="tbladminlock"></a><span data-ttu-id="6c843-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="6c843-103">tblAdminLock</span></span>
 
<span data-ttu-id="6c843-104">TblAdminLock enthält die Administratorsperre, die zum Administratorbefehle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6c843-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="6c843-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="6c843-105">**Columns**</span></span>

|<span data-ttu-id="6c843-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6c843-106">**Column**</span></span>|<span data-ttu-id="6c843-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6c843-107">**Type**</span></span>|<span data-ttu-id="6c843-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="6c843-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c843-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="6c843-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="6c843-110">DateTime, nicht null</span><span class="sxs-lookup"><span data-stu-id="6c843-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="6c843-111">Ablaufdatum und-Uhrzeit zu sperren.</span><span class="sxs-lookup"><span data-stu-id="6c843-111">Lock expiration date and time.</span></span> <span data-ttu-id="6c843-112">Der Besitzer kann diesen Wert in regelmäßigen Abständen erweitern.</span><span class="sxs-lookup"><span data-stu-id="6c843-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="6c843-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="6c843-113">lockServerID</span></span>  <br/> |<span data-ttu-id="6c843-114">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="6c843-114">int, not null</span></span>  <br/> |<span data-ttu-id="6c843-115">ID des Servers, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="6c843-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="6c843-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="6c843-116">lockActorID</span></span>  <br/> |<span data-ttu-id="6c843-117">Int, nicht null</span><span class="sxs-lookup"><span data-stu-id="6c843-117">int, not null</span></span>  <br/> |<span data-ttu-id="6c843-118">ID des Prinzipals, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="6c843-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

