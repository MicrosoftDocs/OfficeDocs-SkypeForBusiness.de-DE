---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Die AppliedBandwidthSource-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Datenquelle.
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924850"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="9ecd9-104">AppliedBandwidthSource-Tabelle</span><span class="sxs-lookup"><span data-stu-id="9ecd9-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="9ecd9-105">Die AppliedBandwidthSource-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9ecd9-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="9ecd9-106">Jeder Datensatz steht für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="9ecd9-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="9ecd9-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9ecd9-107">**Column**</span></span>|<span data-ttu-id="9ecd9-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9ecd9-108">**Data Type**</span></span>|<span data-ttu-id="9ecd9-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="9ecd9-109">**Key/Index**</span></span>|<span data-ttu-id="9ecd9-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="9ecd9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ecd9-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="9ecd9-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="9ecd9-112">int</span><span class="sxs-lookup"><span data-stu-id="9ecd9-112">int</span></span>  <br/> |<span data-ttu-id="9ecd9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9ecd9-113">Primary</span></span>  <br/> |<span data-ttu-id="9ecd9-114">Eindeutige Zahl, die die Quelle identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9ecd9-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="9ecd9-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="9ecd9-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="9ecd9-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="9ecd9-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="9ecd9-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="9ecd9-117">Unique</span></span>  <br/> |<span data-ttu-id="9ecd9-118">Dies ist die Quelle des Endes Bandbreite eingeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ecd9-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="9ecd9-119">Beschrieben werden, in dem der Grenzwert für Bandbreite (beispielsweise "Richtlinienserver", "Server aktivieren" oder "Modalität") stammt.</span><span class="sxs-lookup"><span data-stu-id="9ecd9-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

