---
title: SessionCorrelation-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: Die SessionCorrelation-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird.
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212116"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="2b738-104">SessionCorrelation-Tabelle</span><span class="sxs-lookup"><span data-stu-id="2b738-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="2b738-105">Die SessionCorrelation-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2b738-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="2b738-106">Jeder Datensatz steht für eine CorrelationID die korrelieren mehrerer Sitzungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2b738-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="2b738-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="2b738-107">**Column**</span></span>|<span data-ttu-id="2b738-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="2b738-108">**Data Type**</span></span>|<span data-ttu-id="2b738-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="2b738-109">**Key/Index**</span></span>|<span data-ttu-id="2b738-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="2b738-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b738-111">**Prüfsumme**</span><span class="sxs-lookup"><span data-stu-id="2b738-111">**Checksum**</span></span> <br/> |<span data-ttu-id="2b738-112">int</span><span class="sxs-lookup"><span data-stu-id="2b738-112">int</span></span>  <br/> |||
|<span data-ttu-id="2b738-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="2b738-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="2b738-114">int</span><span class="sxs-lookup"><span data-stu-id="2b738-114">int</span></span>  <br/> |<span data-ttu-id="2b738-115">Primary</span><span class="sxs-lookup"><span data-stu-id="2b738-115">Primary</span></span>  <br/> |<span data-ttu-id="2b738-116">Eindeutige Zahl, identifiziert dieser A / V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="2b738-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="2b738-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="2b738-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="2b738-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b738-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2b738-119">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="2b738-119">Unique</span></span>  <br/> |<span data-ttu-id="2b738-120">Korrelierte Sitzungen müssen dieselbe Korrelations-ID</span><span class="sxs-lookup"><span data-stu-id="2b738-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="2b738-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2b738-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2b738-122">datetime</span><span class="sxs-lookup"><span data-stu-id="2b738-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="2b738-123">Nur zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="2b738-123">For internal use only.</span></span>  <br/> |
   

