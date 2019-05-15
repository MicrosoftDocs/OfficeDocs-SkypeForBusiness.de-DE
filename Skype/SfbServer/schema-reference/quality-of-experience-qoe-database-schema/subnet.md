---
title: Subnet-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet-Tabelle ist eine Tabelle. Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907066"
---
# <a name="subnet-table"></a><span data-ttu-id="52b19-104">Subnet-Tabelle</span><span class="sxs-lookup"><span data-stu-id="52b19-104">Subnet table</span></span>
 
<span data-ttu-id="52b19-105">Subnet-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="52b19-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="52b19-106">Jeder Datensatz steht für ein Subnetz im Netzwerk Konfigurationseinstellung definiert.</span><span class="sxs-lookup"><span data-stu-id="52b19-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="52b19-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="52b19-107">**Column**</span></span>|<span data-ttu-id="52b19-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="52b19-108">**Data Type**</span></span>|<span data-ttu-id="52b19-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="52b19-109">**Key/Index**</span></span>|<span data-ttu-id="52b19-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="52b19-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52b19-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="52b19-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="52b19-112">int</span><span class="sxs-lookup"><span data-stu-id="52b19-112">int</span></span>  <br/> |<span data-ttu-id="52b19-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="52b19-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="52b19-114">Ganzzahlige Darstellung der Subnetz-IP.</span><span class="sxs-lookup"><span data-stu-id="52b19-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="52b19-115">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="52b19-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="52b19-116">int</span><span class="sxs-lookup"><span data-stu-id="52b19-116">int</span></span>  <br/> ||<span data-ttu-id="52b19-117">Subnetzmaske</span><span class="sxs-lookup"><span data-stu-id="52b19-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="52b19-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="52b19-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="52b19-119">int</span><span class="sxs-lookup"><span data-stu-id="52b19-119">int</span></span>  <br/> |<span data-ttu-id="52b19-120">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="52b19-120">Foreign</span></span>  <br/> |<span data-ttu-id="52b19-121">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="52b19-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="52b19-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="52b19-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="52b19-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="52b19-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="52b19-124">Die Beschreibung des Subnetzes.</span><span class="sxs-lookup"><span data-stu-id="52b19-124">The description for the subnet.</span></span>  <br/> |
   

