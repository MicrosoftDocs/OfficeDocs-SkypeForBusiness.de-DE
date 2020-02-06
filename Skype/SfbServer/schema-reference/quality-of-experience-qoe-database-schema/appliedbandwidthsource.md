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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Die Tabelle AppliedBandwidthSource ist eine unterstützende Tabelle. Jeder Datensatz stellt eine Quelle dar.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811443"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="54782-104">AppliedBandwidthSource-Tabelle</span><span class="sxs-lookup"><span data-stu-id="54782-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="54782-105">Die Tabelle AppliedBandwidthSource ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="54782-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="54782-106">Jeder Datensatz stellt eine Quelle dar.</span><span class="sxs-lookup"><span data-stu-id="54782-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="54782-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="54782-107">**Column**</span></span>|<span data-ttu-id="54782-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="54782-108">**Data Type**</span></span>|<span data-ttu-id="54782-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="54782-109">**Key/Index**</span></span>|<span data-ttu-id="54782-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="54782-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="54782-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="54782-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="54782-112">int</span><span class="sxs-lookup"><span data-stu-id="54782-112">int</span></span>  <br/> |<span data-ttu-id="54782-113">Primary</span><span class="sxs-lookup"><span data-stu-id="54782-113">Primary</span></span>  <br/> |<span data-ttu-id="54782-114">Eindeutige Nummer, die die Quelle kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="54782-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="54782-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="54782-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="54782-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="54782-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="54782-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="54782-117">Unique</span></span>  <br/> |<span data-ttu-id="54782-118">Hierbei handelt es sich um die Quelle des verhängten Bandbreitenlimits.</span><span class="sxs-lookup"><span data-stu-id="54782-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="54782-119">Es wird beschrieben, woher die Bandbreitengrenze stammt (beispielsweise "Richtlinienserver", "Server umwandeln" oder "Modalität").</span><span class="sxs-lookup"><span data-stu-id="54782-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

