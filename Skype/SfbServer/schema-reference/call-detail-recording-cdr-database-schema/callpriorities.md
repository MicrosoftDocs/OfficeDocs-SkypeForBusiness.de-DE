---
title: CallPriorities-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901529"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bafd2-103">CallPriorities-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bafd2-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bafd2-104">CallPriorities-Tabelle ist eine statische Tabelle, die die Liste der möglichen Anruf Prioritäten, wie beispielsweise "emergency", "sofortigen" oder "normal" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bafd2-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="bafd2-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="bafd2-105">**Column**</span></span>|<span data-ttu-id="bafd2-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="bafd2-106">**Data Type**</span></span>|<span data-ttu-id="bafd2-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="bafd2-107">**Key/Index**</span></span>|<span data-ttu-id="bafd2-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="bafd2-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bafd2-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="bafd2-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="bafd2-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="bafd2-110">tinyint</span></span>  <br/> |<span data-ttu-id="bafd2-111">Primary</span><span class="sxs-lookup"><span data-stu-id="bafd2-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="bafd2-112">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="bafd2-112">**Priority**</span></span> <br/> |<span data-ttu-id="bafd2-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bafd2-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="bafd2-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="bafd2-114">Allowed values:</span></span> <br/>  <span data-ttu-id="bafd2-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="bafd2-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="bafd2-116">1 – nicht dringend</span><span class="sxs-lookup"><span data-stu-id="bafd2-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="bafd2-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="bafd2-117">2 - Normal</span></span> <br/>  <span data-ttu-id="bafd2-118">3 - dringende</span><span class="sxs-lookup"><span data-stu-id="bafd2-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="bafd2-119">4 - emergency</span><span class="sxs-lookup"><span data-stu-id="bafd2-119">4 - Emergency</span></span> <br/> |
   

