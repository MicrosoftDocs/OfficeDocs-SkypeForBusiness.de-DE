---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Das Cmdlet Renew-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn sie bald ablaufen oder bereits abgelaufen sind. Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2.0 und neueren Versionen geändert.
ms.openlocfilehash: 632807f8d6b8dda7b3df6639e8f6166e8ac5e6a22381646616a0637779a9159a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340731"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Das Cmdlet Renew-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn sie bald ablaufen oder bereits abgelaufen sind. Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2.0 und neueren Versionen geändert. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Zertifikate für die zentrale Verwaltung Store, den Vermittlungsserver und den Edgeserver erneuert, wenn die Zertifikate bald ablaufen oder bereits abgelaufen sind:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie bald ablaufen oder bereits abgelaufen sind:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Interne Cloud Connector-Zertifikate, die an die zentrale Verwaltungs-Store, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre lang gültig, nachdem sie von einem Zertifizierungsstellendienst ausgestellt wurden. Wenn Zertifikate bald ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet Renew-CcServerCertificate aus, um die Zertifikate zu erneuern. 
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Rollen  <br/> |Optional  <br/> |System.Array  <br/> | Array von Cloud Connector-Serverrollen. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Renew-CcServerCertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

