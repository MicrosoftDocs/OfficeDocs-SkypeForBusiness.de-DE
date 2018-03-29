---
title: DeviceDriver-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: Die DeviceDriver-Tabelle ist eine Tabelle. Jeder Datensatz steht für ein Treiber vom entweder ein Aufnahmegerät verwendet oder darstellungsgerät.
ms.openlocfilehash: d5882ba853bd4909863fc5da415c993d4b59ea4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="devicedriver-table"></a><span data-ttu-id="8393a-104">DeviceDriver-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8393a-104">DeviceDriver table</span></span>
 
<span data-ttu-id="8393a-105">Die DeviceDriver-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8393a-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="8393a-106">Jeder Datensatz steht für ein Treiber vom entweder ein Aufnahmegerät verwendet oder darstellungsgerät.</span><span class="sxs-lookup"><span data-stu-id="8393a-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="8393a-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8393a-107">**Column**</span></span>|<span data-ttu-id="8393a-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8393a-108">**Data Type**</span></span>|<span data-ttu-id="8393a-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="8393a-109">**Key/Index**</span></span>|<span data-ttu-id="8393a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="8393a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8393a-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="8393a-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="8393a-112">int</span><span class="sxs-lookup"><span data-stu-id="8393a-112">int</span></span>  <br/> |<span data-ttu-id="8393a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8393a-113">Primary</span></span>  <br/> |<span data-ttu-id="8393a-114">Eindeutige Zahl, die diesen gerätetreiberdatensatz identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8393a-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="8393a-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="8393a-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="8393a-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="8393a-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="8393a-117">eindeutige</span><span class="sxs-lookup"><span data-stu-id="8393a-117">unique</span></span>  <br/> |<span data-ttu-id="8393a-118">Name des Aufnahmegeräts-Treiber.</span><span class="sxs-lookup"><span data-stu-id="8393a-118">Device driver name.</span></span>  <br/> |
   

