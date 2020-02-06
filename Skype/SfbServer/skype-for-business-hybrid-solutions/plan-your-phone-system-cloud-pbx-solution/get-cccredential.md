---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 'Das Cmdlet „Get-CcCredential“ gibt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung zurück. '
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800395"
---
# <a name="get-cccredential"></a><span data-ttu-id="361e7-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="361e7-103">Get-CcCredential</span></span>
 
<span data-ttu-id="361e7-104">Das Cmdlet „Get-CcCredential“ gibt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung zurück. </span><span class="sxs-lookup"><span data-stu-id="361e7-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="361e7-105">Mit Version 2,0 und höher können Sie auch den-DisplayPassword-Parameter verwenden, um die Kennwörter für TenantAdmin, DomainAdmin und VMAdmin anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="361e7-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="361e7-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="361e7-106">Examples</span></span>
<span data-ttu-id="361e7-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="361e7-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="361e7-108">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="361e7-108">Example 1</span></span>

<span data-ttu-id="361e7-109">Im folgenden Beispiel werden die Anmeldeinformationen des Domänenadministrators der Domäne für Cloud Connector-VMs zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="361e7-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="361e7-110">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="361e7-110">Detailed Description</span></span>
<span data-ttu-id="361e7-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="361e7-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="361e7-p101">Das Cmdlet „Get-CcCredential“ gibt die Anmeldeinformationen für den angegebenen Kontotyp zurück. Diese Anmeldeinformationen werden von dem Administrator angegeben, der die Cmdlets „Register-CcAppliance“ und „Install-CcAppliance“ bei der Bereitstellung der aktuellen Appliance ausführt. </span><span class="sxs-lookup"><span data-stu-id="361e7-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="361e7-p102">Das Cmdlet „Get-CcCredential“ gibt eine Instanz des Objekts „System.Management.Automation.PSCredential“ zurück. Die Kennworteigenschaft des zurückgegebenen Objekts lautet „System.Security.SecureString“.</span><span class="sxs-lookup"><span data-stu-id="361e7-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="361e7-116">Wenn Sie das Domänenadministratorkennwort als Klartext abrufen möchten, muss das Kennwort durch Ihr aktuelles Anmeldekonto auf dem Hostserver eingegeben werden. Öffnen Sie dann eine PowerShell-Konsole als Administrator, und führen Sie das folgende Skript aus:</span><span class="sxs-lookup"><span data-stu-id="361e7-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="361e7-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="361e7-117">Parameters</span></span>
<span data-ttu-id="361e7-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="361e7-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="361e7-119">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="361e7-119">**Parameter**</span></span>|<span data-ttu-id="361e7-120">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="361e7-120">**Required**</span></span>|<span data-ttu-id="361e7-121">**Typ**</span><span class="sxs-lookup"><span data-stu-id="361e7-121">**Type**</span></span>|<span data-ttu-id="361e7-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="361e7-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="361e7-123"> AccountType</span><span class="sxs-lookup"><span data-stu-id="361e7-123">AccountType</span></span> <br/> |<span data-ttu-id="361e7-124">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="361e7-124">Required</span></span>  <br/> | <span data-ttu-id="361e7-125">System.String</span><span class="sxs-lookup"><span data-stu-id="361e7-125">System.String</span></span> <br/> | <span data-ttu-id="361e7-126">Für „AccountType“ sind die folgenden Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="361e7-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="361e7-127">VmAdmin: der lokale Administrator der virtuellen Cloud Connector-Computer.</span><span class="sxs-lookup"><span data-stu-id="361e7-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="361e7-128">„DomainAdmin“: Der Domänenadministrator einer Domäne für Cloud Connector-VMs.</span><span class="sxs-lookup"><span data-stu-id="361e7-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="361e7-129">„SafeModeAdmin“: Der „SafeModeAdmin“ eines Domänencontrollers für Cloud Connector-VMs</span><span class="sxs-lookup"><span data-stu-id="361e7-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="361e7-130">„ExternalCert“: Das Konto eines externen Zertifikats, das auf dem Edgeserver installiert ist</span><span class="sxs-lookup"><span data-stu-id="361e7-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="361e7-131">„TenantAdmin“: Der Administrator des Office 365-Mandanten</span><span class="sxs-lookup"><span data-stu-id="361e7-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="361e7-132">Eingabetypen</span><span class="sxs-lookup"><span data-stu-id="361e7-132">Input Types</span></span>
<span data-ttu-id="361e7-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="361e7-133"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="361e7-p103">Keine. Das Cmdlet „Get-CcCredential“ akzeptiert keine Pipelineeingaben.</span><span class="sxs-lookup"><span data-stu-id="361e7-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="361e7-136">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="361e7-136">Return Types</span></span>
<span data-ttu-id="361e7-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="361e7-137"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="361e7-138">Das Cmdlet „Get-CcCredential“ gibt eine Instanz des Objekts „System.Management.Automation.PSCredential“ zurück.</span><span class="sxs-lookup"><span data-stu-id="361e7-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="361e7-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="361e7-139">See also</span></span>
<span data-ttu-id="361e7-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="361e7-140"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="361e7-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="361e7-141">Set-CcCredential</span></span>](set-cccredential.md)
  

