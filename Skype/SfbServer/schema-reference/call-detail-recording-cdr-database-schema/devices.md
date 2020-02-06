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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Die Tabelle Devices ist eine unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815283"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b4178-104">Tabelle "Geräte" in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b4178-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b4178-105">Die Tabelle Devices ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b4178-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="b4178-106">Jeder Datensatz speichert Informationen zu einem Gerät (Tischtelefon).</span><span class="sxs-lookup"><span data-stu-id="b4178-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="b4178-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b4178-107">**Column**</span></span>|<span data-ttu-id="b4178-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b4178-108">**Data Type**</span></span>|<span data-ttu-id="b4178-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b4178-109">**Key/Index**</span></span>|<span data-ttu-id="b4178-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b4178-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4178-111">**DeviceID**</span><span class="sxs-lookup"><span data-stu-id="b4178-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="b4178-112">int</span><span class="sxs-lookup"><span data-stu-id="b4178-112">int</span></span>  <br/> |<span data-ttu-id="b4178-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b4178-113">Primary</span></span>  <br/> |<span data-ttu-id="b4178-114">Eindeutige Nummer, die diese Hardware Version kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b4178-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="b4178-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="b4178-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="b4178-116">int</span><span class="sxs-lookup"><span data-stu-id="b4178-116">int</span></span>  <br/> |<span data-ttu-id="b4178-117">Fremd</span><span class="sxs-lookup"><span data-stu-id="b4178-117">Foreign</span></span>  <br/> |<span data-ttu-id="b4178-118">Hersteller des Geräts.</span><span class="sxs-lookup"><span data-stu-id="b4178-118">Manufacturer of this device.</span></span> <span data-ttu-id="b4178-119">Weitere Informationen finden Sie [in der Tabelle "Hersteller" in Skype for Business Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="b4178-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b4178-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="b4178-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="b4178-121">int</span><span class="sxs-lookup"><span data-stu-id="b4178-121">int</span></span>  <br/> |<span data-ttu-id="b4178-122">Fremd</span><span class="sxs-lookup"><span data-stu-id="b4178-122">Foreign</span></span>  <br/> |<span data-ttu-id="b4178-123">Hardware Version dieses Geräts.</span><span class="sxs-lookup"><span data-stu-id="b4178-123">Hardware version of this device.</span></span> <span data-ttu-id="b4178-124">Weitere Informationen finden Sie [in der Tabelle HardwareVersions in Skype for Business Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="b4178-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b4178-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="b4178-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="b4178-126">bigint</span><span class="sxs-lookup"><span data-stu-id="b4178-126">bigint</span></span>  <br/> ||<span data-ttu-id="b4178-127">Mac-Adresse</span><span class="sxs-lookup"><span data-stu-id="b4178-127">MAC Address</span></span>  <br/> |
   

