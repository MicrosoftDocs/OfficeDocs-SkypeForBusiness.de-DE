---
title: SessionCorrelation-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907080"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="d1427-104">SessionCorrelation-Tabelle</span><span class="sxs-lookup"><span data-stu-id="d1427-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="d1427-105">Die SessionCorrelation-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d1427-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="d1427-106">Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d1427-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="d1427-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="d1427-107">**Column**</span></span>|<span data-ttu-id="d1427-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="d1427-108">**Data Type**</span></span>|<span data-ttu-id="d1427-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="d1427-109">**Key/Index**</span></span>|<span data-ttu-id="d1427-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d1427-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1427-111">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="d1427-111">**Checksum**</span></span> <br/> |<span data-ttu-id="d1427-112">int</span><span class="sxs-lookup"><span data-stu-id="d1427-112">int</span></span>  <br/> |||
|<span data-ttu-id="d1427-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="d1427-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="d1427-114">int</span><span class="sxs-lookup"><span data-stu-id="d1427-114">int</span></span>  <br/> |<span data-ttu-id="d1427-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d1427-115">Primary</span></span>  <br/> |<span data-ttu-id="d1427-116">Eindeutige Zahl, identifiziert dieser A / V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="d1427-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="d1427-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="d1427-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="d1427-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1427-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d1427-119">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="d1427-119">Unique</span></span>  <br/> |<span data-ttu-id="d1427-120">Korrelierte Sitzungen müssen dieselbe Korrelations-ID</span><span class="sxs-lookup"><span data-stu-id="d1427-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="d1427-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d1427-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d1427-122">datetime</span><span class="sxs-lookup"><span data-stu-id="d1427-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="d1427-123">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d1427-123">For internal use only.</span></span>  <br/> |
   

