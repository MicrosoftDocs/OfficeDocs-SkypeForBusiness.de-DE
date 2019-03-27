---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. '
ms.openlocfilehash: 8f1a8b7d99a555006c1d69ee52f2403e9bf0a874
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880214"
---
# <a name="install-ccappliance"></a><span data-ttu-id="9e88d-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9e88d-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="9e88d-104">Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="9e88d-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9e88d-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9e88d-105">Examples</span></span>
<span data-ttu-id="9e88d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9e88d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9e88d-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="9e88d-107">Example 1</span></span>

<span data-ttu-id="9e88d-108">Im folgende Beispiel wird eine neue Cloud-Connector Appliance auf dem Hostserver installiert:</span><span class="sxs-lookup"><span data-stu-id="9e88d-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="9e88d-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="9e88d-109">Example 2</span></span>

<span data-ttu-id="9e88d-110">Im folgende Beispiel werden Cloud Connector auf die neueste Version aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="9e88d-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="9e88d-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="9e88d-111">Example 3</span></span>

<span data-ttu-id="9e88d-112">Das folgende Beispiel entfernt alle Cloud Connector Anmeldeinformationen Cache auf dem Hostserver fordert den Benutzer an allen Anmeldeinformationen erneut, und installiert dann Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9e88d-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="9e88d-113">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="9e88d-113">Example 4</span></span>

<span data-ttu-id="9e88d-114">Im folgenden Beispiel werden alle Bereitstellungsschritte in der PowerShell-Konsole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9e88d-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="9e88d-115">Der Parameter „-ShowStepsOnly“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9e88d-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="9e88d-116">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="9e88d-116">Example 5</span></span>

<span data-ttu-id="9e88d-117">Im folgenden Beispiel werden Konfigurationsdateien für die einzelnen Bereitstellungsschritte auf dem Hostserver generiert.</span><span class="sxs-lookup"><span data-stu-id="9e88d-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="9e88d-118">Konfigurationsdateien gespeichert, die \<ApplianceRoot\>\Instances\\<Version\>-Default\ExportedConfig-Ordner auf dem Hostserver:</span><span class="sxs-lookup"><span data-stu-id="9e88d-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="9e88d-119">Um den Appliance-Stamm zu ermitteln, führen Sie das Cmdlet „Get-CcApplianceDirectory“ aus. </span><span class="sxs-lookup"><span data-stu-id="9e88d-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="9e88d-120">Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="9e88d-120">Example 6</span></span>

<span data-ttu-id="9e88d-p102">Im folgenden Beispiel führt Cloud Connector die Bereitstellungsschritte 1, 2 und 3 aus, um virtuelle Switches zu erstellen, eine virtuelle AD-Maschine zu erstellen und den Domänendienst auf dem AD-Server zu installieren. Bereits ausgeführte Schritte werden übersprungen:</span><span class="sxs-lookup"><span data-stu-id="9e88d-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="9e88d-123">Der Parameter „SkipExistingObjects“ muss in Verbindung mit dem Parameter „Steps“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e88d-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e88d-124">Der Parameter „Steps“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9e88d-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="9e88d-125">Verwenden Sie diesen Parameter nicht, um eine Appliance bereitzustellen oder eine verwendete Appliance zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9e88d-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="9e88d-126">Um die Bereitstellungsschritte zu ermitteln, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="9e88d-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="9e88d-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="9e88d-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="9e88d-128">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e88d-128">Detailed Description</span></span>
<span data-ttu-id="9e88d-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9e88d-129"></span></span>

<span data-ttu-id="9e88d-130">Das Cmdlet Install-CcAppliance wird zum Bereitstellen von Cloud-Connector für eine neue Appliance oder eines Upgrades eine vorhandene Appliance auf die neueste Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e88d-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="9e88d-131">Wenn Sie eine neue Appliance haben, müssen Sie unbedingt finden Sie unter Prepare Ihrer Umgebung für Cloud-Connector zunächst, führen Sie das Cmdlet Register-CcAppliance zum Registrieren der Appliance, und führen Sie das Cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="9e88d-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="9e88d-132">Weitere Informationen finden Sie unter [Bereitstellen einer einzelnen Website in der Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [mehrere Standorte in der Cloud Connector bereitstellen](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9e88d-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="9e88d-133">Wenn Sie eine vorhandene Bereitstellung von Cloud-Connector verfügen, und Sie aktualisieren möchten, führen Sie die Anweisungen in das [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9e88d-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9e88d-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e88d-134">Parameters</span></span>
<span data-ttu-id="9e88d-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9e88d-135"></span></span>

|<span data-ttu-id="9e88d-136">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="9e88d-136">**Parameter**</span></span>|<span data-ttu-id="9e88d-137">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="9e88d-137">**Required**</span></span>|<span data-ttu-id="9e88d-138">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9e88d-138">**Type**</span></span>|<span data-ttu-id="9e88d-139">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9e88d-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e88d-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="9e88d-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="9e88d-141">Optional</span><span class="sxs-lookup"><span data-stu-id="9e88d-141">Optional</span></span>  <br/> |<span data-ttu-id="9e88d-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9e88d-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="9e88d-p105"> Generiert Konfigurationsdateien für die einzelnen Bereitstellungsschritte. Dieser Parameter ist nur für die Problembehandlung vorgesehen. </span><span class="sxs-lookup"><span data-stu-id="9e88d-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="9e88d-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="9e88d-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="9e88d-146">Optional</span><span class="sxs-lookup"><span data-stu-id="9e88d-146">Optional</span></span>  <br/> |<span data-ttu-id="9e88d-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9e88d-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9e88d-p106">Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9e88d-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="9e88d-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="9e88d-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="9e88d-151">Optional</span><span class="sxs-lookup"><span data-stu-id="9e88d-151">Optional</span></span>  <br/> |<span data-ttu-id="9e88d-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9e88d-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9e88d-p107">Dieser Parameter muss in Verbindung mit dem Parameter „Steps“ verwendet werden. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9e88d-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="9e88d-155">Steps</span><span class="sxs-lookup"><span data-stu-id="9e88d-155">Steps</span></span>  <br/> |<span data-ttu-id="9e88d-156">Optional</span><span class="sxs-lookup"><span data-stu-id="9e88d-156">Optional</span></span>  <br/> |<span data-ttu-id="9e88d-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="9e88d-157">System.Array</span></span>  <br/> |<span data-ttu-id="9e88d-p108">Führt die Bereitstellungsschritte aus. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9e88d-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="9e88d-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="9e88d-160">Upgrade</span></span>  <br/> |<span data-ttu-id="9e88d-161">Optional</span><span class="sxs-lookup"><span data-stu-id="9e88d-161">Optional</span></span>  <br/> |<span data-ttu-id="9e88d-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9e88d-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9e88d-163">Aktualisiert eine vorhandene Cloud Connector-Installation auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="9e88d-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="9e88d-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="9e88d-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="9e88d-165">Optional</span><span class="sxs-lookup"><span data-stu-id="9e88d-165">Optional</span></span>  <br/> |<span data-ttu-id="9e88d-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9e88d-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9e88d-167">Entfernen Sie alle Cloud Connector Anmeldeinformationen im Cache.</span><span class="sxs-lookup"><span data-stu-id="9e88d-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="9e88d-168">Fordert den Benutzer auf, für die Installation neue Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="9e88d-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9e88d-169">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="9e88d-169">Input Types</span></span>
<span data-ttu-id="9e88d-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9e88d-170"></span></span>

<span data-ttu-id="9e88d-p110">Keine. Das Cmdlet „Install-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="9e88d-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9e88d-173">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="9e88d-173">Return Types</span></span>
<span data-ttu-id="9e88d-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9e88d-174"></span></span>

<span data-ttu-id="9e88d-175">Keine </span><span class="sxs-lookup"><span data-stu-id="9e88d-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e88d-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e88d-176">See also</span></span>
<span data-ttu-id="9e88d-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9e88d-177"></span></span>

[<span data-ttu-id="9e88d-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9e88d-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="9e88d-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9e88d-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="9e88d-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9e88d-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="9e88d-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="9e88d-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

