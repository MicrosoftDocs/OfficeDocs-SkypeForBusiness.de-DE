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
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Das Cmdlet "Wiederherstellen Cc-Credentials" stellt alle Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung wieder her.
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588437"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Das Cmdlet "Wiederherstellen Cc-Credentials" stellt alle Anmeldeinformationen der aktuellen Skype for Business Cloud Connector Edition-Bereitstellung wieder her. 
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

Das Cmdlet Restore-CcCredentials bereinigt alle Anmeldeinformationen und fordert Sie auf, alle für die aktuelle Skype for Business Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut einzugeben.
  
## <a name="parameters"></a>Parameter

Keine
  
## <a name="input-types"></a>Eingabetypen

Keine. Das cmdlet Restore-CcCredentials akzeptiert keine weitergeleitete Eingabe.
  
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
  

