---
title: Subnet-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet-Tabelle ist eine Tabelle. Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880476"
---
# <a name="subnet-table"></a><span data-ttu-id="6b32e-104">Subnet-Tabelle</span><span class="sxs-lookup"><span data-stu-id="6b32e-104">Subnet table</span></span>
 
<span data-ttu-id="6b32e-105">Subnet-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6b32e-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="6b32e-106">Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="6b32e-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="6b32e-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6b32e-107">**Column**</span></span>|<span data-ttu-id="6b32e-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="6b32e-108">**Data Type**</span></span>|<span data-ttu-id="6b32e-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="6b32e-109">**Key/Index**</span></span>|<span data-ttu-id="6b32e-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="6b32e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b32e-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="6b32e-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="6b32e-112">int</span><span class="sxs-lookup"><span data-stu-id="6b32e-112">int</span></span>  <br/> |<span data-ttu-id="6b32e-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="6b32e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6b32e-114">Ganzzahlige Darstellung der Subnetz-IP.</span><span class="sxs-lookup"><span data-stu-id="6b32e-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="6b32e-115">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="6b32e-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="6b32e-116">int</span><span class="sxs-lookup"><span data-stu-id="6b32e-116">int</span></span>  <br/> ||<span data-ttu-id="6b32e-117">Subnetzmaske</span><span class="sxs-lookup"><span data-stu-id="6b32e-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="6b32e-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="6b32e-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="6b32e-119">int</span><span class="sxs-lookup"><span data-stu-id="6b32e-119">int</span></span>  <br/> |<span data-ttu-id="6b32e-120">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="6b32e-120">Foreign</span></span>  <br/> |<span data-ttu-id="6b32e-121">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="6b32e-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="6b32e-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="6b32e-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="6b32e-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="6b32e-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="6b32e-124">Die Beschreibung des Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="6b32e-124">The description for the subnet.</span></span>  <br/> |
   

