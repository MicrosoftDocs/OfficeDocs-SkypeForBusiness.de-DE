---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. '
ms.openlocfilehash: 7b2def71eee17c81b6f178a18d4c248557a0f022
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885648"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="8033e-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8033e-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="8033e-104">Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="8033e-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="8033e-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8033e-105">Examples</span></span>
<span data-ttu-id="8033e-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8033e-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8033e-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="8033e-107">Example 1</span></span>

<span data-ttu-id="8033e-108">Das folgende Beispiel verbraucht und die Cloud Connector Appliance vom Hostserver deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="8033e-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="8033e-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="8033e-109">Example 2</span></span>

<span data-ttu-id="8033e-110">Im nächste Beispiel verbraucht und das Entfernen die ausgeführte Appliance Cloud Connector auf dem Hostserver deinstalliert, auch wenn der ausgleichen-Prozess konnte nicht:</span><span class="sxs-lookup"><span data-stu-id="8033e-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="8033e-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="8033e-111">Example 3</span></span>

<span data-ttu-id="8033e-112">Im nächste Beispiel werden eine Cloud-Connector Sicherungsversion ohne Bestätigung des Benutzers deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="8033e-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="8033e-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8033e-113">Detailed Description</span></span>
<span data-ttu-id="8033e-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8033e-114"></span></span>

<span data-ttu-id="8033e-115">Wenn Sie die aktuelle ausgeführte Version von Cloud-Connector deinstallieren, werden ausgleichen Services zuerst auf dem Vermittlungsserver und Edge-Server gleichzeitige Anrufe beendet ist, bevor Sie die virtuellen Computer deinstallieren können ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8033e-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="8033e-116">Wenn Sie eine Sicherungsversion deinstallieren, wird kein Ausgleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8033e-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8033e-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="8033e-117">Parameters</span></span>
<span data-ttu-id="8033e-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8033e-118"></span></span>

|<span data-ttu-id="8033e-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="8033e-119">**Parameter**</span></span>|<span data-ttu-id="8033e-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="8033e-120">**Required**</span></span>|<span data-ttu-id="8033e-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8033e-121">**Type**</span></span>|<span data-ttu-id="8033e-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8033e-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8033e-123">Version</span><span class="sxs-lookup"><span data-stu-id="8033e-123">Version</span></span> <br/> | <span data-ttu-id="8033e-124"> Optional</span><span class="sxs-lookup"><span data-stu-id="8033e-124">Optional</span></span> <br/> |<span data-ttu-id="8033e-125">System.String</span><span class="sxs-lookup"><span data-stu-id="8033e-125">System.String</span></span>  <br/> | <span data-ttu-id="8033e-126">Die Version der Cloud-Verbindung, die vom Hostserver deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="8033e-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="8033e-127">Wenn nichts angegeben ist, wird die zurzeit ausgeführte Version deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="8033e-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="8033e-128">Force</span><span class="sxs-lookup"><span data-stu-id="8033e-128">Force</span></span>  <br/> |<span data-ttu-id="8033e-129">Optional</span><span class="sxs-lookup"><span data-stu-id="8033e-129">Optional</span></span>  <br/> |<span data-ttu-id="8033e-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8033e-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8033e-p103">Wenn die zurzeit ausgeführte Version deinstalliert werden soll, wird versucht, Dienste auf dem Vermittlungsserver und dem Edgeserver auszugleichen, bevor die virtuellen Maschinen deinstalliert werden. Wenn Sie den Parameter „Force“ angeben, werden die virtuellen Maschinen auch dann deinstalliert, wenn der Dienstausgleich fehlgeschlagen ist. Dieser Parameter wird nur zum Deinstallieren der zurzeit ausgeführten Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="8033e-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="8033e-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="8033e-134">Confirm</span></span>  <br/> |<span data-ttu-id="8033e-135">Optional</span><span class="sxs-lookup"><span data-stu-id="8033e-135">Optional</span></span>  <br/> |<span data-ttu-id="8033e-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8033e-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8033e-137">Bitten Sie Bestätigung So deinstallieren Sie die virtuellen Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="8033e-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="8033e-138">Der Standardwert ist „TRUE“.</span><span class="sxs-lookup"><span data-stu-id="8033e-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8033e-139">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="8033e-139">Input Types</span></span>
<span data-ttu-id="8033e-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8033e-140"></span></span>

<span data-ttu-id="8033e-p105">Keine. Das Cmdlet „Uninstall-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="8033e-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8033e-143">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="8033e-143">Return Types</span></span>
<span data-ttu-id="8033e-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8033e-144"></span></span>

<span data-ttu-id="8033e-145">Keine </span><span class="sxs-lookup"><span data-stu-id="8033e-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8033e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8033e-146">See also</span></span>
<span data-ttu-id="8033e-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8033e-147"></span></span>

[<span data-ttu-id="8033e-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8033e-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="8033e-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8033e-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="8033e-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8033e-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="8033e-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8033e-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

