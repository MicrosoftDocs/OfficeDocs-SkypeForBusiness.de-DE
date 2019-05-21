---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Das Cmdlet „Register-CcAppliance“ registriert Appliance-Informationen für einen PSTN-Standort in einer Onlinemandantenkonfiguration. Sie müssen eine Appliance registrieren, bevor diese bereitgestellt und mit dem Skype for Business Cloud Connector Edition-Verwaltungsdienst verwaltet werden kann.
ms.openlocfilehash: 9e15d7b8227bf9ee657d197041056703505ca7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287125"
---
# <a name="register-ccappliance"></a><span data-ttu-id="f5fd2-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f5fd2-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="f5fd2-105">Das Cmdlet „Register-CcAppliance“ registriert Appliance-Informationen für einen PSTN-Standort in einer Onlinemandantenkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="f5fd2-106">Sie müssen eine Appliance registrieren, bevor diese bereitgestellt und mit dem Skype for Business Cloud Connector Edition-Verwaltungsdienst verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="f5fd2-107">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f5fd2-107">Examples</span></span>
<span data-ttu-id="f5fd2-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f5fd2-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="f5fd2-109">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="f5fd2-109">Example 1</span></span>

<span data-ttu-id="f5fd2-110">Im folgenden Beispiel werden die aktuellen Appliance-Informationen in einer Onlinemandantenkonfiguration registriert:</span><span class="sxs-lookup"><span data-stu-id="f5fd2-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="f5fd2-111">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="f5fd2-111">Example 2</span></span>

<span data-ttu-id="f5fd2-112">Im nächsten Beispiel wird die Konfiguration lokal auf eine Registrierung überprüft, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen:</span><span class="sxs-lookup"><span data-stu-id="f5fd2-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="f5fd2-113">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="f5fd2-113">Example 3</span></span>

<span data-ttu-id="f5fd2-114">Im nächsten Beispiel wird die aktuelle Appliance unter dem Namen „Appliance1“ am PSTN-Standort „Site1“ registriert:</span><span class="sxs-lookup"><span data-stu-id="f5fd2-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="f5fd2-115">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5fd2-115">Detailed Description</span></span>
<span data-ttu-id="f5fd2-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f5fd2-116"></span></span>

<span data-ttu-id="f5fd2-117">Sie müssen den Namen und das Kennwort für das Administratorkonto des Mandanten angeben.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="f5fd2-118">Verwenden Sie das Konto, das Sie für die Onlineverwaltung von Cloud Connector erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="f5fd2-119">Befolgen Sie in Version 1.4.2 und älteren Versionen die Anweisungen zum Bereitstellen des Kennworts für externes Zertifikat, des Administratorkennworts für den sicheren Modus, des Domänenadministrator Kennworts und des VM-Administratorkennworts.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="f5fd2-120">Befolgen Sie in Version 2,0 und höher die Anweisungen zum Bereitstellen des externen Zertifikats Kennworts, des CceService-Kennworts und des CABackupFile-Kennworts.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="f5fd2-121">Starten Sie nach Abschluss der Registrierung den Cloud Connector-Verwaltungsdienst neu, und melden Sie sich bei den Diensten als CceService-Konto an.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="f5fd2-p104">„SiteName“ in Kombination mit dem externen Edgeserver-FQDN in der Datei „CloudConnector.ini“ gilt als PSTN-Standortidentität. Wenn weder „SiteName“ noch der externe Edgeserver-FQDN zum Registrieren eines Standorts verwendet wurde, wird in einer Onlinemandantenkonfiguration ein neuer Standort für diese Appliance erstellt. Wenn eine PSTN-Standortidentität gefunden wird, verwendet ein PSTN-Standort diese Identität, und die Appliance wird an diesem PSTN-Standort registriert. </span><span class="sxs-lookup"><span data-stu-id="f5fd2-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="f5fd2-125">In der folgenden Situation schlägt das Cmdlet fehl und weist darauf hin, dass „Site1“ bereits registriert ist: </span><span class="sxs-lookup"><span data-stu-id="f5fd2-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="f5fd2-126">	„SiteName“ entspricht „Site1“, und der externe Edgeserver-FQDN lautet „edgserver1.contoso.com“. </span><span class="sxs-lookup"><span data-stu-id="f5fd2-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="f5fd2-127">Der „SiteName“ eines PSTN-Standorts entspricht „Site1“, und der externe Edgeserver-FQDN lautet „edgserver.contoso.com“.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="f5fd2-128">Ein PSTN-Standort mit dem „SiteName“ „NewSite“ und dem externen Edgeserver-FQDN „edgserver1.contoso.com“ wurde registriert. </span><span class="sxs-lookup"><span data-stu-id="f5fd2-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="f5fd2-p105">„ApplianceName“ in Kombination mit dem Vermittlungsserver-FQDN in der Datei „CloudConnector.ini“ gilt als Appliance-Identität. Wenn weder „ApplianceName“ noch der Vermittlungsserver-FQDN zum Registrieren einer Appliance verwendet wurde, wird in der Onlinemandantenkonfiguration eine neue Appliance erstellt. Wenn die Appliance bereits registriert ist, schlägt das Cmdlet fehl.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="f5fd2-132">In der folgenden Situation schlägt das Cmdlet fehl und weist darauf hin, dass die Appliance bereits registriert ist: </span><span class="sxs-lookup"><span data-stu-id="f5fd2-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="f5fd2-133">„ApplianceName“ entspricht „Appliance1“, und der Vermittlungsserver-FQDN lautet „ms1.vdomain.com“.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="f5fd2-134">Am aktuellen PSTN-Standort wurde eine Appliance mit dem Namen „Appliance1“ und dem Vermittlungsserver-FQDN „ms.vdomain.com“ oder eine Appliance mit dem Namen „NewAppliance“ und dem Vermittlungsserver-FQDN „ms1.vdomain.com“ registriert.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="f5fd2-135">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5fd2-135">Parameters</span></span>
<span data-ttu-id="f5fd2-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f5fd2-136"></span></span>

|<span data-ttu-id="f5fd2-137">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="f5fd2-137">**Parameter**</span></span>|<span data-ttu-id="f5fd2-138">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="f5fd2-138">**Required**</span></span>|<span data-ttu-id="f5fd2-139">**Typ**</span><span class="sxs-lookup"><span data-stu-id="f5fd2-139">**Type**</span></span>|<span data-ttu-id="f5fd2-140">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f5fd2-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5fd2-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="f5fd2-141">SiteName</span></span>  <br/> |<span data-ttu-id="f5fd2-142">Optional </span><span class="sxs-lookup"><span data-stu-id="f5fd2-142">Optional</span></span>  <br/> |<span data-ttu-id="f5fd2-143">System.String</span><span class="sxs-lookup"><span data-stu-id="f5fd2-143">System.String</span></span>  <br/> |<span data-ttu-id="f5fd2-p106">Name des PSTN-Standorts, für den die Appliance registriert ist. Der Standardwert ist der Wert „SiteName“ in der Datei „CloudConnector.ini“. </span><span class="sxs-lookup"><span data-stu-id="f5fd2-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="f5fd2-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="f5fd2-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="f5fd2-147">Optional </span><span class="sxs-lookup"><span data-stu-id="f5fd2-147">Optional</span></span>  <br/> |<span data-ttu-id="f5fd2-148">System.String</span><span class="sxs-lookup"><span data-stu-id="f5fd2-148">System.String</span></span>  <br/> |<span data-ttu-id="f5fd2-p107">Name der aktuellen Appliance. Der Standardwert ist der Computername des Hostservers.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="f5fd2-151">Local</span><span class="sxs-lookup"><span data-stu-id="f5fd2-151">Local</span></span>  <br/> |<span data-ttu-id="f5fd2-152">Optional</span><span class="sxs-lookup"><span data-stu-id="f5fd2-152">Optional</span></span>  <br/> |<span data-ttu-id="f5fd2-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f5fd2-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="f5fd2-154">Überprüft Konfigurationen lokal auf eine Registrierung, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f5fd2-155">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="f5fd2-155">Input Types</span></span>
<span data-ttu-id="f5fd2-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f5fd2-156"></span></span>

<span data-ttu-id="f5fd2-p108">Keine. Das Cmdlet „Register-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="f5fd2-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f5fd2-159">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="f5fd2-159">Return Types</span></span>
<span data-ttu-id="f5fd2-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f5fd2-160"></span></span>

<span data-ttu-id="f5fd2-161">Keine</span><span class="sxs-lookup"><span data-stu-id="f5fd2-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5fd2-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5fd2-162">See also</span></span>
<span data-ttu-id="f5fd2-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f5fd2-163"></span></span>

[<span data-ttu-id="f5fd2-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f5fd2-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="f5fd2-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f5fd2-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="f5fd2-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f5fd2-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="f5fd2-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f5fd2-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

