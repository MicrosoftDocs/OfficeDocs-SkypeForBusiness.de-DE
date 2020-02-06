---
title: MonitoredUserSiteLink-Tabelle
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807793"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="91471-104">MonitoredUserSiteLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="91471-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="91471-105">Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="91471-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="91471-106">Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.</span><span class="sxs-lookup"><span data-stu-id="91471-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="91471-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="91471-107">**Column**</span></span>|<span data-ttu-id="91471-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="91471-108">**Data Type**</span></span>|<span data-ttu-id="91471-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="91471-109">**Key/Index**</span></span>|<span data-ttu-id="91471-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="91471-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91471-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="91471-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="91471-112">int</span><span class="sxs-lookup"><span data-stu-id="91471-112">int</span></span>  <br/> |<span data-ttu-id="91471-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="91471-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="91471-114">Wird in der [UserSite-Tabelle](usersite.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="91471-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="91471-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="91471-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="91471-116">int</span><span class="sxs-lookup"><span data-stu-id="91471-116">int</span></span>  <br/> |<span data-ttu-id="91471-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="91471-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="91471-118">Verweis aus der [Tabelle "UserSite](usersite.md)"</span><span class="sxs-lookup"><span data-stu-id="91471-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

