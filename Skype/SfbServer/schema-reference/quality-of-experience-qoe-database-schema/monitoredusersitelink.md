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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle. Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294852"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="f7644-104">MonitoredUserSiteLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="f7644-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="f7644-105">Die Tabelle MonitoredUserSiteLink ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f7644-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="f7644-106">Jeder Datensatz steht für einen Link zwischen zwei Benutzer Websites.</span><span class="sxs-lookup"><span data-stu-id="f7644-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="f7644-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="f7644-107">**Column**</span></span>|<span data-ttu-id="f7644-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="f7644-108">**Data Type**</span></span>|<span data-ttu-id="f7644-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="f7644-109">**Key/Index**</span></span>|<span data-ttu-id="f7644-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="f7644-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7644-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="f7644-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="f7644-112">int</span><span class="sxs-lookup"><span data-stu-id="f7644-112">int</span></span>  <br/> |<span data-ttu-id="f7644-113">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="f7644-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f7644-114">Wird in der [UserSite-Tabelle](usersite.md)referenziert.</span><span class="sxs-lookup"><span data-stu-id="f7644-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="f7644-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="f7644-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="f7644-116">int</span><span class="sxs-lookup"><span data-stu-id="f7644-116">int</span></span>  <br/> |<span data-ttu-id="f7644-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="f7644-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f7644-118">Verweis aus der [Tabelle "UserSite](usersite.md)"</span><span class="sxs-lookup"><span data-stu-id="f7644-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

