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
description: Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen geändert.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824261"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Dieser Befehl wurde in Update-CcServerCertificate in Cloud Connector 2,0 und höheren Versionen geändert. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Interne Zertifikate des Cloud Connectors, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig, nachdem Sie von einem Zertifizierungsstellendienst ausgestellt wurden. Wenn Zertifikate in Kürze ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet „Renew-CcServerCertificate“ aus, um die Zertifikate zu erneuern. 
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Rollen  <br/> |Optional  <br/> |System.Array  <br/> |  Array von Cloud Connector-Serverrollen <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Renew-CcServerCertificate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

