---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287426"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="b756e-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="b756e-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="b756e-104">Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="b756e-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="b756e-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2. </span><span class="sxs-lookup"><span data-stu-id="b756e-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="b756e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b756e-106">Parameters</span></span>

<span data-ttu-id="b756e-107">Keine</span><span class="sxs-lookup"><span data-stu-id="b756e-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b756e-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b756e-108">Examples</span></span>
<span data-ttu-id="b756e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b756e-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="b756e-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="b756e-110">Example 1</span></span>

<span data-ttu-id="b756e-111">Der folgende Befehl versetzt die Appliance, auf der er ausgeführt wird, wieder in den Produktionsmodus: </span><span class="sxs-lookup"><span data-stu-id="b756e-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="b756e-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b756e-112">Detailed Description</span></span>
<span data-ttu-id="b756e-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b756e-113"></span></span>

<span data-ttu-id="b756e-114">Wenn Sie Appliances durch Angeben des Cmdlets „Enter-CcUpdate“ in den Wartungsmodus versetzt haben, werden diese durch das Cmdlet „Exit-CcUpdate“ wieder in den Produktionsmodus versetzt. </span><span class="sxs-lookup"><span data-stu-id="b756e-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="b756e-115">Weitere Informationen zum Versetzen von Appliances in den Wartungsmodus finden Sie unter „Enter-CcUpdate“.</span><span class="sxs-lookup"><span data-stu-id="b756e-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b756e-116">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="b756e-116">Input Types</span></span>
<span data-ttu-id="b756e-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b756e-117"></span></span>

<span data-ttu-id="b756e-p101">Keine. Das Cmdlet „Exit-CcUpdate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="b756e-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b756e-120">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="b756e-120">Return Types</span></span>
<span data-ttu-id="b756e-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b756e-121"></span></span>

<span data-ttu-id="b756e-122">Keine </span><span class="sxs-lookup"><span data-stu-id="b756e-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b756e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b756e-123">See also</span></span>
<span data-ttu-id="b756e-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b756e-124"></span></span>

[<span data-ttu-id="b756e-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="b756e-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

