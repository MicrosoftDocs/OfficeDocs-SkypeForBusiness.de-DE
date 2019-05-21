---
title: SessionCorrelation-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die Tabelle SessionCorrelation ist eine unterstützende Tabelle. Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294656"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="7597b-104">SessionCorrelation-Tabelle</span><span class="sxs-lookup"><span data-stu-id="7597b-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="7597b-105">Die Tabelle SessionCorrelation ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7597b-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="7597b-106">Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7597b-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="7597b-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="7597b-107">**Column**</span></span>|<span data-ttu-id="7597b-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="7597b-108">**Data Type**</span></span>|<span data-ttu-id="7597b-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="7597b-109">**Key/Index**</span></span>|<span data-ttu-id="7597b-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="7597b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7597b-111">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="7597b-111">**Checksum**</span></span> <br/> |<span data-ttu-id="7597b-112">int</span><span class="sxs-lookup"><span data-stu-id="7597b-112">int</span></span>  <br/> |||
|<span data-ttu-id="7597b-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="7597b-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="7597b-114">int</span><span class="sxs-lookup"><span data-stu-id="7597b-114">int</span></span>  <br/> |<span data-ttu-id="7597b-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7597b-115">Primary</span></span>  <br/> |<span data-ttu-id="7597b-116">Eindeutige Nummer, die diesen A/V-Konferenz Server kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="7597b-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="7597b-117">**CorrelationId**</span><span class="sxs-lookup"><span data-stu-id="7597b-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="7597b-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7597b-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7597b-119">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="7597b-119">Unique</span></span>  <br/> |<span data-ttu-id="7597b-120">Für Sitzungen, die korreliert sind, gibt es dieselbe Korrelations-ID.</span><span class="sxs-lookup"><span data-stu-id="7597b-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="7597b-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7597b-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7597b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="7597b-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="7597b-123">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="7597b-123">For internal use only.</span></span>  <br/> |
   

