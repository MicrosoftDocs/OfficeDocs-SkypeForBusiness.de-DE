---
title: MonitoredUserSiteLink-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Die MonitoredUserSiteLink-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Verbindung zwischen zwei Benutzer Websites.
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920012"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="9af47-104">MonitoredUserSiteLink-Tabelle</span><span class="sxs-lookup"><span data-stu-id="9af47-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="9af47-105">Die MonitoredUserSiteLink-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9af47-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="9af47-106">Jeder Datensatz steht für eine Verbindung zwischen zwei Benutzer Websites.</span><span class="sxs-lookup"><span data-stu-id="9af47-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="9af47-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9af47-107">**Column**</span></span>|<span data-ttu-id="9af47-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9af47-108">**Data Type**</span></span>|<span data-ttu-id="9af47-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="9af47-109">**Key/Index**</span></span>|<span data-ttu-id="9af47-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="9af47-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9af47-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="9af47-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="9af47-112">int</span><span class="sxs-lookup"><span data-stu-id="9af47-112">int</span></span>  <br/> |<span data-ttu-id="9af47-113">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="9af47-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9af47-114">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="9af47-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="9af47-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="9af47-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="9af47-116">int</span><span class="sxs-lookup"><span data-stu-id="9af47-116">int</span></span>  <br/> |<span data-ttu-id="9af47-117">Primär, Fremd</span><span class="sxs-lookup"><span data-stu-id="9af47-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9af47-118">Verweis von der [UserSite-Tabelle](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="9af47-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

