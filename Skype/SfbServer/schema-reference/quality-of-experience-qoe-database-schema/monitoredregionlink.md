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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Die Tabelle MonitoredRegionLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Ländern/Regionen.
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294873"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="a5443-104">MonitoredRegionLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="a5443-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="a5443-105">Die Tabelle MonitoredRegionLink ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a5443-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="a5443-106">Jeder Datensatz steht für einen Link zwischen zwei Ländern/Regionen.</span><span class="sxs-lookup"><span data-stu-id="a5443-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="a5443-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="a5443-107">**Column**</span></span>|<span data-ttu-id="a5443-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a5443-108">**Data Type**</span></span>|<span data-ttu-id="a5443-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="a5443-109">**Key/Index**</span></span>|<span data-ttu-id="a5443-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="a5443-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5443-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="a5443-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="a5443-112">int</span><span class="sxs-lookup"><span data-stu-id="a5443-112">int</span></span>  <br/> |<span data-ttu-id="a5443-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="a5443-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a5443-114">Wird in der [Regions Tabelle](region.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="a5443-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="a5443-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="a5443-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="a5443-116">int</span><span class="sxs-lookup"><span data-stu-id="a5443-116">int</span></span>  <br/> |<span data-ttu-id="a5443-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="a5443-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a5443-118">Wird in der [Regions Tabelle](region.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="a5443-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

