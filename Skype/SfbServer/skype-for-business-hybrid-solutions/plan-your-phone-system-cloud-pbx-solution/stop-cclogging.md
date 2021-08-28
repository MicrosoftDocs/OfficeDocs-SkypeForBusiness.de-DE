---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Das Cmdlet Stop-CcLogging beendet die Generierung des Protokolls für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition Appliance.
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580340"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Das Cmdlet Stop-CcLogging beendet die Generierung des Protokolls für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition Appliance.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Generierung des Protokolls für ein- und ausgehende Anrufe beendet: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Generierung des Protokolls für ein- und ausgehende Anrufe beendet und die Cachedateien bereinigt:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das cmdlet Stop-CcLogging beendet die Protokollierung eingehender und ausgehender Anrufe in einer Appliance. Standardmäßig wird die Protokollierung nach vier Stunden automatisch beendet.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Optional <br/> | System.Management.Automation.SwitchParameter <br/> |Entfernt die Protokollierungscachedateien.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Stop-CcLogging akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

