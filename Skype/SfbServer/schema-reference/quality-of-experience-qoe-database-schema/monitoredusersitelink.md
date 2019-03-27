---
title: MonitoredUserSiteLink-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Die MonitoredUserSiteLink-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Verbindung zwischen zwei Benutzer Websites.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874259"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="f6bb3-104">MonitoredUserSiteLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="f6bb3-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="f6bb3-105">Die MonitoredUserSiteLink-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="f6bb3-106">Jeder Datensatz steht für eine Verbindung zwischen zwei Benutzer Websites.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="f6bb3-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f6bb3-107">**Column**</span></span>|<span data-ttu-id="f6bb3-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f6bb3-108">**Data Type**</span></span>|<span data-ttu-id="f6bb3-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="f6bb3-109">**Key/Index**</span></span>|<span data-ttu-id="f6bb3-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f6bb3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6bb3-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="f6bb3-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="f6bb3-112">int</span><span class="sxs-lookup"><span data-stu-id="f6bb3-112">int</span></span>  <br/> |<span data-ttu-id="f6bb3-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="f6bb3-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f6bb3-114">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="f6bb3-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="f6bb3-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="f6bb3-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="f6bb3-116">int</span><span class="sxs-lookup"><span data-stu-id="f6bb3-116">int</span></span>  <br/> |<span data-ttu-id="f6bb3-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="f6bb3-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f6bb3-118">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="f6bb3-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

