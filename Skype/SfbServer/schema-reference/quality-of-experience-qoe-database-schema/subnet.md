---
title: Subnet-Tabelle
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
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="e9fc0-104">Subnet-Tabelle</span><span class="sxs-lookup"><span data-stu-id="e9fc0-104">Subnet table</span></span>
 
<span data-ttu-id="e9fc0-105">Subnet-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="e9fc0-106">Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="e9fc0-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-107">**Column**</span></span>|<span data-ttu-id="e9fc0-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-108">**Data Type**</span></span>|<span data-ttu-id="e9fc0-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-109">**Key/Index**</span></span>|<span data-ttu-id="e9fc0-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9fc0-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="e9fc0-112">int</span><span class="sxs-lookup"><span data-stu-id="e9fc0-112">int</span></span>  <br/> |<span data-ttu-id="e9fc0-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="e9fc0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e9fc0-114">Ganzzahlige Darstellung der Subnetz-IP.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="e9fc0-115">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="e9fc0-116">int</span><span class="sxs-lookup"><span data-stu-id="e9fc0-116">int</span></span>  <br/> ||<span data-ttu-id="e9fc0-117">Subnetzmaske</span><span class="sxs-lookup"><span data-stu-id="e9fc0-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="e9fc0-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="e9fc0-119">int</span><span class="sxs-lookup"><span data-stu-id="e9fc0-119">int</span></span>  <br/> |<span data-ttu-id="e9fc0-120">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="e9fc0-120">Foreign</span></span>  <br/> |<span data-ttu-id="e9fc0-121">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e9fc0-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="e9fc0-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="e9fc0-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="e9fc0-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="e9fc0-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="e9fc0-124">Die Beschreibung des Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="e9fc0-124">The description for the subnet.</span></span>  <br/> |
   

