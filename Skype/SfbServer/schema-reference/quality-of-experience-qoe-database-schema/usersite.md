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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die Tabelle UserSite ist eine unterstützende Tabelle. Jeder Datensatz steht für eine Benutzer Website, die in der Netzwerk Konfigurationseinstellung definiert ist.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805003"
---
# <a name="usersite-table"></a><span data-ttu-id="7bf7b-104">UserSite-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7bf7b-104">UserSite table</span></span>
 
<span data-ttu-id="7bf7b-105">Die Tabelle UserSite ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="7bf7b-106">Jeder Datensatz steht für eine Benutzer Website, die in der Netzwerk Konfigurationseinstellung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="7bf7b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-107">**Column**</span></span>|<span data-ttu-id="7bf7b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-108">**Data Type**</span></span>|<span data-ttu-id="7bf7b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-109">**Key/Index**</span></span>|<span data-ttu-id="7bf7b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7bf7b-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="7bf7b-112">int</span><span class="sxs-lookup"><span data-stu-id="7bf7b-112">int</span></span>  <br/> |<span data-ttu-id="7bf7b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7bf7b-113">Primary</span></span>  <br/> |<span data-ttu-id="7bf7b-114">Eindeutige Nummer, die die Benutzer Website kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="7bf7b-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="7bf7b-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="7bf7b-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="7bf7b-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="7bf7b-117">Unique</span></span>  <br/> |<span data-ttu-id="7bf7b-118">Name der Benutzer Website.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="7bf7b-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="7bf7b-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="7bf7b-120">int</span><span class="sxs-lookup"><span data-stu-id="7bf7b-120">int</span></span>  <br/> |<span data-ttu-id="7bf7b-121">Fremd</span><span class="sxs-lookup"><span data-stu-id="7bf7b-121">Foreign</span></span>  <br/> |<span data-ttu-id="7bf7b-122">Referenziert aus der [Regions Tabelle](region.md).</span><span class="sxs-lookup"><span data-stu-id="7bf7b-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

