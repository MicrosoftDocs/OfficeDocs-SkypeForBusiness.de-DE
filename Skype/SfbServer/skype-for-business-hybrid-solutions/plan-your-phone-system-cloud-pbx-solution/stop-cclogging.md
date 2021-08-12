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
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Das cmdlet Stop-CcLogging beendet das Generieren des Protokolls für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition Appliance.
ms.openlocfilehash: 7813acf9867829cadaa26d84a0e8a6c33f825ef45b9fca781840a44f94574930
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347560"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Das cmdlet Stop-CcLogging beendet das Generieren des Protokolls für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition Appliance.
  
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
  

