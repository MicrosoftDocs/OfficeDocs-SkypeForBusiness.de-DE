---
title: Tabelle "Geräte" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Die Tabelle Devices ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296378"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e2e48-104">Tabelle "Geräte" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e2e48-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2e48-105">Die Tabelle Devices ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e2e48-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="e2e48-106">Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).</span><span class="sxs-lookup"><span data-stu-id="e2e48-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="e2e48-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e2e48-107">**Column**</span></span>|<span data-ttu-id="e2e48-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e2e48-108">**Data Type**</span></span>|<span data-ttu-id="e2e48-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e2e48-109">**Key/Index**</span></span>|<span data-ttu-id="e2e48-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e2e48-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2e48-111">**DeviceID**</span><span class="sxs-lookup"><span data-stu-id="e2e48-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="e2e48-112">int</span><span class="sxs-lookup"><span data-stu-id="e2e48-112">int</span></span>  <br/> |<span data-ttu-id="e2e48-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e2e48-113">Primary</span></span>  <br/> |<span data-ttu-id="e2e48-114">Eindeutige Nummer, die diese Hardware Version kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e2e48-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="e2e48-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="e2e48-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="e2e48-116">int</span><span class="sxs-lookup"><span data-stu-id="e2e48-116">int</span></span>  <br/> |<span data-ttu-id="e2e48-117">Fremd</span><span class="sxs-lookup"><span data-stu-id="e2e48-117">Foreign</span></span>  <br/> |<span data-ttu-id="e2e48-118">Hersteller des Geräts.</span><span class="sxs-lookup"><span data-stu-id="e2e48-118">Manufacturer of this device.</span></span> <span data-ttu-id="e2e48-119">Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="e2e48-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e2e48-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="e2e48-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="e2e48-121">int</span><span class="sxs-lookup"><span data-stu-id="e2e48-121">int</span></span>  <br/> |<span data-ttu-id="e2e48-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="e2e48-122">Foreign</span></span>  <br/> |<span data-ttu-id="e2e48-123">Hardware Version dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="e2e48-123">Hardware version of this device.</span></span> <span data-ttu-id="e2e48-124">Weitere Informationen finden Sie [in der Tabelle HardwareVersions in Skype for Business Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="e2e48-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e2e48-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="e2e48-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="e2e48-126">bigint</span><span class="sxs-lookup"><span data-stu-id="e2e48-126">bigint</span></span>  <br/> ||<span data-ttu-id="e2e48-127">Mac-Adresse</span><span class="sxs-lookup"><span data-stu-id="e2e48-127">MAC Address</span></span>  <br/> |
   

