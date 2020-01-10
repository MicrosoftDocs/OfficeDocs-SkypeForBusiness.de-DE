---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese nahezu abgelaufen sind oder bereits abgelaufen sind.
ms.openlocfilehash: 920770b4ce77e893a7195d1326ea13ac73e0cc70
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003115"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese nahezu abgelaufen sind oder bereits abgelaufen sind. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Interne Zertifikate des Cloud Connectors, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig, nachdem Sie von einem Zertifizierungsstellendienst ausgestellt wurden. Wenn Zertifikate nahezu ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet Update-CcServerCertificate aus, um die Zertifikate zu erneuern. 
  
Dieser Befehl ersetzt das Cmdlet Renew-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Rollen  <br/> |Optional  <br/> |System.Array  <br/> |  Array von Cloud Connector-Serverrollen <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Update-CcServerCertificate akzeptiert keine Pipelineeingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

