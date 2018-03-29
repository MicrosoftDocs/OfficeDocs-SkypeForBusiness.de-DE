---
title: MonitoredUserSiteLink-Tabelle
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
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="cb38b-104">MonitoredUserSiteLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="cb38b-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="cb38b-105">Die MonitoredUserSiteLink-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cb38b-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="cb38b-106">Jeder Datensatz steht für eine Verbindung zwischen zwei Benutzer Websites.</span><span class="sxs-lookup"><span data-stu-id="cb38b-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="cb38b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cb38b-107">**Column**</span></span>|<span data-ttu-id="cb38b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="cb38b-108">**Data Type**</span></span>|<span data-ttu-id="cb38b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="cb38b-109">**Key/Index**</span></span>|<span data-ttu-id="cb38b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="cb38b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb38b-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="cb38b-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="cb38b-112">int</span><span class="sxs-lookup"><span data-stu-id="cb38b-112">int</span></span>  <br/> |<span data-ttu-id="cb38b-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="cb38b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cb38b-114">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="cb38b-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="cb38b-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="cb38b-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="cb38b-116">int</span><span class="sxs-lookup"><span data-stu-id="cb38b-116">int</span></span>  <br/> |<span data-ttu-id="cb38b-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="cb38b-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cb38b-118">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="cb38b-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

