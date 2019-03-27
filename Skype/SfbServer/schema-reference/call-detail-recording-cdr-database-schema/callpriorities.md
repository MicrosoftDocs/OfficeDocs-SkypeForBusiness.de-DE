---
title: CallPriorities-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882990"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="014e6-103">CallPriorities-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="014e6-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="014e6-104">CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="014e6-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="014e6-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="014e6-105">**Column**</span></span>|<span data-ttu-id="014e6-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="014e6-106">**Data Type**</span></span>|<span data-ttu-id="014e6-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="014e6-107">**Key/Index**</span></span>|<span data-ttu-id="014e6-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="014e6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="014e6-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="014e6-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="014e6-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="014e6-110">tinyint</span></span>  <br/> |<span data-ttu-id="014e6-111">Primary</span><span class="sxs-lookup"><span data-stu-id="014e6-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="014e6-112">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="014e6-112">**Priority**</span></span> <br/> |<span data-ttu-id="014e6-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="014e6-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="014e6-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="014e6-114">Allowed values:</span></span> <br/>  <span data-ttu-id="014e6-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="014e6-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="014e6-116">1 – nicht dringend</span><span class="sxs-lookup"><span data-stu-id="014e6-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="014e6-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="014e6-117">2 - Normal</span></span> <br/>  <span data-ttu-id="014e6-118">3 - dringende</span><span class="sxs-lookup"><span data-stu-id="014e6-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="014e6-119">4 - emergency</span><span class="sxs-lookup"><span data-stu-id="014e6-119">4 - Emergency</span></span> <br/> |
   

