---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Das Cmdlet „Convert-CcIsoToVhdx“ erstellt eine Datei einer virtuellen Basisfestplatte (VHDX) und verwendet dazu eine vom Kunden bereitgestellte ISO-Datei von Windows Server 2012 R2. Die VHDX-Datei wird bei der Bereitstellung von Skype for Business Cloud Connector Edition verwendet.
ms.openlocfilehash: 181d1af762d1f8c9c8f3e65a4411b317ab36ce4a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245369"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="9a715-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="9a715-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="9a715-p102">Das Cmdlet „Convert-CcIsoToVhdx“ erstellt eine Datei einer virtuellen Basisfestplatte (VHDX) und verwendet dazu eine vom Kunden bereitgestellte ISO-Datei von Windows Server 2012 R2. Die VHDX-Datei wird bei der Bereitstellung von Skype for Business Cloud Connector Edition verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a715-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="9a715-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a715-107">Parameters</span></span>

|<span data-ttu-id="9a715-108">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="9a715-108">**Parameter**</span></span>|<span data-ttu-id="9a715-109">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="9a715-109">**Required**</span></span>|<span data-ttu-id="9a715-110">**Typ**</span><span class="sxs-lookup"><span data-stu-id="9a715-110">**Type**</span></span>|<span data-ttu-id="9a715-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9a715-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a715-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="9a715-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="9a715-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9a715-113">Required</span></span> <br/> |<span data-ttu-id="9a715-114">System.String</span><span class="sxs-lookup"><span data-stu-id="9a715-114">System.String</span></span>  <br/> | <span data-ttu-id="9a715-115"> Der Pfad zur ISO-Datei von Windows Server 2012 R2 </span><span class="sxs-lookup"><span data-stu-id="9a715-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="9a715-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="9a715-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="9a715-117">Optional</span><span class="sxs-lookup"><span data-stu-id="9a715-117">Optional</span></span>  <br/> |<span data-ttu-id="9a715-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9a715-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9a715-p103">Wenn der Konvertierungsprozess beim Update von Windows fehlschlägt, können Sie versuchen, das Netzwerk und einen Proxy zu konfigurieren und Windows manuell zu aktualisieren. Wenn die manuellen Aufgaben abgeschlossen sind, können Sie dieses Cmdlet mit dem Parameter „-GeneralizeOnly“ ausführen. Dadurch werden die verbleibenden Aufträge ausgeführt. </span><span class="sxs-lookup"><span data-stu-id="9a715-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="9a715-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="9a715-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="9a715-122">Optional</span><span class="sxs-lookup"><span data-stu-id="9a715-122">Optional</span></span>  <br/> |<span data-ttu-id="9a715-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9a715-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9a715-p104">Um Windows zu aktualisieren, müssen Sie möglicherweise die Netzwerk-/Proxykonfiguration in der Basis-VM manuell anpassen. Wenn dieser Parameter angegeben ist, wird der Konvertierungsprozess vor dem Update von Windows angehalten. Nach Abschluss der manuellen Konfiguration können Sie den Prozess fortsetzen. </span><span class="sxs-lookup"><span data-stu-id="9a715-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="9a715-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9a715-127">Examples</span></span>
<span data-ttu-id="9a715-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9a715-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="9a715-129">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="9a715-129">Example 1</span></span>

<span data-ttu-id="9a715-130">Im folgenden Beispiel wird die VHDX-Basisdatei mithilfe einer ISO-Datei von Windows Server 2012 R2 unter „C:\Windows_Server_2012_R2-EN-US-x64.ISO“ vorbereitet: </span><span class="sxs-lookup"><span data-stu-id="9a715-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="9a715-131">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="9a715-131">Example 2</span></span>

<span data-ttu-id="9a715-132">Wenn das Cmdlet Convert-CcIsoToVhdx während ein Fehler auftritt Windows update, ist es wahrscheinlich aufgrund von falschen Netzwerk-Proxy-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a715-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="9a715-133">Sie können die Anweisungen in der Fehlermeldung befolgen und sich bei der Basis-VM anmelden, um das Problem zu beheben und Windows manuell zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9a715-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="9a715-134">Wenn die manuellen Aufgaben abgeschlossen sind, führen Sie das Cmdlet erneut mit dem Parameter „-GeneralizeOnly“ aus, um die verbleibenden Aufträge auszuführen:</span><span class="sxs-lookup"><span data-stu-id="9a715-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="9a715-135">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="9a715-135">Example 3</span></span>

<span data-ttu-id="9a715-136">Wenn für das Update von Windows eine manuelle Konfiguration notwendig ist, können Sie den Parameter „-PauseBeforeUpdate“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a715-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="9a715-137">Mit diesem Parameter wird Cloud Connector anhalten, bevor der Prozess für die Windows update.</span><span class="sxs-lookup"><span data-stu-id="9a715-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="9a715-138">Dann können Sie die manuelle Konfiguration vornehmen und den Konvertierungsprozess wie folgt fortsetzen:</span><span class="sxs-lookup"><span data-stu-id="9a715-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="9a715-139">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a715-139">Detailed Description</span></span>
<span data-ttu-id="9a715-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9a715-140"></span></span>

<span data-ttu-id="9a715-141">Das Convert-CcIsoToVhdx-Cmdlet erstellt eine Base, die VM zuerst einige grundlegenden Komponenten installiert, Cloud-Connector hängt von, und klicken Sie dann Windows-Updates installiert.</span><span class="sxs-lookup"><span data-stu-id="9a715-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="9a715-142">Schließlich verallgemeinert er den virtuellen Computer (Sysprep) um einen Basiskalender VHDX Datei abzurufen, die von den virtuellen Computern einer Cloud-Connector Appliance verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a715-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="9a715-143">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="9a715-143">Input Types</span></span>
<span data-ttu-id="9a715-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a715-144"></span></span>

<span data-ttu-id="9a715-p108">Keine. Das Cmdlet „Convert-CcIsoToVhdx“ akzeptiert keine Pipelineeingaben. </span><span class="sxs-lookup"><span data-stu-id="9a715-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="9a715-147">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="9a715-147">Return Types</span></span>
<span data-ttu-id="9a715-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a715-148"></span></span>

<span data-ttu-id="9a715-149">Keine </span><span class="sxs-lookup"><span data-stu-id="9a715-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a715-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a715-150">See also</span></span>
<span data-ttu-id="9a715-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a715-151"></span></span>

<span data-ttu-id="9a715-152">Keine</span><span class="sxs-lookup"><span data-stu-id="9a715-152">None</span></span>
  

