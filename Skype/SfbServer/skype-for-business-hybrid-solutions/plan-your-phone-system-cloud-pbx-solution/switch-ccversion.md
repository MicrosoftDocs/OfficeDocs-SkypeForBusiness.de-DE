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
ms.localizationpriority: medium
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Das cmdlet Switch-CcVersion trennt die ausgeführte Appliance und wechselt zu einer neu bereitgestellten oder Sicherungsanwendung.
ms.openlocfilehash: 9b15310956f80a9269c8fb611a0f7c6c06f561e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580329"
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

Mit dem Cmdlet Switch-CcVersion werden die Cloud Connector-Dienste auf dem Vermittlungsserver und dem Edgeserver ausgeglichen. Alle laufenden Anrufe werden abgeschlossen, die Appliance lehnt jedoch alle neuen Anrufe ab. Nach dem Ausgleich trennt das Cmdlet die ausgeführte Appliance von den Unternehmens- und Internetnetzwerken, deaktiviert alle virtuellen Computer, die zur Appliance gehören, und verbindet dann die Sicherungsanwendung mit den Unternehmens- und Internetnetzwerken.
  
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
  

