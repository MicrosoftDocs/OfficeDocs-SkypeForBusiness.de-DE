---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest. '
ms.openlocfilehash: 547f0b87b006347a337a2c25222aecbd4f402669
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876641"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Das Cmdlet „Set-CcCredential“ legt die Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung fest.  
  
Mit Cloud Connector, Version 2.0 und höher kann mit diesem Cmdlet auch die Kontoinformationen für die virtuellen Computer-Administrator und Domänenadministrator festlegen.
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden der Kontoname und das Kennwort für den Mandantenadministrator angegeben:
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet „Set-CcCredential“ legt den Kontonamen und das Kennwort für den Mandantenadministrator fest. Für Versionen vor Version 2.0 muss dieser Administrator ein globaler Office 365-Administrator sein. Cloud-Connector wird dieses Konto verwendet, um Konfigurationsinformationen erhalten möchten, legen Sie die Konfiguration der Office 365-Mandanten Konfigurationsparameter und Aktualisierungsstatus Appliance. Mit Version 2.0 und höher, können Sie dieses Cmdlet zum Aktualisieren der Kennwörter für die Konten VmAdmin und DomainAdmin "verwenden.
  
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
  

