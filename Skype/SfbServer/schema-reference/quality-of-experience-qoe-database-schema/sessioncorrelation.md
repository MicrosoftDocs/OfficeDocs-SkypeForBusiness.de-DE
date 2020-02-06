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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die Tabelle SessionCorrelation ist eine unterstützende Tabelle. Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805743"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="977a2-104">SessionCorrelation-Tabelle</span><span class="sxs-lookup"><span data-stu-id="977a2-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="977a2-105">Die Tabelle SessionCorrelation ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="977a2-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="977a2-106">Jeder Datensatz steht für einen CorrelationId, der für die Korrelation mehrerer Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="977a2-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="977a2-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="977a2-107">**Column**</span></span>|<span data-ttu-id="977a2-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="977a2-108">**Data Type**</span></span>|<span data-ttu-id="977a2-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="977a2-109">**Key/Index**</span></span>|<span data-ttu-id="977a2-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="977a2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="977a2-111">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="977a2-111">**Checksum**</span></span> <br/> |<span data-ttu-id="977a2-112">int</span><span class="sxs-lookup"><span data-stu-id="977a2-112">int</span></span>  <br/> |||
|<span data-ttu-id="977a2-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="977a2-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="977a2-114">int</span><span class="sxs-lookup"><span data-stu-id="977a2-114">int</span></span>  <br/> |<span data-ttu-id="977a2-115">Primary</span><span class="sxs-lookup"><span data-stu-id="977a2-115">Primary</span></span>  <br/> |<span data-ttu-id="977a2-116">Eindeutige Nummer, die diesen A/V-Konferenz Server kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="977a2-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="977a2-117">**CorrelationId**</span><span class="sxs-lookup"><span data-stu-id="977a2-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="977a2-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="977a2-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="977a2-119">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="977a2-119">Unique</span></span>  <br/> |<span data-ttu-id="977a2-120">Für Sitzungen, die korreliert sind, gibt es dieselbe Korrelations-ID.</span><span class="sxs-lookup"><span data-stu-id="977a2-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="977a2-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="977a2-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="977a2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="977a2-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="977a2-123">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="977a2-123">For internal use only.</span></span>  <br/> |
   

