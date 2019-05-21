---
title: UserSite-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die Tabelle UserSite ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Benutzer Website, die in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294572"
---
# <a name="usersite-table"></a><span data-ttu-id="309eb-104">UserSite-Tabelle</span><span class="sxs-lookup"><span data-stu-id="309eb-104">UserSite table</span></span>
 
<span data-ttu-id="309eb-105">Die Tabelle UserSite ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="309eb-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="309eb-106">Jeder Datensatz steht für eine Benutzer Website, die in der Netzwerk Konfigurationseinstellung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="309eb-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="309eb-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="309eb-107">**Column**</span></span>|<span data-ttu-id="309eb-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="309eb-108">**Data Type**</span></span>|<span data-ttu-id="309eb-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="309eb-109">**Key/Index**</span></span>|<span data-ttu-id="309eb-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="309eb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="309eb-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="309eb-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="309eb-112">int</span><span class="sxs-lookup"><span data-stu-id="309eb-112">int</span></span>  <br/> |<span data-ttu-id="309eb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="309eb-113">Primary</span></span>  <br/> |<span data-ttu-id="309eb-114">Eindeutige Nummer, die die Benutzer Website kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="309eb-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="309eb-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="309eb-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="309eb-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="309eb-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="309eb-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="309eb-117">Unique</span></span>  <br/> |<span data-ttu-id="309eb-118">Name der Benutzer Website.</span><span class="sxs-lookup"><span data-stu-id="309eb-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="309eb-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="309eb-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="309eb-120">int</span><span class="sxs-lookup"><span data-stu-id="309eb-120">int</span></span>  <br/> |<span data-ttu-id="309eb-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="309eb-121">Foreign</span></span>  <br/> |<span data-ttu-id="309eb-122">Referenziert aus der [Regions Tabelle](region.md).</span><span class="sxs-lookup"><span data-stu-id="309eb-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

