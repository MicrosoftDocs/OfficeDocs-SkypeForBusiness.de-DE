---
title: Exit-CcUpdate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: f7b913fd6aaa77a18df66fd86a36d5d4838f69d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition.  
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2. 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Der folgende Befehl versetzt die Appliance, auf der er ausgeführt wird, wieder in den Produktionsmodus:  
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn Sie Appliances durch Angeben des Cmdlets „Enter-CcUpdate“ in den Wartungsmodus versetzt haben, werden diese durch das Cmdlet „Exit-CcUpdate“ wieder in den Produktionsmodus versetzt.  
  
Weitere Informationen zum Versetzen von Appliances in den Wartungsmodus finden Sie unter „Enter-CcUpdate“.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Exit-CcUpdate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Geben Sie CcUpdate](enter-ccupdate.md)
  

