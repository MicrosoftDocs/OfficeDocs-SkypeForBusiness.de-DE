---
title: Device-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Die Gerät-Tabelle ist eine unterstützende Tabelle, die Informationen zu den verschiedenen Capture gespeichert, oder darstellungsgeräte. Jeder Datensatz in der Tabelle steht für ein Gerät.
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920026"
---
# <a name="device-table"></a><span data-ttu-id="7beb4-104">Device-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7beb4-104">Device table</span></span>
 
<span data-ttu-id="7beb4-105">Die Gerät-Tabelle ist eine unterstützende Tabelle, die Informationen zu den verschiedenen Capture gespeichert, oder darstellungsgeräte.</span><span class="sxs-lookup"><span data-stu-id="7beb4-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="7beb4-106">Jeder Datensatz in der Tabelle steht für ein Gerät.</span><span class="sxs-lookup"><span data-stu-id="7beb4-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="7beb4-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7beb4-107">**Column**</span></span>|<span data-ttu-id="7beb4-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7beb4-108">**Data Type**</span></span>|<span data-ttu-id="7beb4-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7beb4-109">**Key/Index**</span></span>|<span data-ttu-id="7beb4-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7beb4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7beb4-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="7beb4-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="7beb4-112">int</span><span class="sxs-lookup"><span data-stu-id="7beb4-112">int</span></span>  <br/> |<span data-ttu-id="7beb4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7beb4-113">Primary</span></span>  <br/> |<span data-ttu-id="7beb4-114">Eindeutige Zahl, die dieses Gerät identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7beb4-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="7beb4-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="7beb4-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="7beb4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7beb4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7beb4-117">DeviceName + DeviceType ist unique</span><span class="sxs-lookup"><span data-stu-id="7beb4-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="7beb4-118">Name des Aufnahmegeräts.</span><span class="sxs-lookup"><span data-stu-id="7beb4-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="7beb4-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="7beb4-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="7beb4-120">bit</span><span class="sxs-lookup"><span data-stu-id="7beb4-120">bit</span></span>  <br/> |<span data-ttu-id="7beb4-121">DeviceName + DeviceType ist unique</span><span class="sxs-lookup"><span data-stu-id="7beb4-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="7beb4-122">Gerätetyp.</span><span class="sxs-lookup"><span data-stu-id="7beb4-122">Device type.</span></span> <span data-ttu-id="7beb4-123">1 ist ein Aufnahmegerät, 0 ist eine darstellungsgerät.</span><span class="sxs-lookup"><span data-stu-id="7beb4-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

