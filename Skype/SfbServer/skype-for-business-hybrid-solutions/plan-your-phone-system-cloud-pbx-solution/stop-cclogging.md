---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824159"
---
# <a name="stop-cclogging"></a><span data-ttu-id="383d9-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="383d9-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="383d9-104">Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.</span><span class="sxs-lookup"><span data-stu-id="383d9-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="383d9-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="383d9-105">Examples</span></span>
<span data-ttu-id="383d9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="383d9-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="383d9-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="383d9-107">Example 1</span></span>

<span data-ttu-id="383d9-108">Im folgenden Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet: </span><span class="sxs-lookup"><span data-stu-id="383d9-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="383d9-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="383d9-109">Example 2</span></span>

<span data-ttu-id="383d9-110">Im nächsten Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet, und die Cachedateien werden bereinigt:</span><span class="sxs-lookup"><span data-stu-id="383d9-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="383d9-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="383d9-111">Detailed Description</span></span>
<span data-ttu-id="383d9-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="383d9-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="383d9-113">Das Cmdlet „Stop-CcLogging“ beendet die Protokollierung ein- und ausgehender Anrufe in einer Appliance.</span><span class="sxs-lookup"><span data-stu-id="383d9-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="383d9-114">Standardmäßig wird die Protokollierung nach vier Stunden automatisch beendet.</span><span class="sxs-lookup"><span data-stu-id="383d9-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="383d9-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="383d9-115">Parameters</span></span>
<span data-ttu-id="383d9-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="383d9-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="383d9-117">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="383d9-117">**Parameter**</span></span>|<span data-ttu-id="383d9-118">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="383d9-118">**Required**</span></span>|<span data-ttu-id="383d9-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="383d9-119">**Type**</span></span>|<span data-ttu-id="383d9-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="383d9-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="383d9-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="383d9-121">RemoveCache</span></span> <br/> | <span data-ttu-id="383d9-122">Optional</span><span class="sxs-lookup"><span data-stu-id="383d9-122">Optional</span></span> <br/> | <span data-ttu-id="383d9-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="383d9-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="383d9-124">Entfernt die Cachedateien für die Protokollierung. </span><span class="sxs-lookup"><span data-stu-id="383d9-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="383d9-125">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="383d9-125">Input Types</span></span>
<span data-ttu-id="383d9-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="383d9-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="383d9-p102">Keine. Das Cmdlet „Stop-CcLogging“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="383d9-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="383d9-129">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="383d9-129">Return Types</span></span>
<span data-ttu-id="383d9-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="383d9-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="383d9-131">Keine</span><span class="sxs-lookup"><span data-stu-id="383d9-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="383d9-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="383d9-132">See also</span></span>
<span data-ttu-id="383d9-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="383d9-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="383d9-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="383d9-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="383d9-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="383d9-135">Start-CcLogging</span></span>](start-cclogging.md)
  

