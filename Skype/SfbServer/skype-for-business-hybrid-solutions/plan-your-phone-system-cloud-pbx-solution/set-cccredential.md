---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. '
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824209"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest.  
  
Mit Cloud Connector, Version 2,0 und höher, kann dieses Cmdlet auch die Kontoinformationen für den Virtual Machine-Administrator und für den Domänenadministrator einrichten.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden der Kontoname und das Kennwort für den Mandantenadministrator angegeben:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet „Set-CcCredential“ legt den Kontonamen und das Kennwort für den Mandantenadministrator fest. Für Versionen vor Version 2.0 muss dieser Administrator ein globaler Office 365-Administrator sein. Cloud Connector verwendet dieses Konto, um Konfigurationsinformationen abzurufen, Konfigurationsparameter einzurichten und den Appliance-Status auf die Office 365-Mandanten Konfiguration zu aktualisieren. Mit Version 2,0 und höher können Sie auch dieses Cmdlet verwenden, um die Kennwörter für die VmAdmin-und DomainAdmin-Konten zu aktualisieren.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  AccountType <br/> | Erforderlich <br/> |System.String  <br/> |  Der Parameterwert muss „TenantAdmin“ „VmAdmin“ oder „DomainAdmin“ lauten. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Set-CcCredential“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

