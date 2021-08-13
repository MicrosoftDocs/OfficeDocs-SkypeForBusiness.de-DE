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
description: Das cmdlet Switch-CcVersion trennt die ausgeführte Appliance und wechselt zu einer neu bereitgestellten oder Sicherungsanwendung.
ms.openlocfilehash: 1558f34d2388dc75bf4398ba15fc09cd36c439e2d70a39588ee697bc0ef04341
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320038"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Das cmdlet Switch-CcVersion trennt die ausgeführte Appliance und wechselt zu einer neu bereitgestellten oder Sicherungsanwendung. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Dienste der aktuell ausgeführten Appliance ausgeglichen und dann zu einer neu bereitgestellten oder Sicherungsanwendung gewechselt:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Dienste der aktuell ausgeführten Appliance geleert, und die Dienste werden bei einem Fehler beim Ausgleich der Dienste unterbrochen. Der Befehl wechselt dann zu einer neu bereitgestellten oder Sicherungsanwendung:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Mit dem Cmdlet Switch-CcVersion werden die Cloud Connector-Dienste auf dem Vermittlungsserver und dem Edgeserver ausgeglichen. Alle laufenden Anrufe werden abgeschlossen, die Appliance lehnt jedoch alle neuen Anrufe ab. Nach dem Ausgleich trennt das Cmdlet die ausgeführte Appliance von den Unternehmens- und Internetnetzwerken, deaktiviert alle zur Appliance gehörenden virtuellen Computer und verbindet die Sicherungs-Appliance mit den Unternehmens- und Internetnetzwerken.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Optional <br/> |System.Management.Automation.SwitchParameter  <br/> | Stoppt dienstecibly, wenn das Ausgleichen der Dienste fehlschlägt. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

