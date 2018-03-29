---
title: Update-CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype für Business Cloud Connector Edition ein, wenn sie in der Nähe Ablauf sind oder bereits abgelaufen sind.
ms.openlocfilehash: 1971f754a7c850d72a3d870e7181738267c99101
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Das Cmdlet Update-CcServerCertificate erneuert die Zertifikate für Skype für Business Cloud Connector Edition ein, wenn sie in der Nähe Ablauf sind oder bereits abgelaufen sind. 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Zertifikate für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Zertifikate für den Vermittlungsserver und den Edgeserver erneuert, wenn sie in Kürze ablaufen oder bereits abgelaufen sind:
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Interne Zertifikate für den zentralen Verwaltungsspeicher, Vermittlungsserver und Edge-Server ausgestellt Cloud Connector gelten für zwei Jahre, nachdem sie aus einem Dienst Zertifizierungsstelle ausgestellt wurden. Zertifikate sind in der Nähe Ablauf oder bereits abgelaufen sind, führen Sie das Cmdlet Update-CcServerCertificate, um die Zertifikate zu erneuern. 
  
Mit diesem Befehl wird das Cmdlet erneuern CcServerCertificate in der Cloud Connector 2.0 und spätere Versionen ersetzt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Rollen  <br/> |Optional   <br/> |System.Array  <br/> |  Array von Cloud Connector-Serverrollen <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Update-CcServerCertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Erneuern CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

