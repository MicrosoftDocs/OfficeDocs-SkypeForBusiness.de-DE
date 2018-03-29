---
title: Erneuern CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Mit diesem Befehl wurde Update-CcServerCertificate in der Cloud Connector 2.0 und spätere Versionen geändert.
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a>Erneuern CcServerCertificate
 
Das Cmdlet „Renew-CcServerCertificate“ erneuert die Zertifikate für Skype for Business Cloud Connector Edition, wenn diese in Kürze ablaufen oder bereits abgelaufen sind. Mit diesem Befehl wurde Update-CcServerCertificate in der Cloud Connector 2.0 und spätere Versionen geändert. 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Interne Zertifikate für den zentralen Verwaltungsspeicher, Vermittlungsserver und Edge-Server ausgestellt Cloud Connector gelten für zwei Jahre, nachdem sie aus einem Dienst Zertifizierungsstelle ausgestellt wurden. Wenn Zertifikate in Kürze ablaufen oder bereits abgelaufen sind, führen Sie das Cmdlet „Renew-CcServerCertificate“ aus, um die Zertifikate zu erneuern. 
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Rollen  <br/> |Optional   <br/> |System.Array  <br/> |  Array von Cloud Connector-Serverrollen <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Renew-CcServerCertificate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Erneuern CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

