---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003445"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Das Cmdlet „Exit-CcUpdate“ beendet den Wartungsmodus für das Update auf dem Hostserver von Skype for Business Cloud Connector Edition.  
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.  
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Der folgende Befehl versetzt die Appliance, auf der er ausgeführt wird, wieder in den Produktionsmodus:  
  
```powershell
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

[Enter-CcUpdate](enter-ccupdate.md)
  

