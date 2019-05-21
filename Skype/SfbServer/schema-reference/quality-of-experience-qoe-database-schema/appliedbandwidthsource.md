---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Die Tabelle AppliedBandwidthSource ist eine unterstützende Tabelle. Jeder Datensatz stellt eine Quelle dar.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295111"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="34089-104">AppliedBandwidthSource-Tabelle</span><span class="sxs-lookup"><span data-stu-id="34089-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="34089-105">Die Tabelle AppliedBandwidthSource ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="34089-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="34089-106">Jeder Datensatz stellt eine Quelle dar.</span><span class="sxs-lookup"><span data-stu-id="34089-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="34089-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="34089-107">**Column**</span></span>|<span data-ttu-id="34089-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="34089-108">**Data Type**</span></span>|<span data-ttu-id="34089-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="34089-109">**Key/Index**</span></span>|<span data-ttu-id="34089-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="34089-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34089-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="34089-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="34089-112">int</span><span class="sxs-lookup"><span data-stu-id="34089-112">int</span></span>  <br/> |<span data-ttu-id="34089-113">Primary</span><span class="sxs-lookup"><span data-stu-id="34089-113">Primary</span></span>  <br/> |<span data-ttu-id="34089-114">Eindeutige Nummer, die die Quelle kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="34089-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="34089-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="34089-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="34089-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="34089-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="34089-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="34089-117">Unique</span></span>  <br/> |<span data-ttu-id="34089-118">Hierbei handelt es sich um die Quelle des verhängten Bandbreitenlimits.</span><span class="sxs-lookup"><span data-stu-id="34089-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="34089-119">Es wird beschrieben, woher die Bandbreitengrenze stammt (beispielsweise "Richtlinienserver", "Server umwandeln" oder "Modalität").</span><span class="sxs-lookup"><span data-stu-id="34089-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

