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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801765"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="8cc38-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="8cc38-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="8cc38-104">Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="8cc38-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="8cc38-105">Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2. </span><span class="sxs-lookup"><span data-stu-id="8cc38-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="8cc38-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8cc38-106">Parameters</span></span>

<span data-ttu-id="8cc38-107">Keine</span><span class="sxs-lookup"><span data-stu-id="8cc38-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8cc38-108">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8cc38-108">Examples</span></span>
<span data-ttu-id="8cc38-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8cc38-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8cc38-110">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="8cc38-110">Example 1</span></span>

<span data-ttu-id="8cc38-111">Der folgende Befehl versetzt die Appliance, auf der er ausgeführt wird, wieder in den Produktionsmodus: </span><span class="sxs-lookup"><span data-stu-id="8cc38-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="8cc38-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cc38-112">Detailed Description</span></span>
<span data-ttu-id="8cc38-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8cc38-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8cc38-114">Wenn Sie Appliances durch Angeben des Cmdlets „Enter-CcUpdate“ in den Wartungsmodus versetzt haben, werden diese durch das Cmdlet „Exit-CcUpdate“ wieder in den Produktionsmodus versetzt. </span><span class="sxs-lookup"><span data-stu-id="8cc38-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="8cc38-115">Weitere Informationen zum Versetzen von Appliances in den Wartungsmodus finden Sie unter „Enter-CcUpdate“.</span><span class="sxs-lookup"><span data-stu-id="8cc38-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8cc38-116">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="8cc38-116">Input Types</span></span>
<span data-ttu-id="8cc38-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8cc38-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8cc38-p101">Keine. Das Cmdlet „Exit-CcUpdate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="8cc38-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8cc38-120">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="8cc38-120">Return Types</span></span>
<span data-ttu-id="8cc38-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8cc38-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8cc38-122">Keine </span><span class="sxs-lookup"><span data-stu-id="8cc38-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8cc38-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cc38-123">See also</span></span>
<span data-ttu-id="8cc38-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8cc38-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="8cc38-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="8cc38-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

