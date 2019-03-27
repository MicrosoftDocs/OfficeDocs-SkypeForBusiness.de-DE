---
title: MonitoredRegionLink-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die MonitoredRegionLink-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Verbindung zwischen zwei Länder/Regionen.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884414"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="e0ed0-104">MonitoredRegionLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="e0ed0-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="e0ed0-105">Die MonitoredRegionLink-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="e0ed0-106">Jeder Datensatz steht für eine Verbindung zwischen zwei Länder/Regionen.</span><span class="sxs-lookup"><span data-stu-id="e0ed0-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="e0ed0-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e0ed0-107">**Column**</span></span>|<span data-ttu-id="e0ed0-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e0ed0-108">**Data Type**</span></span>|<span data-ttu-id="e0ed0-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e0ed0-109">**Key/Index**</span></span>|<span data-ttu-id="e0ed0-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e0ed0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0ed0-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="e0ed0-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="e0ed0-112">int</span><span class="sxs-lookup"><span data-stu-id="e0ed0-112">int</span></span>  <br/> |<span data-ttu-id="e0ed0-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e0ed0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e0ed0-114">Verweis von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="e0ed0-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="e0ed0-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="e0ed0-116">int</span><span class="sxs-lookup"><span data-stu-id="e0ed0-116">int</span></span>  <br/> |<span data-ttu-id="e0ed0-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e0ed0-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e0ed0-118">Verweis von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="e0ed0-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

