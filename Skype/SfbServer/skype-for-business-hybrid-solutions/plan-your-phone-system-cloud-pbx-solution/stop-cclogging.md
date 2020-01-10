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
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.
ms.openlocfilehash: 4528f7c1458093874f59f347585a736666a9ea08
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003165"
---
# <a name="stop-cclogging"></a><span data-ttu-id="2a2f7-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="2a2f7-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="2a2f7-104">Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.</span><span class="sxs-lookup"><span data-stu-id="2a2f7-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="2a2f7-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2a2f7-105">Examples</span></span>
<span data-ttu-id="2a2f7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2a2f7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="2a2f7-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="2a2f7-107">Example 1</span></span>

<span data-ttu-id="2a2f7-108">Im folgenden Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet: </span><span class="sxs-lookup"><span data-stu-id="2a2f7-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="2a2f7-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="2a2f7-109">Example 2</span></span>

<span data-ttu-id="2a2f7-110">Im nächsten Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet, und die Cachedateien werden bereinigt:</span><span class="sxs-lookup"><span data-stu-id="2a2f7-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="2a2f7-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a2f7-111">Detailed Description</span></span>
<span data-ttu-id="2a2f7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2a2f7-112"></span></span>

<span data-ttu-id="2a2f7-113">Das Cmdlet „Stop-CcLogging“ beendet die Protokollierung ein- und ausgehender Anrufe in einer Appliance.</span><span class="sxs-lookup"><span data-stu-id="2a2f7-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="2a2f7-114">Standardmäßig wird die Protokollierung nach vier Stunden automatisch beendet.</span><span class="sxs-lookup"><span data-stu-id="2a2f7-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2a2f7-115">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a2f7-115">Parameters</span></span>
<span data-ttu-id="2a2f7-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2a2f7-116"></span></span>

|<span data-ttu-id="2a2f7-117">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="2a2f7-117">**Parameter**</span></span>|<span data-ttu-id="2a2f7-118">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="2a2f7-118">**Required**</span></span>|<span data-ttu-id="2a2f7-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="2a2f7-119">**Type**</span></span>|<span data-ttu-id="2a2f7-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2a2f7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2a2f7-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="2a2f7-121">RemoveCache</span></span> <br/> | <span data-ttu-id="2a2f7-122">Optional</span><span class="sxs-lookup"><span data-stu-id="2a2f7-122">Optional</span></span> <br/> | <span data-ttu-id="2a2f7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2a2f7-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="2a2f7-124">Entfernt die Cachedateien für die Protokollierung. </span><span class="sxs-lookup"><span data-stu-id="2a2f7-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2a2f7-125">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="2a2f7-125">Input Types</span></span>
<span data-ttu-id="2a2f7-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a2f7-126"></span></span>

<span data-ttu-id="2a2f7-p102">Keine. Das Cmdlet „Stop-CcLogging“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="2a2f7-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2a2f7-129">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="2a2f7-129">Return Types</span></span>
<span data-ttu-id="2a2f7-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a2f7-130"></span></span>

<span data-ttu-id="2a2f7-131">Keine</span><span class="sxs-lookup"><span data-stu-id="2a2f7-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a2f7-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a2f7-132">See also</span></span>
<span data-ttu-id="2a2f7-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2a2f7-133"></span></span>

[<span data-ttu-id="2a2f7-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="2a2f7-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="2a2f7-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="2a2f7-135">Start-CcLogging</span></span>](start-cclogging.md)
  

