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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212523"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="ada83-104">MonitoredUserSiteLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="ada83-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="ada83-105">Die MonitoredUserSiteLink-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ada83-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="ada83-106">Jeder Datensatz steht für eine Verbindung zwischen zwei Benutzer Websites.</span><span class="sxs-lookup"><span data-stu-id="ada83-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="ada83-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ada83-107">**Column**</span></span>|<span data-ttu-id="ada83-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ada83-108">**Data Type**</span></span>|<span data-ttu-id="ada83-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ada83-109">**Key/Index**</span></span>|<span data-ttu-id="ada83-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ada83-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ada83-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="ada83-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="ada83-112">int</span><span class="sxs-lookup"><span data-stu-id="ada83-112">int</span></span>  <br/> |<span data-ttu-id="ada83-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ada83-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ada83-114">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ada83-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="ada83-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="ada83-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="ada83-116">int</span><span class="sxs-lookup"><span data-stu-id="ada83-116">int</span></span>  <br/> |<span data-ttu-id="ada83-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="ada83-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ada83-118">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="ada83-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

