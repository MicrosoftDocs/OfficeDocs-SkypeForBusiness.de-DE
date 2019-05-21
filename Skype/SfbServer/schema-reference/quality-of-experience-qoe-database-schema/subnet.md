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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Die Subnet-Tabelle ist eine unterstützende Tabelle. Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294635"
---
# <a name="subnet-table"></a><span data-ttu-id="0bd50-104">Subnet-Tabelle</span><span class="sxs-lookup"><span data-stu-id="0bd50-104">Subnet table</span></span>
 
<span data-ttu-id="0bd50-105">Die Subnet-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0bd50-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="0bd50-106">Jeder Datensatz steht für ein Subnetz, das in der Netzwerk Konfigurationseinstellung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0bd50-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="0bd50-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="0bd50-107">**Column**</span></span>|<span data-ttu-id="0bd50-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="0bd50-108">**Data Type**</span></span>|<span data-ttu-id="0bd50-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="0bd50-109">**Key/Index**</span></span>|<span data-ttu-id="0bd50-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="0bd50-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0bd50-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="0bd50-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="0bd50-112">int</span><span class="sxs-lookup"><span data-stu-id="0bd50-112">int</span></span>  <br/> |<span data-ttu-id="0bd50-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="0bd50-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0bd50-114">Ganzzahlige Darstellung für die Subnetz-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="0bd50-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="0bd50-115">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="0bd50-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="0bd50-116">int</span><span class="sxs-lookup"><span data-stu-id="0bd50-116">int</span></span>  <br/> ||<span data-ttu-id="0bd50-117">Subnetzmaske</span><span class="sxs-lookup"><span data-stu-id="0bd50-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="0bd50-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="0bd50-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="0bd50-119">int</span><span class="sxs-lookup"><span data-stu-id="0bd50-119">int</span></span>  <br/> |<span data-ttu-id="0bd50-120">Fremd</span><span class="sxs-lookup"><span data-stu-id="0bd50-120">Foreign</span></span>  <br/> |<span data-ttu-id="0bd50-121">Wird in der [UserSite-Tabelle](usersite.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="0bd50-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="0bd50-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="0bd50-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="0bd50-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="0bd50-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="0bd50-124">Die Beschreibung für das Subnetz.</span><span class="sxs-lookup"><span data-stu-id="0bd50-124">The description for the subnet.</span></span>  <br/> |
   

