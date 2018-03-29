---
title: Switch-CcVersion
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
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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

-
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

