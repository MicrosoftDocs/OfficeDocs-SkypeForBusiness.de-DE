---
title: UserSite-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Die UserSite-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906953"
---
# <a name="usersite-table"></a><span data-ttu-id="56b9b-104">UserSite-Tabelle</span><span class="sxs-lookup"><span data-stu-id="56b9b-104">UserSite table</span></span>
 
<span data-ttu-id="56b9b-105">Die UserSite-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="56b9b-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="56b9b-106">Jeder Datensatz steht für eine Website des Benutzers in der Einstellung der Netzwerk-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="56b9b-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="56b9b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="56b9b-107">**Column**</span></span>|<span data-ttu-id="56b9b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="56b9b-108">**Data Type**</span></span>|<span data-ttu-id="56b9b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="56b9b-109">**Key/Index**</span></span>|<span data-ttu-id="56b9b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="56b9b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56b9b-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="56b9b-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="56b9b-112">int</span><span class="sxs-lookup"><span data-stu-id="56b9b-112">int</span></span>  <br/> |<span data-ttu-id="56b9b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="56b9b-113">Primary</span></span>  <br/> |<span data-ttu-id="56b9b-114">Eindeutige Zahl, die den Benutzerstandort identifiziert.</span><span class="sxs-lookup"><span data-stu-id="56b9b-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="56b9b-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="56b9b-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="56b9b-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="56b9b-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="56b9b-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="56b9b-117">Unique</span></span>  <br/> |<span data-ttu-id="56b9b-118">Name der Website des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="56b9b-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="56b9b-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="56b9b-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="56b9b-120">int</span><span class="sxs-lookup"><span data-stu-id="56b9b-120">int</span></span>  <br/> |<span data-ttu-id="56b9b-121">Ausländisch</span><span class="sxs-lookup"><span data-stu-id="56b9b-121">Foreign</span></span>  <br/> |<span data-ttu-id="56b9b-122">Verwiesen von der [Region Table](region.md).</span><span class="sxs-lookup"><span data-stu-id="56b9b-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

