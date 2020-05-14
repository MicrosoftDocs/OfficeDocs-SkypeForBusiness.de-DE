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
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221569"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Das Cmdlet Set-CcCredential legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. 
  
Mit Cloud Connector Version 2,0 und höher können mit diesem Cmdlet auch die Kontoinformationen für den Administrator des virtuellen Computers und für den Domänenadministrator festgelegt werden.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel gibt den Kontonamen und das Kennwort für den mandantenadministrator an:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Set-CcCredential legt den Kontonamen und das Kennwort für den mandantenadministrator fest. Für Releases vor 2,0 muss dieser Administrator ein globaler Administrator sein. Cloud Connector verwendet dieses Konto, um Konfigurationsinformationen abzurufen, Konfigurationsparameter festzulegen und den Appliance-Status auf die Microsoft 365-oder Office 365-Organisationskonfiguration zu aktualisieren. Mit Version 2,0 und höher können Sie dieses Cmdlet auch zum Aktualisieren der Kennwörter für die "vmadmin"-und DomainAdmin-Konten verwenden.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Erforderlich <br/> |System.String  <br/> | Der Parameter Wert muss "TenantAdmin", "" vmadmin "" oder "DomainAdmin" lauten. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet "Sets-CcCredential" akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

