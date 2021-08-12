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
description: Das Cmdlet Set-CcCredential legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest.
ms.openlocfilehash: 330326790f20add51dcaeb4468b17438c302c353c08076402e15f4d32985c117
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324135"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Das Cmdlet Set-CcCredential legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. 
  
Mit Cloud Connector, Version 2.0 und höher, kann dieses Cmdlet auch die Kontoinformationen für den Administrator des virtuellen Computers und für den Domänenadministrator festlegen.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden der Kontoname und das Kennwort für den Mandantenadministrator angegeben:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Set-CcCredential legt den Kontonamen und das Kennwort für den Mandantenadministrator fest. Für Versionen vor Version 2.0 muss dieser Administrator ein globaler Administrator sein. Cloud Connector verwendet dieses Konto, um Konfigurationsinformationen abzurufen, Konfigurationsparameter festzulegen und den Appliance-Status auf die Microsoft 365 oder Office 365 Organisationskonfiguration zu aktualisieren. Mit Version 2.0 und höher können Sie dieses Cmdlet auch verwenden, um die Kennwörter für die Konten "VmAdmin" und "DomainAdmin" zu aktualisieren.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Erforderlich <br/> |System.String  <br/> | Der Parameterwert muss "TenantAdmin", "VmAdmin" oder "DomainAdmin" sein. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Set-CcCredential akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

