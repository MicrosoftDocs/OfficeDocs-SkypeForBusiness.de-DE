---
title: UserSite-Tabelle
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
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a><span data-ttu-id="67238-104">UserSite-Tabelle</span><span class="sxs-lookup"><span data-stu-id="67238-104">UserSite table</span></span>
 
<span data-ttu-id="67238-105">Die UserSite-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="67238-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="67238-106">Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="67238-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="67238-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="67238-107">**Column**</span></span>|<span data-ttu-id="67238-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="67238-108">**Data Type**</span></span>|<span data-ttu-id="67238-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="67238-109">**Key/Index**</span></span>|<span data-ttu-id="67238-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="67238-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="67238-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="67238-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="67238-112">int</span><span class="sxs-lookup"><span data-stu-id="67238-112">int</span></span>  <br/> |<span data-ttu-id="67238-113">Primary</span><span class="sxs-lookup"><span data-stu-id="67238-113">Primary</span></span>  <br/> |<span data-ttu-id="67238-114">Eindeutige Zahl, die den Benutzerstandort identifiziert.</span><span class="sxs-lookup"><span data-stu-id="67238-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="67238-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="67238-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="67238-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="67238-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="67238-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="67238-117">Unique</span></span>  <br/> |<span data-ttu-id="67238-118">Name der Website des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="67238-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="67238-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="67238-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="67238-120">int</span><span class="sxs-lookup"><span data-stu-id="67238-120">int</span></span>  <br/> |<span data-ttu-id="67238-121">Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="67238-121">Foreign</span></span>  <br/> |<span data-ttu-id="67238-122">Verwiesen von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="67238-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

