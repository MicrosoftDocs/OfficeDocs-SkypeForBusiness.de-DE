---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814693"
---
# <a name="tbladminlock"></a><span data-ttu-id="c8c39-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="c8c39-103">tblAdminLock</span></span>
 
<span data-ttu-id="c8c39-104">tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c8c39-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="c8c39-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="c8c39-105">**Columns**</span></span>

|<span data-ttu-id="c8c39-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c8c39-106">**Column**</span></span>|<span data-ttu-id="c8c39-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c8c39-107">**Type**</span></span>|<span data-ttu-id="c8c39-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c8c39-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8c39-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="c8c39-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="c8c39-110">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c8c39-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="c8c39-111">Ablaufdatum und-Uhrzeit Sperren</span><span class="sxs-lookup"><span data-stu-id="c8c39-111">Lock expiration date and time.</span></span> <span data-ttu-id="c8c39-112">Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.</span><span class="sxs-lookup"><span data-stu-id="c8c39-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="c8c39-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="c8c39-113">lockServerID</span></span>  <br/> |<span data-ttu-id="c8c39-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c8c39-114">int, not null</span></span>  <br/> |<span data-ttu-id="c8c39-115">Die ID des Servers, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="c8c39-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="c8c39-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="c8c39-116">lockActorID</span></span>  <br/> |<span data-ttu-id="c8c39-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="c8c39-117">int, not null</span></span>  <br/> |<span data-ttu-id="c8c39-118">Die ID des Prinzipals, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="c8c39-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

