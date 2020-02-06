---
title: Subnet-Tabelle
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Die Subnet-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805203"
---
# <a name="subnet-table"></a><span data-ttu-id="22d43-104">Subnet-Tabelle</span><span class="sxs-lookup"><span data-stu-id="22d43-104">Subnet table</span></span>
 
<span data-ttu-id="22d43-105">Die Subnet-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="22d43-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="22d43-106">Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="22d43-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="22d43-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="22d43-107">**Column**</span></span>|<span data-ttu-id="22d43-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="22d43-108">**Data Type**</span></span>|<span data-ttu-id="22d43-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="22d43-109">**Key/Index**</span></span>|<span data-ttu-id="22d43-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="22d43-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="22d43-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="22d43-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="22d43-112">int</span><span class="sxs-lookup"><span data-stu-id="22d43-112">int</span></span>  <br/> |<span data-ttu-id="22d43-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="22d43-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="22d43-114">Ganzzahlige Darstellung für die Subnetz-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="22d43-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="22d43-115">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="22d43-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="22d43-116">int</span><span class="sxs-lookup"><span data-stu-id="22d43-116">int</span></span>  <br/> ||<span data-ttu-id="22d43-117">Subnetzmaske</span><span class="sxs-lookup"><span data-stu-id="22d43-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="22d43-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="22d43-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="22d43-119">int</span><span class="sxs-lookup"><span data-stu-id="22d43-119">int</span></span>  <br/> |<span data-ttu-id="22d43-120">Fremd</span><span class="sxs-lookup"><span data-stu-id="22d43-120">Foreign</span></span>  <br/> |<span data-ttu-id="22d43-121">Wird in der [UserSite-Tabelle](usersite.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="22d43-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="22d43-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="22d43-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="22d43-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="22d43-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="22d43-124">Die Beschreibung für das Subnetz.</span><span class="sxs-lookup"><span data-stu-id="22d43-124">The description for the subnet.</span></span>  <br/> |
   

