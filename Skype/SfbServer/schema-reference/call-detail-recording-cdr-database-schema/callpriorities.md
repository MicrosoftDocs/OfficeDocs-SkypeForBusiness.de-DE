---
title: CallPriorities-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296567"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="85e3a-103">CallPriorities-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="85e3a-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="85e3a-104">Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="85e3a-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="85e3a-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="85e3a-105">**Column**</span></span>|<span data-ttu-id="85e3a-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="85e3a-106">**Data Type**</span></span>|<span data-ttu-id="85e3a-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="85e3a-107">**Key/Index**</span></span>|<span data-ttu-id="85e3a-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="85e3a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85e3a-109">**Prioritäts-Nr**</span><span class="sxs-lookup"><span data-stu-id="85e3a-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="85e3a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="85e3a-110">tinyint</span></span>  <br/> |<span data-ttu-id="85e3a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="85e3a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="85e3a-112">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="85e3a-112">**Priority**</span></span> <br/> |<span data-ttu-id="85e3a-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="85e3a-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="85e3a-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="85e3a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="85e3a-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="85e3a-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="85e3a-116">1 – nicht dringend</span><span class="sxs-lookup"><span data-stu-id="85e3a-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="85e3a-117">2 – Normal</span><span class="sxs-lookup"><span data-stu-id="85e3a-117">2 - Normal</span></span> <br/>  <span data-ttu-id="85e3a-118">3 – dringend</span><span class="sxs-lookup"><span data-stu-id="85e3a-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="85e3a-119">4 – Notfall</span><span class="sxs-lookup"><span data-stu-id="85e3a-119">4 - Emergency</span></span> <br/> |
   

