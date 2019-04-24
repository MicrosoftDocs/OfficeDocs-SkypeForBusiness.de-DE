---
title: Device-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Die Gerät-Tabelle ist eine unterstützende Tabelle, die Informationen zu den verschiedenen Capture gespeichert, oder darstellungsgeräte. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212249"
---
# <a name="device-table"></a><span data-ttu-id="2772e-104">Device-Tabelle</span><span class="sxs-lookup"><span data-stu-id="2772e-104">Device table</span></span>
 
<span data-ttu-id="2772e-105">Die Gerät-Tabelle ist eine unterstützende Tabelle, die Informationen zu den verschiedenen Capture gespeichert, oder darstellungsgeräte.</span><span class="sxs-lookup"><span data-stu-id="2772e-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="2772e-106">Jeder Datensatz in der Tabelle steht für ein Gerät.</span><span class="sxs-lookup"><span data-stu-id="2772e-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="2772e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2772e-107">**Column**</span></span>|<span data-ttu-id="2772e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2772e-108">**Data Type**</span></span>|<span data-ttu-id="2772e-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="2772e-109">**Key/Index**</span></span>|<span data-ttu-id="2772e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="2772e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2772e-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="2772e-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="2772e-112">int</span><span class="sxs-lookup"><span data-stu-id="2772e-112">int</span></span>  <br/> |<span data-ttu-id="2772e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="2772e-113">Primary</span></span>  <br/> |<span data-ttu-id="2772e-114">Eindeutige Zahl, die dieses Gerät identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2772e-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="2772e-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="2772e-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="2772e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2772e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2772e-117">DeviceName + DeviceType ist unique</span><span class="sxs-lookup"><span data-stu-id="2772e-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="2772e-118">Name des Aufnahmegeräts.</span><span class="sxs-lookup"><span data-stu-id="2772e-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="2772e-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="2772e-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="2772e-120">bit</span><span class="sxs-lookup"><span data-stu-id="2772e-120">bit</span></span>  <br/> |<span data-ttu-id="2772e-121">DeviceName + DeviceType ist unique</span><span class="sxs-lookup"><span data-stu-id="2772e-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="2772e-122">Gerätetyp.</span><span class="sxs-lookup"><span data-stu-id="2772e-122">Device type.</span></span> <span data-ttu-id="2772e-123">1 ist ein Aufnahmegerät, 0 ist eine darstellungsgerät.</span><span class="sxs-lookup"><span data-stu-id="2772e-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

