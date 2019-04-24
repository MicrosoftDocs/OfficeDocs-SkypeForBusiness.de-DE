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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212088"
---
# <a name="subnet-table"></a><span data-ttu-id="ca821-104">Subnet-Tabelle</span><span class="sxs-lookup"><span data-stu-id="ca821-104">Subnet table</span></span>
 
<span data-ttu-id="ca821-105">Subnet-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ca821-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="ca821-106">Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="ca821-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="ca821-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ca821-107">**Column**</span></span>|<span data-ttu-id="ca821-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ca821-108">**Data Type**</span></span>|<span data-ttu-id="ca821-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ca821-109">**Key/Index**</span></span>|<span data-ttu-id="ca821-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ca821-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ca821-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="ca821-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="ca821-112">int</span><span class="sxs-lookup"><span data-stu-id="ca821-112">int</span></span>  <br/> |<span data-ttu-id="ca821-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ca821-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ca821-114">Ganzzahlige Darstellung der Subnetz-IP.</span><span class="sxs-lookup"><span data-stu-id="ca821-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="ca821-115">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="ca821-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="ca821-116">int</span><span class="sxs-lookup"><span data-stu-id="ca821-116">int</span></span>  <br/> ||<span data-ttu-id="ca821-117">Subnetzmaske</span><span class="sxs-lookup"><span data-stu-id="ca821-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="ca821-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="ca821-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="ca821-119">int</span><span class="sxs-lookup"><span data-stu-id="ca821-119">int</span></span>  <br/> |<span data-ttu-id="ca821-120">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="ca821-120">Foreign</span></span>  <br/> |<span data-ttu-id="ca821-121">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ca821-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ca821-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="ca821-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="ca821-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="ca821-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="ca821-124">Die Beschreibung des Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="ca821-124">The description for the subnet.</span></span>  <br/> |
   

