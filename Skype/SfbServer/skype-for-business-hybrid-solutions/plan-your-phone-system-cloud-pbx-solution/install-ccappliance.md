---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. '
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287272"
---
# <a name="install-ccappliance"></a><span data-ttu-id="487d5-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="487d5-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="487d5-104">Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="487d5-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="487d5-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="487d5-105">Examples</span></span>
<span data-ttu-id="487d5-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="487d5-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="487d5-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="487d5-107">Example 1</span></span>

<span data-ttu-id="487d5-108">Im folgenden Beispiel wird eine neue Cloud Connector-Appliance auf dem Hostserver installiert:</span><span class="sxs-lookup"><span data-stu-id="487d5-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="487d5-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="487d5-109">Example 2</span></span>

<span data-ttu-id="487d5-110">Im folgenden Beispiel wird Cloud Connector auf die neueste Version aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="487d5-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="487d5-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="487d5-111">Example 3</span></span>

<span data-ttu-id="487d5-112">Im folgenden Beispiel werden alle auf dem Hostserver zwischengespeicherten Cloud Connector-Anmeldeinformationen entfernt, der Benutzer wird aufgefordert, alle Anmeldeinformationen erneut anzugeben, und dann wird Cloud Connector installiert:</span><span class="sxs-lookup"><span data-stu-id="487d5-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="487d5-113">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="487d5-113">Example 4</span></span>

<span data-ttu-id="487d5-114">Im folgenden Beispiel werden alle Bereitstellungsschritte in der PowerShell-Konsole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="487d5-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="487d5-115">Der Parameter „-ShowStepsOnly“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="487d5-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="487d5-116">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="487d5-116">Example 5</span></span>

<span data-ttu-id="487d5-117">Im folgenden Beispiel werden Konfigurationsdateien für die einzelnen Bereitstellungsschritte auf dem Hostserver generiert.</span><span class="sxs-lookup"><span data-stu-id="487d5-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="487d5-118">Konfigurationsdateien werden im \<Ordner ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig auf dem Hostserver gespeichert:</span><span class="sxs-lookup"><span data-stu-id="487d5-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="487d5-119">Um den Appliance-Stamm zu ermitteln, führen Sie das Cmdlet „Get-CcApplianceDirectory“ aus. </span><span class="sxs-lookup"><span data-stu-id="487d5-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="487d5-120">Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="487d5-120">Example 6</span></span>

<span data-ttu-id="487d5-p102">Im folgenden Beispiel führt Cloud Connector die Bereitstellungsschritte 1, 2 und 3 aus, um virtuelle Switches zu erstellen, eine virtuelle AD-Maschine zu erstellen und den Domänendienst auf dem AD-Server zu installieren. Bereits ausgeführte Schritte werden übersprungen:</span><span class="sxs-lookup"><span data-stu-id="487d5-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="487d5-123">Der Parameter „SkipExistingObjects“ muss in Verbindung mit dem Parameter „Steps“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="487d5-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="487d5-124">Der Parameter „Steps“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="487d5-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="487d5-125">Verwenden Sie diesen Parameter nicht, um eine Appliance bereitzustellen oder eine verwendete Appliance zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="487d5-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="487d5-126">Um die Bereitstellungsschritte zu ermitteln, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="487d5-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="487d5-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="487d5-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="487d5-128">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="487d5-128">Detailed Description</span></span>
<span data-ttu-id="487d5-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="487d5-129"></span></span>

<span data-ttu-id="487d5-130">Das Cmdlet "Install-CcAppliance" wird verwendet, um den Cloud Connector für eine neue Appliance bereitzustellen oder um eine vorhandene Appliance auf die neueste Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="487d5-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="487d5-131">Wenn Sie über eine neue Appliance verfügen, lesen Sie Vorbereiten Ihrer Umgebung für Cloud Connector zuerst, führen Sie das Cmdlet Register-CcAppliance aus, um die Appliance zu registrieren, und führen Sie dann das Cmdlet Install-CcAppliance aus.</span><span class="sxs-lookup"><span data-stu-id="487d5-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="487d5-132">Weitere Informationen finden Sie unter [Bereitstelleneiner einzelnen Website in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Websites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="487d5-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="487d5-133">Wenn Sie über eine vorhandene Bereitstellung von Cloud Connector verfügen und ein Upgrade durchführen möchten, folgen Sie den Anweisungen unter [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="487d5-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="487d5-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="487d5-134">Parameters</span></span>
<span data-ttu-id="487d5-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="487d5-135"></span></span>

|<span data-ttu-id="487d5-136">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="487d5-136">**Parameter**</span></span>|<span data-ttu-id="487d5-137">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="487d5-137">**Required**</span></span>|<span data-ttu-id="487d5-138">**Typ**</span><span class="sxs-lookup"><span data-stu-id="487d5-138">**Type**</span></span>|<span data-ttu-id="487d5-139">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="487d5-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="487d5-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="487d5-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="487d5-141">Optional</span><span class="sxs-lookup"><span data-stu-id="487d5-141">Optional</span></span>  <br/> |<span data-ttu-id="487d5-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="487d5-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="487d5-p105"> Generiert Konfigurationsdateien für die einzelnen Bereitstellungsschritte. Dieser Parameter ist nur für die Problembehandlung vorgesehen. </span><span class="sxs-lookup"><span data-stu-id="487d5-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="487d5-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="487d5-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="487d5-146">Optional</span><span class="sxs-lookup"><span data-stu-id="487d5-146">Optional</span></span>  <br/> |<span data-ttu-id="487d5-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="487d5-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="487d5-p106">Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="487d5-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="487d5-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="487d5-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="487d5-151">Optional</span><span class="sxs-lookup"><span data-stu-id="487d5-151">Optional</span></span>  <br/> |<span data-ttu-id="487d5-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="487d5-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="487d5-p107">Dieser Parameter muss in Verbindung mit dem Parameter „Steps“ verwendet werden. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="487d5-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="487d5-155">Steps</span><span class="sxs-lookup"><span data-stu-id="487d5-155">Steps</span></span>  <br/> |<span data-ttu-id="487d5-156">Optional</span><span class="sxs-lookup"><span data-stu-id="487d5-156">Optional</span></span>  <br/> |<span data-ttu-id="487d5-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="487d5-157">System.Array</span></span>  <br/> |<span data-ttu-id="487d5-p108">Führt die Bereitstellungsschritte aus. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="487d5-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="487d5-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="487d5-160">Upgrade</span></span>  <br/> |<span data-ttu-id="487d5-161">Optional</span><span class="sxs-lookup"><span data-stu-id="487d5-161">Optional</span></span>  <br/> |<span data-ttu-id="487d5-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="487d5-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="487d5-163">Aktualisiert eine vorhandene Cloud Connector-Installation auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="487d5-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="487d5-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="487d5-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="487d5-165">Optional</span><span class="sxs-lookup"><span data-stu-id="487d5-165">Optional</span></span>  <br/> |<span data-ttu-id="487d5-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="487d5-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="487d5-167">Entfernen Sie alle Anmeldeinformationen für den Cloud Connector im Cache.</span><span class="sxs-lookup"><span data-stu-id="487d5-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="487d5-168">Fordert den Benutzer auf, für die Installation neue Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="487d5-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="487d5-169">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="487d5-169">Input Types</span></span>
<span data-ttu-id="487d5-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="487d5-170"></span></span>

<span data-ttu-id="487d5-p110">Keine. Das Cmdlet „Install-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="487d5-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="487d5-173">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="487d5-173">Return Types</span></span>
<span data-ttu-id="487d5-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="487d5-174"></span></span>

<span data-ttu-id="487d5-175">Keine</span><span class="sxs-lookup"><span data-stu-id="487d5-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="487d5-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="487d5-176">See also</span></span>
<span data-ttu-id="487d5-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="487d5-177"></span></span>

[<span data-ttu-id="487d5-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="487d5-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="487d5-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="487d5-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="487d5-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="487d5-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="487d5-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="487d5-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

