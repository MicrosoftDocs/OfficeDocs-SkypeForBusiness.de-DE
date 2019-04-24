---
title: ErrorCategory-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'ErrorCategory-Tabelle enthält den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung. Skype für Business Server 2015 verwendet standardmäßig die folgenden Klassifikationen:'
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213116"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cfdf3-104">ErrorCategory-Tabelle in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cfdf3-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cfdf3-105">ErrorCategory-Tabelle enthält den Anzeigenamen für jedes Skype für Business Server 2015-diagnoseklassifizierung.</span><span class="sxs-lookup"><span data-stu-id="cfdf3-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="cfdf3-106">Skype für Business Server 2015 verwendet standardmäßig die folgenden Klassifikationen:</span><span class="sxs-lookup"><span data-stu-id="cfdf3-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="cfdf3-107">0 – Erfolg</span><span class="sxs-lookup"><span data-stu-id="cfdf3-107">0 -- Success</span></span>
    
- <span data-ttu-id="cfdf3-108">1--Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="cfdf3-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="cfdf3-109">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="cfdf3-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="cfdf3-110">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cfdf3-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cfdf3-111">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="cfdf3-111">**Column**</span></span>|<span data-ttu-id="cfdf3-112">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="cfdf3-112">**Data Type**</span></span>|<span data-ttu-id="cfdf3-113">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="cfdf3-113">**Key/Index**</span></span>|<span data-ttu-id="cfdf3-114">**Details**</span><span class="sxs-lookup"><span data-stu-id="cfdf3-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cfdf3-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="cfdf3-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="cfdf3-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="cfdf3-116">tinyint</span></span>  <br/> |<span data-ttu-id="cfdf3-117">Primary</span><span class="sxs-lookup"><span data-stu-id="cfdf3-117">Primary</span></span>  <br/> |<span data-ttu-id="cfdf3-118">Eindeutiger Bezeichner für die Klassifikation.</span><span class="sxs-lookup"><span data-stu-id="cfdf3-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="cfdf3-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="cfdf3-119">**Name**</span></span> <br/> |<span data-ttu-id="cfdf3-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cfdf3-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="cfdf3-121">Wert und dem Anzeigenamen der Klassifikation zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cfdf3-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="cfdf3-122">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="cfdf3-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="cfdf3-123">0 – Erfolg</span><span class="sxs-lookup"><span data-stu-id="cfdf3-123">0 -- Success</span></span> <br/>  <span data-ttu-id="cfdf3-124">1--Erwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="cfdf3-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="cfdf3-125">2 – unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="cfdf3-125">2 - Unexpected failure</span></span> <br/> |
   

