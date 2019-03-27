---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das Switch-CcVersion-Cmdlet trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten oder backup Einheit.
ms.openlocfilehash: 73ae9b4f93a2488dea29f3271565ac3d25759fd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872859"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Das Switch-CcVersion-Cmdlet trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten oder backup Einheit. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Dienste der aktuellen ausgeführten Appliance verbraucht, und anschließend der Wechsel zu einer neu bereitgestellten oder backup Einheit:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Dienste der aktuellen ausgeführten Appliance verbraucht und zwangsweise Dienste beendet, wenn die Dienste ausgleichen ein Fehler auftritt. Der Befehl wechselt dann in einer neu bereitgestellten oder backup Einheit:
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Switch-CcVersion-Cmdlet verbraucht der Connector Cloud-Dienste auf dem Vermittlungsserver und Edge-Server. Alle ausgeführten Anrufe werden abgeschlossen, aber die Anwendung lehnt keine neuen Anrufe. Nach dem ausgleichen, mit dem Cmdlet trennt die Verbindung der ausgeführten Appliance corporate und Internet-Netzwerke, alle virtuellen Computer, die an die Appliance gehören deaktiviert und verbindet Sie dann die Sicherung Appliance an das Unternehmen und das Internet.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Optional <br/> |System.Management.Automation.SwitchParameter  <br/> | Beendet Dienste erzwingen, wenn die Dienste ausgleichen fällt aus. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine 
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

