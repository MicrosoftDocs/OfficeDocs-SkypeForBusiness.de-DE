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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295524"
---
# <a name="tbladminlock"></a><span data-ttu-id="e7d21-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="e7d21-103">tblAdminLock</span></span>
 
<span data-ttu-id="e7d21-104">tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e7d21-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="e7d21-105">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="e7d21-105">**Columns**</span></span>

|<span data-ttu-id="e7d21-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e7d21-106">**Column**</span></span>|<span data-ttu-id="e7d21-107">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e7d21-107">**Type**</span></span>|<span data-ttu-id="e7d21-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e7d21-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7d21-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="e7d21-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="e7d21-110">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e7d21-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="e7d21-111">Ablaufdatum und-Uhrzeit Sperren</span><span class="sxs-lookup"><span data-stu-id="e7d21-111">Lock expiration date and time.</span></span> <span data-ttu-id="e7d21-112">Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.</span><span class="sxs-lookup"><span data-stu-id="e7d21-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="e7d21-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="e7d21-113">lockServerID</span></span>  <br/> |<span data-ttu-id="e7d21-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e7d21-114">int, not null</span></span>  <br/> |<span data-ttu-id="e7d21-115">Die ID des Servers, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="e7d21-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="e7d21-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="e7d21-116">lockActorID</span></span>  <br/> |<span data-ttu-id="e7d21-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="e7d21-117">int, not null</span></span>  <br/> |<span data-ttu-id="e7d21-118">Die ID des Prinzipals, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="e7d21-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

