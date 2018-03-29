---
title: Stop-CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.
ms.openlocfilehash: abecc5acc6a454b2965fbf79caadb23f2256e4cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="stop-cclogging"></a><span data-ttu-id="ca194-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="ca194-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="ca194-104">Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.</span><span class="sxs-lookup"><span data-stu-id="ca194-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="ca194-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ca194-105">Examples</span></span>
<span data-ttu-id="ca194-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ca194-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="ca194-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="ca194-107">Example 1</span></span>

<span data-ttu-id="ca194-108">Im folgenden Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet: </span><span class="sxs-lookup"><span data-stu-id="ca194-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="ca194-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="ca194-109">Example 2</span></span>

<span data-ttu-id="ca194-110">Im nächsten Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet, und die Cachedateien werden bereinigt:</span><span class="sxs-lookup"><span data-stu-id="ca194-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="ca194-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca194-111">Detailed Description</span></span>
<span data-ttu-id="ca194-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ca194-112"></span></span>

<span data-ttu-id="ca194-p101">Das Cmdlet „Stop-CcLogging“ beendet die Protokollierung ein- und ausgehender Anrufe in einer Appliance. Standardmäßig wird die Protokollierung nach vier Stunden automatisch beendet.</span><span class="sxs-lookup"><span data-stu-id="ca194-p101">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance. By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ca194-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca194-115">Parameters</span></span>
<span data-ttu-id="ca194-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ca194-116"></span></span>

|<span data-ttu-id="ca194-117">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="ca194-117">**Parameter**</span></span>|<span data-ttu-id="ca194-118">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="ca194-118">**Required**</span></span>|<span data-ttu-id="ca194-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ca194-119">**Type**</span></span>|<span data-ttu-id="ca194-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ca194-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ca194-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="ca194-121">RemoveCache</span></span> <br/> | <span data-ttu-id="ca194-122">Optional</span><span class="sxs-lookup"><span data-stu-id="ca194-122">Optional</span></span> <br/> | <span data-ttu-id="ca194-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ca194-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="ca194-124">Entfernt die Cachedateien für die Protokollierung. </span><span class="sxs-lookup"><span data-stu-id="ca194-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ca194-125">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="ca194-125">Input Types</span></span>
<span data-ttu-id="ca194-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ca194-126"></span></span>

<span data-ttu-id="ca194-p102">Keine. Das Cmdlet „Stop-CcLogging“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="ca194-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ca194-129">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="ca194-129">Return Types</span></span>
<span data-ttu-id="ca194-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ca194-130"></span></span>

<span data-ttu-id="ca194-131">Keine</span><span class="sxs-lookup"><span data-stu-id="ca194-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca194-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca194-132">See also</span></span>
<span data-ttu-id="ca194-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ca194-133"></span></span>

[<span data-ttu-id="ca194-134">Suche CcLog</span><span class="sxs-lookup"><span data-stu-id="ca194-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="ca194-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="ca194-135">Start-CcLogging</span></span>](start-cclogging.md)
  

