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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Das Cmdlet Remove-CcLegacyServerCertificate entfernt Legacyserverzertifikate auf der zentralen Verwaltungs-Store, dem Vermittlungsserver und dem Edgeserver, nachdem Sie die Cmdlets "Renew-CcCACertificate" oder "Renew CcServerCertificate" ausgeführt haben.
ms.openlocfilehash: 93df3e8658cecdb4a6cc8b14d59d61a716dab8fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589949"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Das Cmdlet Remove-CcLegacyServerCertificate entfernt Legacyserverzertifikate auf der zentralen Verwaltungs-Store, dem Vermittlungsserver und dem Edgeserver, nachdem Sie die Cmdlets "Renew-CcCACertificate" oder "Renew CcServerCertificate" ausgeführt haben.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden legacyzertifikate entfernt, die für die zentrale Verwaltung Store, den Vermittlungsserver und den Edgeserver ausgestellt wurden, nachdem Sie die Zertifikate erneuert haben:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden Zertifikate entfernt, die für den Vermittlungsserver und den Edgeserver ausgestellt wurden, nachdem Sie die Zertifikate erneuert haben: 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Rollen <br/> |Optional  <br/> |System.Array  <br/> | Array von Cloud Connector-Serverrollen. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Remove-CcLegacyServerCertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

