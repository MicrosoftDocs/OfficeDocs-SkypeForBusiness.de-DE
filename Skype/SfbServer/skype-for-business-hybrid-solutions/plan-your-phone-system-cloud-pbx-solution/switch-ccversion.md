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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824149"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Das Cmdlet Switch-CcVersion trennt die laufende Appliance und wechselt zu einer neu bereitgestellten oder Backup-Appliance. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Dienste der aktuell ausgeführten Appliance entladen und dann zu einer neu bereitgestellten oder Backup-Appliance gewechselt:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Dienste der aktuell ausgeführten Appliance entleert, und Dienste werden nicht mehr erzwungen, wenn das Entladen der Dienste fehlschlägt. Der Befehl wechselt dann zu einer neu bereitgestellten oder Backup-Appliance:
  
```powershell
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
  

