---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Das Cmdlet Restore CC-Credentials stellt alle Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung wieder her.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824241"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Das Cmdlet Restore CC-Credentials stellt alle Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung wieder her. 
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 2,1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

Das Cmdlet Restore-CcCredentials bereinigt alle Anmeldeinformationen und fordert Sie auf, alle für die aktuelle Skype for Business Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut einzugeben.
  
## <a name="parameters"></a>Parameter

Keine
  
## <a name="input-types"></a>Eingabetypen

Keine. Das Cmdlet "Restore-CcCredentials" akzeptiert keine Pipeline-Eingaben.
  
## <a name="return-types"></a>Rückgabetypen

Keine.
  
## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung wiederhergestellt:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Siehe auch

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

