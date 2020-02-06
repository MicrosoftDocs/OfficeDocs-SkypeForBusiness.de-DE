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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815443"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5622e-103">CallPriorities-Tabelle in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5622e-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5622e-104">Bei der CallPriorities-Tabelle handelt es sich um eine statische Tabelle, in der die Liste möglicher Anruf Prioritäten wie "Notfall", "dringend" oder "Normal" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="5622e-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="5622e-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5622e-105">**Column**</span></span>|<span data-ttu-id="5622e-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="5622e-106">**Data Type**</span></span>|<span data-ttu-id="5622e-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="5622e-107">**Key/Index**</span></span>|<span data-ttu-id="5622e-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="5622e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5622e-109">**Prioritäts-Nr**</span><span class="sxs-lookup"><span data-stu-id="5622e-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="5622e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="5622e-110">tinyint</span></span>  <br/> |<span data-ttu-id="5622e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="5622e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="5622e-112">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="5622e-112">**Priority**</span></span> <br/> |<span data-ttu-id="5622e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5622e-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="5622e-114">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="5622e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="5622e-115">0 – unbekannt</span><span class="sxs-lookup"><span data-stu-id="5622e-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="5622e-116">1 – nicht dringend</span><span class="sxs-lookup"><span data-stu-id="5622e-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="5622e-117">2 – Normal</span><span class="sxs-lookup"><span data-stu-id="5622e-117">2 - Normal</span></span> <br/>  <span data-ttu-id="5622e-118">3 – dringend</span><span class="sxs-lookup"><span data-stu-id="5622e-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="5622e-119">4 – Notfall</span><span class="sxs-lookup"><span data-stu-id="5622e-119">4 - Emergency</span></span> <br/> |
   

