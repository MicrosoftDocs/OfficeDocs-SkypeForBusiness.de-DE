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
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286936"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Das Cmdlet „Stop-CcLogging“ beendet die Generierung der Liste für ein- und ausgehende Anrufe für eine Skype for Business Cloud Connector Edition-Appliance.
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet:  
  
```
Stop-CcLogging
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Generierung der Liste für ein- und ausgehende Anrufe beendet, und die Cachedateien werden bereinigt:
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet „Stop-CcLogging“ beendet die Protokollierung ein- und ausgehender Anrufe in einer Appliance. Standardmäßig wird die Protokollierung nach vier Stunden automatisch beendet.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Optional <br/> | System.Management.Automation.SwitchParameter <br/> |Entfernt die Cachedateien für die Protokollierung.   <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Stop-CcLogging“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

