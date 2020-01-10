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
ms.openlocfilehash: cccf500c6506c8ba3459631d5c823940907ad213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003325"
---
# <a name="install-ccappliance"></a><span data-ttu-id="b89a0-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b89a0-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="b89a0-104">Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. </span><span class="sxs-lookup"><span data-stu-id="b89a0-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b89a0-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b89a0-105">Examples</span></span>
<span data-ttu-id="b89a0-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b89a0-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b89a0-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="b89a0-107">Example 1</span></span>

<span data-ttu-id="b89a0-108">Im folgenden Beispiel wird eine neue Cloud Connector-Appliance auf dem Hostserver installiert:</span><span class="sxs-lookup"><span data-stu-id="b89a0-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="b89a0-109">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="b89a0-109">Example 2</span></span>

<span data-ttu-id="b89a0-110">Im folgenden Beispiel wird Cloud Connector auf die neueste Version aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="b89a0-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="b89a0-111">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="b89a0-111">Example 3</span></span>

<span data-ttu-id="b89a0-112">Im folgenden Beispiel werden alle auf dem Hostserver zwischengespeicherten Cloud Connector-Anmeldeinformationen entfernt, der Benutzer wird aufgefordert, alle Anmeldeinformationen erneut anzugeben, und dann wird Cloud Connector installiert:</span><span class="sxs-lookup"><span data-stu-id="b89a0-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="b89a0-113">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="b89a0-113">Example 4</span></span>

<span data-ttu-id="b89a0-114">Im folgenden Beispiel werden alle Bereitstellungsschritte in der PowerShell-Konsole angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b89a0-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="b89a0-115">Der Parameter „-ShowStepsOnly“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b89a0-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="b89a0-116">Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="b89a0-116">Example 5</span></span>

<span data-ttu-id="b89a0-117">Im folgenden Beispiel werden Konfigurationsdateien für die einzelnen Bereitstellungsschritte auf dem Hostserver generiert.</span><span class="sxs-lookup"><span data-stu-id="b89a0-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="b89a0-118">Konfigurationsdateien werden \<im ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig-Ordner auf dem Hostserver gespeichert:</span><span class="sxs-lookup"><span data-stu-id="b89a0-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="b89a0-119">Um den Appliance-Stamm zu ermitteln, führen Sie das Cmdlet „Get-CcApplianceDirectory“ aus. </span><span class="sxs-lookup"><span data-stu-id="b89a0-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="b89a0-120">Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="b89a0-120">Example 6</span></span>

<span data-ttu-id="b89a0-p102">Im folgenden Beispiel führt Cloud Connector die Bereitstellungsschritte 1, 2 und 3 aus, um virtuelle Switches zu erstellen, eine virtuelle AD-Maschine zu erstellen und den Domänendienst auf dem AD-Server zu installieren. Bereits ausgeführte Schritte werden übersprungen:</span><span class="sxs-lookup"><span data-stu-id="b89a0-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="b89a0-123">Der Parameter „SkipExistingObjects“ muss in Verbindung mit dem Parameter „Steps“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b89a0-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b89a0-124">Der Parameter „Steps“ ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b89a0-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="b89a0-125">Verwenden Sie diesen Parameter nicht, um eine Appliance bereitzustellen oder eine verwendete Appliance zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b89a0-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="b89a0-126">Um die Bereitstellungsschritte zu ermitteln, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b89a0-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="b89a0-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="b89a0-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="b89a0-128">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b89a0-128">Detailed Description</span></span>
<span data-ttu-id="b89a0-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b89a0-129"></span></span>

<span data-ttu-id="b89a0-130">Das Cmdlet "Install-CcAppliance" wird verwendet, um den Cloud Connector für eine neue Appliance bereitzustellen oder um eine vorhandene Appliance auf die neueste Version zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b89a0-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="b89a0-131">Wenn Sie über eine neue Appliance verfügen, lesen Sie Vorbereiten Ihrer Umgebung für Cloud Connector zuerst, führen Sie das Cmdlet Register-CcAppliance aus, um die Appliance zu registrieren, und führen Sie dann das Cmdlet Install-CcAppliance aus.</span><span class="sxs-lookup"><span data-stu-id="b89a0-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="b89a0-132">Weitere Informationen finden Sie unter [Bereitstelleneiner einzelnen Website in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Websites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b89a0-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="b89a0-133">Wenn Sie über eine vorhandene Bereitstellung von Cloud Connector verfügen und ein Upgrade durchführen möchten, folgen Sie den Anweisungen unter [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b89a0-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b89a0-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="b89a0-134">Parameters</span></span>
<span data-ttu-id="b89a0-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b89a0-135"></span></span>

|<span data-ttu-id="b89a0-136">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="b89a0-136">**Parameter**</span></span>|<span data-ttu-id="b89a0-137">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="b89a0-137">**Required**</span></span>|<span data-ttu-id="b89a0-138">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b89a0-138">**Type**</span></span>|<span data-ttu-id="b89a0-139">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b89a0-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b89a0-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="b89a0-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="b89a0-141">Optional</span><span class="sxs-lookup"><span data-stu-id="b89a0-141">Optional</span></span>  <br/> |<span data-ttu-id="b89a0-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b89a0-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="b89a0-p105"> Generiert Konfigurationsdateien für die einzelnen Bereitstellungsschritte. Dieser Parameter ist nur für die Problembehandlung vorgesehen. </span><span class="sxs-lookup"><span data-stu-id="b89a0-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="b89a0-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="b89a0-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="b89a0-146">Optional</span><span class="sxs-lookup"><span data-stu-id="b89a0-146">Optional</span></span>  <br/> |<span data-ttu-id="b89a0-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b89a0-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b89a0-p106">Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b89a0-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="b89a0-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="b89a0-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="b89a0-151">Optional</span><span class="sxs-lookup"><span data-stu-id="b89a0-151">Optional</span></span>  <br/> |<span data-ttu-id="b89a0-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b89a0-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b89a0-p107">Dieser Parameter muss in Verbindung mit dem Parameter „Steps“ verwendet werden. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b89a0-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="b89a0-155">Steps</span><span class="sxs-lookup"><span data-stu-id="b89a0-155">Steps</span></span>  <br/> |<span data-ttu-id="b89a0-156">Optional</span><span class="sxs-lookup"><span data-stu-id="b89a0-156">Optional</span></span>  <br/> |<span data-ttu-id="b89a0-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="b89a0-157">System.Array</span></span>  <br/> |<span data-ttu-id="b89a0-p108">Führt die Bereitstellungsschritte aus. Dieser Parameter ist nur für die Problembehandlung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b89a0-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="b89a0-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="b89a0-160">Upgrade</span></span>  <br/> |<span data-ttu-id="b89a0-161">Optional</span><span class="sxs-lookup"><span data-stu-id="b89a0-161">Optional</span></span>  <br/> |<span data-ttu-id="b89a0-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b89a0-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b89a0-163">Aktualisiert eine vorhandene Cloud Connector-Installation auf die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="b89a0-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="b89a0-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="b89a0-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="b89a0-165">Optional</span><span class="sxs-lookup"><span data-stu-id="b89a0-165">Optional</span></span>  <br/> |<span data-ttu-id="b89a0-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b89a0-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b89a0-167">Entfernen Sie alle Anmeldeinformationen für den Cloud Connector im Cache.</span><span class="sxs-lookup"><span data-stu-id="b89a0-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="b89a0-168">Fordert den Benutzer auf, für die Installation neue Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="b89a0-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b89a0-169">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="b89a0-169">Input Types</span></span>
<span data-ttu-id="b89a0-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b89a0-170"></span></span>

<span data-ttu-id="b89a0-p110">Keine. Das Cmdlet „Install-CcAppliance“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="b89a0-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b89a0-173">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="b89a0-173">Return Types</span></span>
<span data-ttu-id="b89a0-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b89a0-174"></span></span>

<span data-ttu-id="b89a0-175">Keine</span><span class="sxs-lookup"><span data-stu-id="b89a0-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b89a0-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b89a0-176">See also</span></span>
<span data-ttu-id="b89a0-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b89a0-177"></span></span>

[<span data-ttu-id="b89a0-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b89a0-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="b89a0-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b89a0-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="b89a0-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b89a0-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="b89a0-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b89a0-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

