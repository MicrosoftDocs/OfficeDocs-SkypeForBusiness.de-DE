---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance.
ms.openlocfilehash: e63c5ea6d74e979f7fc9fe5a4c5eae97a0689e1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286929"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Dienste der aktuell ausgeführten Appliance entladen und dann zu einer neu bereitgestellten oder Backup-Appliance gewechselt:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Dienste der aktuell ausgeführten Appliance entleert, und Dienste werden nicht mehr erzwungen, wenn das Entladen der Dienste fehlschlägt. Der Befehl wechselt dann zu einer neu bereitgestellten oder Backup-Appliance:
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Switch-CcVersion entwässert die Cloud Connector-Dienste auf dem Vermittlungsserver und dem Edgeserver. Alle laufenden Anrufe werden abgeschlossen, aber die Appliance lehnt alle neuen Anrufe ab. Nach dem Entladen trennt das Cmdlet die ausgeführte Appliance vom Unternehmens-und Internet Netzwerk, deaktiviert alle virtuellen Computer, die zur Appliance gehören, und verbindet dann die Backup-Appliance mit den Unternehmens-und Internet Netzwerken.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Optional <br/> |System.Management.Automation.SwitchParameter  <br/> | Beendet Dienste zwangsläufig, wenn das Entladen der Dienste fehlschlägt. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

