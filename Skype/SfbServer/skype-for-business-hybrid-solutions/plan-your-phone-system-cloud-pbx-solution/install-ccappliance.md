---
title: Install-CcAppliance
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
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a><span data-ttu-id="8949c-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8949c-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="8949c-104">Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="8949c-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a><span data-ttu-id="8949c-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8949c-105">Examples</span></span>
<span data-ttu-id="8949c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8949c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8949c-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="8949c-107">Example 1</span></span>

<span data-ttu-id="8949c-108">Im folgende Beispiel wird eine neue Cloud-Connector Appliance auf dem Hostserver installiert:</span><span class="sxs-lookup"><span data-stu-id="8949c-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="8949c-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="8949c-109">Example 2</span></span>

<span data-ttu-id="8949c-110">Im folgende Beispiel werden Cloud Connector auf die neueste Version aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="8949c-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="8949c-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="8949c-111">Example 3</span></span>

<span data-ttu-id="8949c-112">Das folgende Beispiel entfernt alle Cloud Connector Anmeldeinformationen Cache auf dem Hostserver fordert den Benutzer an allen Anmeldeinformationen erneut, und installiert dann Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="8949c-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="8949c-113">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="8949c-113">Example 4</span></span>

<span data-ttu-id="8949c-114">Im folgenden Beispiel werden alle Bereitstellungsschritte in der PowerShell-Konsole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8949c-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="8949c-115">Der Parameter „-ShowStepsOnly“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8949c-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="8949c-116">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="8949c-116">Example 5</span></span>

<span data-ttu-id="8949c-117">Im folgenden Beispiel werden Konfigurationsdateien für die einzelnen Bereitstellungsschritte auf dem Hostserver generiert.</span><span class="sxs-lookup"><span data-stu-id="8949c-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="8949c-118">Konfigurationsdateien gespeichert, die \<ApplianceRoot\>\Instances\\< Version\>-Default\ExportedConfig-Ordner auf dem Hostserver:</span><span class="sxs-lookup"><span data-stu-id="8949c-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="8949c-119">Um den Appliance-Stamm zu ermitteln, führen Sie das Cmdlet „Get-CcApplianceDirectory“ aus. </span><span class="sxs-lookup"><span data-stu-id="8949c-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="8949c-120">Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="8949c-120">Example 6</span></span>

<span data-ttu-id="8949c-p102">Im folgenden Beispiel führt Cloud Connector die Bereitstellungsschritte 1, 2 und 3 aus, um virtuelle Switches zu erstellen, eine virtuelle AD-Maschine zu erstellen und den Domänendienst auf dem AD-Server zu installieren. Bereits ausgeführte Schritte werden übersprungen:</span><span class="sxs-lookup"><span data-stu-id="8949c-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="8949c-123">Der Parameter „SkipExistingObjects“ muss in Verbindung mit dem Parameter „Steps“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8949c-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8949c-124">Der Parameter „Steps“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8949c-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="8949c-125">Verwenden Sie diesen Parameter nicht, um eine Appliance bereitzustellen oder eine verwendete Appliance zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8949c-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="8949c-126">Um die Bereitstellungsschritte zu ermitteln, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8949c-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="8949c-127">Install-CcAppliance - ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="8949c-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="8949c-128">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8949c-128">Detailed Description</span></span>
<span data-ttu-id="8949c-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8949c-129"></span></span>

<span data-ttu-id="8949c-130">Das Cmdlet Install-CcAppliance wird zum Bereitstellen von Cloud-Connector für eine neue Appliance oder eines Upgrades eine vorhandene Appliance auf die neueste Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="8949c-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="8949c-131">Wenn Sie eine neue Appliance haben, müssen Sie unbedingt finden Sie unter Prepare Ihrer Umgebung für Cloud-Connector zunächst, führen Sie das Cmdlet Register-CcAppliance zum Registrieren der Appliance, und führen Sie das Cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="8949c-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="8949c-132">Weitere Informationen finden Sie unter [Bereitstellen einer einzelnen Website in der Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [mehrere Standorte in der Cloud Connector bereitstellen](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8949c-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="8949c-133">Wenn Sie eine vorhandene Bereitstellung von Cloud-Connector verfügen, und Sie aktualisieren möchten, führen Sie die Anweisungen in das [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8949c-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8949c-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="8949c-134">Parameters</span></span>
<span data-ttu-id="8949c-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8949c-135"></span></span>

|<span data-ttu-id="8949c-136">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="8949c-136">**Parameter**</span></span>|<span data-ttu-id="8949c-137">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="8949c-137">**Required**</span></span>|<span data-ttu-id="8949c-138">**Typ**</span><span class="sxs-lookup"><span data-stu-id="8949c-138">**Type**</span></span>|<span data-ttu-id="8949c-139">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8949c-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8949c-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="8949c-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="8949c-141">Optional</span><span class="sxs-lookup"><span data-stu-id="8949c-141">Optional</span></span>  <br/> |<span data-ttu-id="8949c-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8949c-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="8949c-p105"> Generiert Konfigurationsdateien für die einzelnen Bereitstellungsschritte. Dieser Parameter ist nur für die Problembehandlung vorgesehen. </span><span class="sxs-lookup"><span data-stu-id="8949c-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="8949c-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="8949c-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="8949c-146">Optional</span><span class="sxs-lookup"><span data-stu-id="8949c-146">Optional</span></span>  <br/> |<span data-ttu-id="8949c-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8949c-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8949c-p106">Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8949c-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="8949c-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="8949c-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="8949c-151">Optional</span><span class="sxs-lookup"><span data-stu-id="8949c-151">Optional</span></span>  <br/> |<span data-ttu-id="8949c-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8949c-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8949c-p107">Dieser Parameter muss in Verbindung mit dem Parameter „Steps“ verwendet werden. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8949c-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="8949c-155">Steps</span><span class="sxs-lookup"><span data-stu-id="8949c-155">Steps</span></span>  <br/> |<span data-ttu-id="8949c-156">Optional</span><span class="sxs-lookup"><span data-stu-id="8949c-156">Optional</span></span>  <br/> |<span data-ttu-id="8949c-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="8949c-157">System.Array</span></span>  <br/> |<span data-ttu-id="8949c-p108">Führt die Bereitstellungsschritte aus. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8949c-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="8949c-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="8949c-160">Upgrade</span></span>  <br/> |<span data-ttu-id="8949c-161">Optional</span><span class="sxs-lookup"><span data-stu-id="8949c-161">Optional</span></span>  <br/> |<span data-ttu-id="8949c-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8949c-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8949c-163">Aktualisiert eine vorhandene Cloud Connector-Installation auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="8949c-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="8949c-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="8949c-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="8949c-165">Optional</span><span class="sxs-lookup"><span data-stu-id="8949c-165">Optional</span></span>  <br/> |<span data-ttu-id="8949c-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8949c-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8949c-167">Entfernen Sie alle Cloud Connector Anmeldeinformationen im Cache.</span><span class="sxs-lookup"><span data-stu-id="8949c-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="8949c-168">Fordert den Benutzer auf, für die Installation neue Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="8949c-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8949c-169">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="8949c-169">Input Types</span></span>
<span data-ttu-id="8949c-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8949c-170"></span></span>

<span data-ttu-id="8949c-p110">Keine. Das Cmdlet „Install-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="8949c-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8949c-173">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="8949c-173">Return Types</span></span>
<span data-ttu-id="8949c-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8949c-174"></span></span>

<span data-ttu-id="8949c-175">Keine</span><span class="sxs-lookup"><span data-stu-id="8949c-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8949c-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8949c-176">See also</span></span>
<span data-ttu-id="8949c-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8949c-177"></span></span>

[<span data-ttu-id="8949c-178">Veröffentlichen von CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8949c-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="8949c-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8949c-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="8949c-180">Aufheben der Registrierung CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8949c-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="8949c-181">Deinstallieren von CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8949c-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

