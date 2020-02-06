---
title: MonitoredRegionLink-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die Tabelle MonitoredRegionLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Ländern/Regionen.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807813"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="ab6dc-104">MonitoredRegionLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="ab6dc-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="ab6dc-105">Die Tabelle MonitoredRegionLink ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ab6dc-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="ab6dc-106">Jeder Datensatz steht für einen Link zwischen zwei Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="ab6dc-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="ab6dc-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ab6dc-107">**Column**</span></span>|<span data-ttu-id="ab6dc-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ab6dc-108">**Data Type**</span></span>|<span data-ttu-id="ab6dc-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ab6dc-109">**Key/Index**</span></span>|<span data-ttu-id="ab6dc-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ab6dc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab6dc-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="ab6dc-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="ab6dc-112">int</span><span class="sxs-lookup"><span data-stu-id="ab6dc-112">int</span></span>  <br/> |<span data-ttu-id="ab6dc-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="ab6dc-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ab6dc-114">Wird in der [Regions Tabelle](region.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="ab6dc-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="ab6dc-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="ab6dc-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="ab6dc-116">int</span><span class="sxs-lookup"><span data-stu-id="ab6dc-116">int</span></span>  <br/> |<span data-ttu-id="ab6dc-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="ab6dc-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ab6dc-118">Wird in der [Regions Tabelle](region.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="ab6dc-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

