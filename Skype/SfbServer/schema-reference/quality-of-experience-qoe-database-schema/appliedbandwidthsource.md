---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Die AppliedBandwidthSource-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Datenquelle.
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212355"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="6bff6-104">AppliedBandwidthSource-Tabelle</span><span class="sxs-lookup"><span data-stu-id="6bff6-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="6bff6-105">Die AppliedBandwidthSource-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6bff6-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="6bff6-106">Jeder Datensatz steht für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="6bff6-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="6bff6-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6bff6-107">**Column**</span></span>|<span data-ttu-id="6bff6-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="6bff6-108">**Data Type**</span></span>|<span data-ttu-id="6bff6-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="6bff6-109">**Key/Index**</span></span>|<span data-ttu-id="6bff6-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="6bff6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bff6-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="6bff6-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="6bff6-112">int</span><span class="sxs-lookup"><span data-stu-id="6bff6-112">int</span></span>  <br/> |<span data-ttu-id="6bff6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6bff6-113">Primary</span></span>  <br/> |<span data-ttu-id="6bff6-114">Eindeutige Zahl, die die Quelle identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6bff6-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="6bff6-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="6bff6-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="6bff6-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="6bff6-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="6bff6-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="6bff6-117">Unique</span></span>  <br/> |<span data-ttu-id="6bff6-118">Dies ist die Quelle des Endes Bandbreite eingeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6bff6-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="6bff6-119">Beschrieben werden, in dem der Grenzwert für Bandbreite (beispielsweise "Richtlinienserver", "Server aktivieren" oder "Modalität") stammt.</span><span class="sxs-lookup"><span data-stu-id="6bff6-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

