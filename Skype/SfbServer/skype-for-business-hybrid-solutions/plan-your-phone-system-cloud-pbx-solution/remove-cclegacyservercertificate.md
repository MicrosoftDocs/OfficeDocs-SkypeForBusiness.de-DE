---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003285"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Das Cmdlet „Remove-CcLegacyServerCertificate“ entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte ältere Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden für den Vermittlungsserver und den Edgeserver ausgestellte Zertifikate entfernt, nachdem Sie die Zertifikate erneuert haben:  
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  Rollen <br/> |Optional  <br/> |System.Array  <br/> |  Array von Cloud Connector-Serverrollen <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Remove-CcLegacyServerCertificate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

