---
title: UserSite-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212046"
---
# <a name="usersite-table"></a><span data-ttu-id="cf1bf-104">UserSite-Tabelle</span><span class="sxs-lookup"><span data-stu-id="cf1bf-104">UserSite table</span></span>
 
<span data-ttu-id="cf1bf-105">Die UserSite-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="cf1bf-106">Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="cf1bf-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-107">**Column**</span></span>|<span data-ttu-id="cf1bf-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-108">**Data Type**</span></span>|<span data-ttu-id="cf1bf-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-109">**Key/Index**</span></span>|<span data-ttu-id="cf1bf-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf1bf-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="cf1bf-112">int</span><span class="sxs-lookup"><span data-stu-id="cf1bf-112">int</span></span>  <br/> |<span data-ttu-id="cf1bf-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cf1bf-113">Primary</span></span>  <br/> |<span data-ttu-id="cf1bf-114">Eindeutige Zahl, die den Benutzerstandort identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="cf1bf-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="cf1bf-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="cf1bf-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="cf1bf-117">Unique</span></span>  <br/> |<span data-ttu-id="cf1bf-118">Name der Website des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="cf1bf-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="cf1bf-120">int</span><span class="sxs-lookup"><span data-stu-id="cf1bf-120">int</span></span>  <br/> |<span data-ttu-id="cf1bf-121">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="cf1bf-121">Foreign</span></span>  <br/> |<span data-ttu-id="cf1bf-122">Verwiesen von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="cf1bf-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

