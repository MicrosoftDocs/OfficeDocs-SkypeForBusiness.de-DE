---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Das Cmdlet „Unregister-CcAppliance“ hebt die Registrierung der aktuellen Skype for Business Cloud Connector Edition-Appliance an einem PSTN-Standort in der Onlinemandantenkonfiguration auf.
ms.openlocfilehash: 6ee21f66c2b189aff8c8aa7d831369536618b18c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892004"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="1dd73-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1dd73-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="1dd73-104">Das Cmdlet „Unregister-CcAppliance“ hebt die Registrierung der aktuellen Skype for Business Cloud Connector Edition-Appliance an einem PSTN-Standort in der Onlinemandantenkonfiguration auf.</span><span class="sxs-lookup"><span data-stu-id="1dd73-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="1dd73-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1dd73-105">Examples</span></span>
<span data-ttu-id="1dd73-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd73-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="1dd73-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="1dd73-107">Example 1</span></span>

<span data-ttu-id="1dd73-108">Im folgenden Beispiel wird die Registrierung einer aktuellen Appliance in der Onlinemandantenkonfiguration aufgehoben:</span><span class="sxs-lookup"><span data-stu-id="1dd73-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="1dd73-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="1dd73-109">Example 2</span></span>

<span data-ttu-id="1dd73-110">Im nächsten Beispiel wird die Konfiguration lokal auf die Aufhebung der Registrierung überprüft, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen:</span><span class="sxs-lookup"><span data-stu-id="1dd73-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="1dd73-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="1dd73-111">Example 3</span></span>

<span data-ttu-id="1dd73-112">Im nächsten Beispiel wird die Registrierung der aktuellen Appliance mit dem Namen „Appliance1“ am PSTN-Standort „Site1“ aufgehoben:</span><span class="sxs-lookup"><span data-stu-id="1dd73-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="1dd73-113">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dd73-113">Detailed Description</span></span>
<span data-ttu-id="1dd73-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd73-114"></span></span>

<span data-ttu-id="1dd73-p101">Ähnlich wie beim Cmdlet „Register-CcAppliance“ gilt „SiteName“ in Kombination mit dem externen Edgeserver-FQDN in der Datei „CloudConnector.ini“ als PSTN-Standortidentität. Entsprechend gilt „ApplianceName“ in Kombination mit dem Vermittlungsserver-FQDN in der Datei „CloudConnector.ini“ als Appliance-Identität.</span><span class="sxs-lookup"><span data-stu-id="1dd73-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="1dd73-117">Nach die Appliance aufgehoben wird, starten Sie neu den Connector Cloud-Verwaltungsdienst und melden Sie sich als das NetworkService-Konto.</span><span class="sxs-lookup"><span data-stu-id="1dd73-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1dd73-118">Parameter</span><span class="sxs-lookup"><span data-stu-id="1dd73-118">Parameters</span></span>
<span data-ttu-id="1dd73-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd73-119"></span></span>

|<span data-ttu-id="1dd73-120">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="1dd73-120">**Parameter**</span></span>|<span data-ttu-id="1dd73-121">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="1dd73-121">**Required**</span></span>|<span data-ttu-id="1dd73-122">**Typ**</span><span class="sxs-lookup"><span data-stu-id="1dd73-122">**Type**</span></span>|<span data-ttu-id="1dd73-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1dd73-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1dd73-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="1dd73-124">SiteName</span></span> <br/> |<span data-ttu-id="1dd73-125">Optional </span><span class="sxs-lookup"><span data-stu-id="1dd73-125">Optional</span></span>  <br/> |<span data-ttu-id="1dd73-126">System.String</span><span class="sxs-lookup"><span data-stu-id="1dd73-126">System.String</span></span>  <br/> |<span data-ttu-id="1dd73-p102">Name des PSTN-Standorts, an dem die Appliance registriert ist. Der Standardwert ist der Wert „SiteName“ in der Datei „CloudConnector.ini“.</span><span class="sxs-lookup"><span data-stu-id="1dd73-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="1dd73-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="1dd73-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="1dd73-130">Optional </span><span class="sxs-lookup"><span data-stu-id="1dd73-130">Optional</span></span>  <br/> |<span data-ttu-id="1dd73-131">System.String</span><span class="sxs-lookup"><span data-stu-id="1dd73-131">System.String</span></span>  <br/> |<span data-ttu-id="1dd73-p103">Name der aktuellen Appliance. Der Standardwert ist der Computername des Hostservers.</span><span class="sxs-lookup"><span data-stu-id="1dd73-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="1dd73-134">Local</span><span class="sxs-lookup"><span data-stu-id="1dd73-134">Local</span></span>  <br/> |<span data-ttu-id="1dd73-135">Optional</span><span class="sxs-lookup"><span data-stu-id="1dd73-135">Optional</span></span>  <br/> |<span data-ttu-id="1dd73-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1dd73-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1dd73-137">Überprüft die Konfiguration lokal auf eine Registrierung, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="1dd73-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1dd73-138">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="1dd73-138">Input Types</span></span>
<span data-ttu-id="1dd73-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd73-139"></span></span>

<span data-ttu-id="1dd73-p104">Keine. Das Cmdlet „Unregister-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="1dd73-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1dd73-142">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="1dd73-142">Return Types</span></span>
<span data-ttu-id="1dd73-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd73-143"></span></span>

<span data-ttu-id="1dd73-144">Keine </span><span class="sxs-lookup"><span data-stu-id="1dd73-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1dd73-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dd73-145">See also</span></span>
<span data-ttu-id="1dd73-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1dd73-146"></span></span>

[<span data-ttu-id="1dd73-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1dd73-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="1dd73-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1dd73-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="1dd73-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1dd73-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="1dd73-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1dd73-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

