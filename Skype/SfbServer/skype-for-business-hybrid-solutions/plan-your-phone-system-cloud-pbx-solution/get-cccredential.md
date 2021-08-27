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
ms.localizationpriority: medium
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Das cmdlet Get-CcCredential gibt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung zurück.
ms.openlocfilehash: 158f6e35f667410a0070e2f7030932bd6fc35ade
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596359"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Das cmdlet Get-CcCredential gibt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung zurück. 
  
Mit Version 2.0 und höher können Sie auch den Parameter "-DisplayPassword" verwenden, um die Kennwörter für TenantAdmin, DomainAdmin und VMAdmin anzuzeigen.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Anmeldeinformationen des Domänenadministrators der Domäne des virtuellen Cloud Connector-Computers zurückgegeben:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das cmdlet Get-CcCredential gibt die Anmeldeinformationen zum angegebenen Kontotyp zurück. Diese Anmeldeinformationen werden vom Administrator angegeben, der die Cmdlets Register-CcAppliance und Install-CcAppliance ausführt, wenn die aktuelle Appliance bereitgestellt wird. 
  
Das cmdlet Get-CcCredential gibt eine Instanz des Objekts System.Management.Automation.PSCredential zurück. Die Kennworteigenschaft des Rückgabeobjekts lautet "System.Security.SecureString".
  
Wenn Sie den Klartext des Domänenadministratorkennworts abrufen möchten, stellen Sie sicher, dass das Kennwort von Ihrem aktuellen Anmeldekonto auf dem Hostserver eingegeben wird. Öffnen Sie dann eine PowerShell-Konsole als Administrator, und führen Sie das folgende Skript aus:
  
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

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Erforderlich  <br/> | System.String <br/> | Der AccountType-Wert kann einer der folgenden Werte sein: <br/>  VmAdmin: der lokale Administrator von virtuellen Cloud Connector-Computern. <br/>  DomainAdmin: Domänenadministrator der Domäne des virtuellen Cloud Connector-Computers. <br/>  SafeModeAdmin: SafeModeAdmin des Cloud Connector-Domänencontrollers für virtuelle Computer. <br/>  ExternalCert: Konto des externen Zertifikats, das auf dem Edgeserver installiert ist. <br/>  TenantAdmin: Administrator des O365-Mandanten. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Get-CcCredential akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Das cmdlet Get-CcCredential gibt eine Instanz des Objekts System.Management.Automation.PSCredential zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

