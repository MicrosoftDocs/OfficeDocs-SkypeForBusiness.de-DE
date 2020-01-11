---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Das Cmdlet "Enter-CcUpdate" bereitet den Skype for Business Cloud Connector Edition-Hostserver für den Updateprozess vor, indem er in den Wartungsmodus versetzt wird. Die Appliance beendet sofort alle Dienste, beendet alle laufenden Anrufe und lehnt alle neuen Anrufe ab.
ms.openlocfilehash: 694faf7f03fb672ec61ee97db08fb61bcf0dc532
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003455"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="cce78-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="cce78-104">Enter-CcUpdate</span></span>

<span data-ttu-id="cce78-105">Das Cmdlet "Enter-CcUpdate" bereitet den Skype for Business Cloud Connector Edition-Hostserver für den Updateprozess vor, indem er in den Wartungsmodus versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="cce78-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="cce78-106">Die Appliance beendet sofort alle Dienste, beendet alle laufenden Anrufe und lehnt alle neuen Anrufe ab.</span><span class="sxs-lookup"><span data-stu-id="cce78-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="cce78-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="cce78-107">Parameters</span></span>

<span data-ttu-id="cce78-108">Keine</span><span class="sxs-lookup"><span data-stu-id="cce78-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="cce78-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cce78-109">Examples</span></span>
<span data-ttu-id="cce78-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cce78-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="cce78-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="cce78-111">Example 1</span></span>

<span data-ttu-id="cce78-112">Im folgenden Beispiel wird die Appliance auf den Updateprozess vorbereitet, indem sie in den Wartungsmodus versetzt wird:</span><span class="sxs-lookup"><span data-stu-id="cce78-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="cce78-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cce78-113">Detailed Description</span></span>
<span data-ttu-id="cce78-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cce78-114"></span></span>

<span data-ttu-id="cce78-115">Das Cmdlet "Enter-CcUpdate" beendet sofort alle Dienste, die alle laufenden Anrufe beenden, und die Appliance lehnt alle neuen Anrufe ab, die an andere Produktions-Appliances übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="cce78-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="cce78-116">Sie müssen sicherstellen, dass die verbleibenden Produktions-Appliances über genügend Kapazität verfügen, um die Anrufe von der Appliance zu verarbeiten, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cce78-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="cce78-p104">Der Wartungsmodus ist hilfreich, wenn zum Beispiel für Ihre Appliance automatische Updates aktiviert sind und Microsoft einen wichtigen Hotfix veröffentlicht. Außerdem ist der Wartungsmodus hilfreich, wenn Sie zwar beschließen, automatische Updates zu deaktivieren, aber regelmäßig manuelle Updates ausführen.</span><span class="sxs-lookup"><span data-stu-id="cce78-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="cce78-119">Nach der Installation der Updates kann die Appliance durch Ausführen des Cmdlets Exit-CcUpdate wieder in den Produktionsmodus versetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cce78-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cce78-120">Wenn Sie sich entscheiden, eine Cloud Connector-Appliance manuell zu aktualisieren, müssen Sie Sie innerhalb von 60 Tagen aktualisieren, nachdem Microsoft die nächste Version veröffentlicht hat.</span><span class="sxs-lookup"><span data-stu-id="cce78-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="cce78-121">Microsoft unterstützt die zuvor veröffentlichte Version von Cloud Connector für 60 Tage nach der Veröffentlichung der neuen Version.</span><span class="sxs-lookup"><span data-stu-id="cce78-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="cce78-122">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="cce78-122">Input Types</span></span>
<span data-ttu-id="cce78-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cce78-123"></span></span>

<span data-ttu-id="cce78-p106">Keine. Das Cmdlet „Enter-CCUpdate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="cce78-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cce78-126">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="cce78-126">Return Types</span></span>
<span data-ttu-id="cce78-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cce78-127"></span></span>

<span data-ttu-id="cce78-128">Keine </span><span class="sxs-lookup"><span data-stu-id="cce78-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cce78-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cce78-129">See also</span></span>
<span data-ttu-id="cce78-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cce78-130"></span></span>

[<span data-ttu-id="cce78-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="cce78-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

