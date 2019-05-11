---
title: MonitoredRegionLink-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die MonitoredRegionLink-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Verbindung zwischen zwei Länder/Regionen.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920152"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="51b1e-104">MonitoredRegionLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="51b1e-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="51b1e-105">Die MonitoredRegionLink-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="51b1e-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="51b1e-106">Jeder Datensatz steht für eine Verbindung zwischen zwei Länder/Regionen.</span><span class="sxs-lookup"><span data-stu-id="51b1e-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="51b1e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="51b1e-107">**Column**</span></span>|<span data-ttu-id="51b1e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="51b1e-108">**Data Type**</span></span>|<span data-ttu-id="51b1e-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="51b1e-109">**Key/Index**</span></span>|<span data-ttu-id="51b1e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="51b1e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="51b1e-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="51b1e-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="51b1e-112">int</span><span class="sxs-lookup"><span data-stu-id="51b1e-112">int</span></span>  <br/> |<span data-ttu-id="51b1e-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="51b1e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="51b1e-114">Verweis von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="51b1e-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="51b1e-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="51b1e-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="51b1e-116">int</span><span class="sxs-lookup"><span data-stu-id="51b1e-116">int</span></span>  <br/> |<span data-ttu-id="51b1e-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="51b1e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="51b1e-118">Verweis von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="51b1e-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

