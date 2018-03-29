---
title: CallPriorities-Tabelle in Skype für Business Server 2015
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
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dac1a-103">CallPriorities-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dac1a-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dac1a-104">CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dac1a-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="dac1a-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="dac1a-105">**Column**</span></span>|<span data-ttu-id="dac1a-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="dac1a-106">**Data Type**</span></span>|<span data-ttu-id="dac1a-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="dac1a-107">**Key/Index**</span></span>|<span data-ttu-id="dac1a-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="dac1a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dac1a-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="dac1a-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="dac1a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="dac1a-110">tinyint</span></span>  <br/> |<span data-ttu-id="dac1a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="dac1a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="dac1a-112">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="dac1a-112">**Priority**</span></span> <br/> |<span data-ttu-id="dac1a-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dac1a-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="dac1a-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="dac1a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="dac1a-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="dac1a-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="dac1a-116">1 – nicht dringend</span><span class="sxs-lookup"><span data-stu-id="dac1a-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="dac1a-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="dac1a-117">2 - Normal</span></span> <br/>  <span data-ttu-id="dac1a-118">3 - dringende</span><span class="sxs-lookup"><span data-stu-id="dac1a-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="dac1a-119">4 - emergency</span><span class="sxs-lookup"><span data-stu-id="dac1a-119">4 - Emergency</span></span> <br/> |
   

