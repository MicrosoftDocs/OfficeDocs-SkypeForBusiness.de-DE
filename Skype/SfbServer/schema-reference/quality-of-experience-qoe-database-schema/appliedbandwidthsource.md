---
title: AppliedBandwidthSource-Tabelle
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
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="70d81-104">AppliedBandwidthSource-Tabelle</span><span class="sxs-lookup"><span data-stu-id="70d81-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="70d81-105">Die AppliedBandwidthSource-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="70d81-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="70d81-106">Jeder Datensatz steht für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="70d81-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="70d81-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="70d81-107">**Column**</span></span>|<span data-ttu-id="70d81-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="70d81-108">**Data Type**</span></span>|<span data-ttu-id="70d81-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="70d81-109">**Key/Index**</span></span>|<span data-ttu-id="70d81-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="70d81-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="70d81-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="70d81-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="70d81-112">int</span><span class="sxs-lookup"><span data-stu-id="70d81-112">int</span></span>  <br/> |<span data-ttu-id="70d81-113">Primary</span><span class="sxs-lookup"><span data-stu-id="70d81-113">Primary</span></span>  <br/> |<span data-ttu-id="70d81-114">Eindeutige Zahl, die die Quelle identifiziert.</span><span class="sxs-lookup"><span data-stu-id="70d81-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="70d81-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="70d81-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="70d81-116">varchar(256)-Wert</span><span class="sxs-lookup"><span data-stu-id="70d81-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="70d81-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="70d81-117">Unique</span></span>  <br/> |<span data-ttu-id="70d81-118">Dies ist die Quelle des Endes Bandbreite eingeführt wird.</span><span class="sxs-lookup"><span data-stu-id="70d81-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="70d81-119">Beschrieben werden, in dem der Grenzwert für Bandbreite (beispielsweise "Richtlinienserver", "Server aktivieren" oder "Modalität") stammt.</span><span class="sxs-lookup"><span data-stu-id="70d81-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

