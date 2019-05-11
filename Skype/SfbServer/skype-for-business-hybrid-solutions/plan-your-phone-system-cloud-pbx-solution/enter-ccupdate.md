---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Das Enter-CcUpdate-Cmdlet wird die Skype für Business Cloud Connector Edition Hostserver für des Aktualisierungsvorgangs indem Sie ihn im Wartungsmodus ablegen vorbereitet. Die Appliance Isdrained – d. h., alle aktuellen Anrufe abgeschlossen, aber neue Aufrufe zurückgewiesen.
ms.openlocfilehash: 42c8f7fa668fa94040276e7749e93b5832d511cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929431"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="747a8-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="747a8-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="747a8-105">Das Enter-CcUpdate-Cmdlet wird die Skype für Business Cloud Connector Edition Hostserver für des Aktualisierungsvorgangs indem Sie ihn im Wartungsmodus ablegen vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="747a8-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="747a8-106">Die Einheit ist "ein Ausgleich vorgenommen" – d. h., alle aktuellen Anrufe abgeschlossen, aber neue Aufrufe zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="747a8-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="747a8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="747a8-107">Parameters</span></span>

<span data-ttu-id="747a8-108">Keine</span><span class="sxs-lookup"><span data-stu-id="747a8-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="747a8-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="747a8-109">Examples</span></span>
<span data-ttu-id="747a8-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="747a8-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="747a8-111">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="747a8-111">Example 1</span></span>

<span data-ttu-id="747a8-112">Im folgenden Beispiel wird die Appliance auf den Updateprozess vorbereitet, indem sie in den Wartungsmodus versetzt wird:</span><span class="sxs-lookup"><span data-stu-id="747a8-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="747a8-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="747a8-113">Detailed Description</span></span>
<span data-ttu-id="747a8-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="747a8-114"></span></span>

<span data-ttu-id="747a8-115">Das Enter-CcUpdate-Cmdlet wird sofort beenden Sie alle Dienste beenden alle laufenden Anrufe und die Anwendung lehnt keine neuen Anrufe, die auf andere Appliances Produktion übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="747a8-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="747a8-116">Sie müssen sicherstellen, dass die verbleibenden Produktion-Einheiten verfügen über genügend Kapazität, um Anrufe von der Anwendung, die Sie zum Aktualisieren vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="747a8-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="747a8-p104">Der Wartungsmodus ist hilfreich, wenn zum Beispiel für Ihre Appliance automatische Updates aktiviert sind und Microsoft einen wichtigen Hotfix veröffentlicht. Außerdem ist der Wartungsmodus hilfreich, wenn Sie zwar beschließen, automatische Updates zu deaktivieren, aber regelmäßig manuelle Updates ausführen.</span><span class="sxs-lookup"><span data-stu-id="747a8-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="747a8-119">Nach der Installation der Updates, kann die Appliance wieder zu Produktionsmodus geschaltet werden durch Ausführen des Cmdlets Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="747a8-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="747a8-120">Wenn Sie eine Cloud-Connector Appliance manuell aktualisieren möchten, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung von Microsoft der nächsten Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="747a8-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="747a8-121">Microsoft unterstützt die zuvor veröffentlichte Version von Cloud-Connector für 60 Tage nach der Veröffentlichung der neuen version</span><span class="sxs-lookup"><span data-stu-id="747a8-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="747a8-122">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="747a8-122">Input Types</span></span>
<span data-ttu-id="747a8-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="747a8-123"></span></span>

<span data-ttu-id="747a8-p106">Keine. Das Cmdlet „Enter-CCUpdate“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="747a8-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="747a8-126">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="747a8-126">Return Types</span></span>
<span data-ttu-id="747a8-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="747a8-127"></span></span>

<span data-ttu-id="747a8-128">Keine </span><span class="sxs-lookup"><span data-stu-id="747a8-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="747a8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="747a8-129">See also</span></span>
<span data-ttu-id="747a8-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="747a8-130"></span></span>

[<span data-ttu-id="747a8-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="747a8-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

