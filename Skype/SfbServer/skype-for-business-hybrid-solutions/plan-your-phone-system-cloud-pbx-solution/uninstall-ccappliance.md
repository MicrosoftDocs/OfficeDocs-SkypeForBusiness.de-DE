---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003145"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="738d9-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="738d9-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="738d9-104">Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="738d9-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="738d9-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="738d9-105">Examples</span></span>
<span data-ttu-id="738d9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="738d9-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="738d9-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="738d9-107">Example 1</span></span>

<span data-ttu-id="738d9-108">Im folgenden Beispiel wird die Cloud Connector-Appliance vom Hostserver entwässert und deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="738d9-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="738d9-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="738d9-109">Example 2</span></span>

<span data-ttu-id="738d9-110">Im nächsten Beispiel wird die ausgeführte Cloud Connector-Appliance auf dem Hostserver entladen und zwangsläufig deinstalliert, auch wenn der Abfluss Vorgang fehlgeschlagen ist:</span><span class="sxs-lookup"><span data-stu-id="738d9-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="738d9-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="738d9-111">Example 3</span></span>

<span data-ttu-id="738d9-112">Im nächsten Beispiel wird eine Cloud Connector-Sicherungsversion ohne Bestätigung des Benutzers deinstalliert:</span><span class="sxs-lookup"><span data-stu-id="738d9-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="738d9-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="738d9-113">Detailed Description</span></span>
<span data-ttu-id="738d9-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="738d9-114"></span></span>

<span data-ttu-id="738d9-115">Wenn Sie die aktuelle Version von Cloud Connector deinstallieren, werden die Entwässerungs Dienste zunächst auf dem Vermittlungsserver und dem Edgeserver ausgeführt, damit gleichzeitige Anrufe beendet werden können, bevor die virtuellen Computer deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="738d9-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="738d9-116">Wenn Sie eine Sicherungsversion deinstallieren, wird kein Ausgleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="738d9-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="738d9-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="738d9-117">Parameters</span></span>
<span data-ttu-id="738d9-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="738d9-118"></span></span>

|<span data-ttu-id="738d9-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="738d9-119">**Parameter**</span></span>|<span data-ttu-id="738d9-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="738d9-120">**Required**</span></span>|<span data-ttu-id="738d9-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="738d9-121">**Type**</span></span>|<span data-ttu-id="738d9-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="738d9-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="738d9-123">Version</span><span class="sxs-lookup"><span data-stu-id="738d9-123">Version</span></span> <br/> | <span data-ttu-id="738d9-124"> Optional</span><span class="sxs-lookup"><span data-stu-id="738d9-124">Optional</span></span> <br/> |<span data-ttu-id="738d9-125">System.String</span><span class="sxs-lookup"><span data-stu-id="738d9-125">System.String</span></span>  <br/> | <span data-ttu-id="738d9-126">Die Version des Cloud Connectors, die vom Hostserver deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="738d9-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="738d9-127">Wenn nichts angegeben ist, wird die zurzeit ausgeführte Version deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="738d9-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="738d9-128">Force</span><span class="sxs-lookup"><span data-stu-id="738d9-128">Force</span></span>  <br/> |<span data-ttu-id="738d9-129">Optional</span><span class="sxs-lookup"><span data-stu-id="738d9-129">Optional</span></span>  <br/> |<span data-ttu-id="738d9-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="738d9-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="738d9-p103">Wenn die zurzeit ausgeführte Version deinstalliert werden soll, wird versucht, Dienste auf dem Vermittlungsserver und dem Edgeserver auszugleichen, bevor die virtuellen Maschinen deinstalliert werden. Wenn Sie den Parameter „Force“ angeben, werden die virtuellen Maschinen auch dann deinstalliert, wenn der Dienstausgleich fehlgeschlagen ist. Dieser Parameter wird nur zum Deinstallieren der zurzeit ausgeführten Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="738d9-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="738d9-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="738d9-134">Confirm</span></span>  <br/> |<span data-ttu-id="738d9-135">Optional</span><span class="sxs-lookup"><span data-stu-id="738d9-135">Optional</span></span>  <br/> |<span data-ttu-id="738d9-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="738d9-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="738d9-137">Bitten Sie die Benutzerbestätigung, die virtuellen Computer zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="738d9-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="738d9-138">Der Standardwert ist „TRUE“.</span><span class="sxs-lookup"><span data-stu-id="738d9-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="738d9-139">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="738d9-139">Input Types</span></span>
<span data-ttu-id="738d9-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="738d9-140"></span></span>

<span data-ttu-id="738d9-p105">Keine. Das Cmdlet „Uninstall-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="738d9-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="738d9-143">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="738d9-143">Return Types</span></span>
<span data-ttu-id="738d9-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="738d9-144"></span></span>

<span data-ttu-id="738d9-145">Keine</span><span class="sxs-lookup"><span data-stu-id="738d9-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="738d9-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="738d9-146">See also</span></span>
<span data-ttu-id="738d9-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="738d9-147"></span></span>

[<span data-ttu-id="738d9-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="738d9-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="738d9-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="738d9-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="738d9-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="738d9-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="738d9-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="738d9-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

