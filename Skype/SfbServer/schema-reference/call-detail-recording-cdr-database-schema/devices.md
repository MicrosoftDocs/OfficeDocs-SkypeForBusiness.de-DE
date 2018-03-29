---
title: Devices-Tabelle in Skype für Business Server 2015
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
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="53af4-104">Devices-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="53af4-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="53af4-105">Die Geräte-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="53af4-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="53af4-106">Jeder Datensatz speichert Informationen zu einem Gerät (Telefonapparat).</span><span class="sxs-lookup"><span data-stu-id="53af4-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="53af4-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="53af4-107">**Column**</span></span>|<span data-ttu-id="53af4-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="53af4-108">**Data Type**</span></span>|<span data-ttu-id="53af4-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="53af4-109">**Key/Index**</span></span>|<span data-ttu-id="53af4-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="53af4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="53af4-111">**Geräte-ID**</span><span class="sxs-lookup"><span data-stu-id="53af4-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="53af4-112">int</span><span class="sxs-lookup"><span data-stu-id="53af4-112">int</span></span>  <br/> |<span data-ttu-id="53af4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="53af4-113">Primary</span></span>  <br/> |<span data-ttu-id="53af4-114">Eindeutige Zahl, die diese Hardwareversion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="53af4-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="53af4-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="53af4-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="53af4-116">int</span><span class="sxs-lookup"><span data-stu-id="53af4-116">int</span></span>  <br/> |<span data-ttu-id="53af4-117">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="53af4-117">Foreign</span></span>  <br/> |<span data-ttu-id="53af4-118">Hersteller des dieses Gerät.</span><span class="sxs-lookup"><span data-stu-id="53af4-118">Manufacturer of this device.</span></span> <span data-ttu-id="53af4-119">[Manufacturers-Tabelle in Skype für Business Server 2015](manufacturers.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="53af4-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="53af4-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="53af4-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="53af4-121">int</span><span class="sxs-lookup"><span data-stu-id="53af4-121">int</span></span>  <br/> |<span data-ttu-id="53af4-122">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="53af4-122">Foreign</span></span>  <br/> |<span data-ttu-id="53af4-123">Hardwareversion dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="53af4-123">Hardware version of this device.</span></span> <span data-ttu-id="53af4-124">[HardwareVersions-Tabelle in Skype für Business Server 2015](hardwareversions.md) Weitere Informationen finden Sie.</span><span class="sxs-lookup"><span data-stu-id="53af4-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="53af4-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="53af4-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="53af4-126">bigint</span><span class="sxs-lookup"><span data-stu-id="53af4-126">bigint</span></span>  <br/> ||<span data-ttu-id="53af4-127">MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="53af4-127">MAC Address</span></span>  <br/> |
   

