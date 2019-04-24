---
title: Devices-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Die Geräte-Tabelle ist eine Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Telefonapparat).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213165"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a495d-104">Devices-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a495d-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a495d-105">Die Geräte-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a495d-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="a495d-106">Jeder Datensatz speichert Informationen zu einem Gerät (Telefonapparat).</span><span class="sxs-lookup"><span data-stu-id="a495d-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="a495d-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a495d-107">**Column**</span></span>|<span data-ttu-id="a495d-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a495d-108">**Data Type**</span></span>|<span data-ttu-id="a495d-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="a495d-109">**Key/Index**</span></span>|<span data-ttu-id="a495d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="a495d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a495d-111">**Geräte-ID**</span><span class="sxs-lookup"><span data-stu-id="a495d-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="a495d-112">int</span><span class="sxs-lookup"><span data-stu-id="a495d-112">int</span></span>  <br/> |<span data-ttu-id="a495d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a495d-113">Primary</span></span>  <br/> |<span data-ttu-id="a495d-114">Eindeutige Zahl, die diese Hardwareversion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a495d-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="a495d-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="a495d-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="a495d-116">int</span><span class="sxs-lookup"><span data-stu-id="a495d-116">int</span></span>  <br/> |<span data-ttu-id="a495d-117">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="a495d-117">Foreign</span></span>  <br/> |<span data-ttu-id="a495d-118">Hersteller des dieses Gerät.</span><span class="sxs-lookup"><span data-stu-id="a495d-118">Manufacturer of this device.</span></span> <span data-ttu-id="a495d-119">[Manufacturers-Tabelle in Skype für Business Server 2015](manufacturers.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="a495d-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a495d-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="a495d-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="a495d-121">int</span><span class="sxs-lookup"><span data-stu-id="a495d-121">int</span></span>  <br/> |<span data-ttu-id="a495d-122">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="a495d-122">Foreign</span></span>  <br/> |<span data-ttu-id="a495d-123">Hardwareversion dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="a495d-123">Hardware version of this device.</span></span> <span data-ttu-id="a495d-124">[HardwareVersions-Tabelle in Skype für Business Server 2015](hardwareversions.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="a495d-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a495d-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="a495d-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="a495d-126">bigint</span><span class="sxs-lookup"><span data-stu-id="a495d-126">bigint</span></span>  <br/> ||<span data-ttu-id="a495d-127">MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="a495d-127">MAC Address</span></span>  <br/> |
   

