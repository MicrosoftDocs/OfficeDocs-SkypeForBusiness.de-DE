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
# <a name="get-cccredential"></a>Get-CcCredential
 
Das Cmdlet „Get-CcCredential“ gibt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung zurück.  
  
Mit Version 2,0 und höher können Sie auch den-DisplayPassword-Parameter verwenden, um die Kennwörter für TenantAdmin, DomainAdmin und VMAdmin anzuzeigen.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Anmeldeinformationen des Domänenadministrators der Domäne für Cloud Connector-VMs zurückgegeben:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet „Get-CcCredential“ gibt die Anmeldeinformationen für den angegebenen Kontotyp zurück. Diese Anmeldeinformationen werden von dem Administrator angegeben, der die Cmdlets „Register-CcAppliance“ und „Install-CcAppliance“ bei der Bereitstellung der aktuellen Appliance ausführt.  
  
Das Cmdlet „Get-CcCredential“ gibt eine Instanz des Objekts „System.Management.Automation.PSCredential“ zurück. Die Kennworteigenschaft des zurückgegebenen Objekts lautet „System.Security.SecureString“.
  
Wenn Sie das Domänenadministratorkennwort als Klartext abrufen möchten, muss das Kennwort durch Ihr aktuelles Anmeldekonto auf dem Hostserver eingegeben werden. Öffnen Sie dann eine PowerShell-Konsole als Administrator, und führen Sie das folgende Skript aus:
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  AccountType <br/> |Erforderlich  <br/> | System.String <br/> | Für „AccountType“ sind die folgenden Werte möglich: <br/>  VmAdmin: der lokale Administrator der virtuellen Cloud Connector-Computer. <br/>  „DomainAdmin“: Der Domänenadministrator einer Domäne für Cloud Connector-VMs. <br/>  „SafeModeAdmin“: Der „SafeModeAdmin“ eines Domänencontrollers für Cloud Connector-VMs <br/>  „ExternalCert“: Das Konto eines externen Zertifikats, das auf dem Edgeserver installiert ist <br/>  „TenantAdmin“: Der Administrator des Office 365-Mandanten <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CcCredential“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Das Cmdlet „Get-CcCredential“ gibt eine Instanz des Objekts „System.Management.Automation.PSCredential“ zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

