---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Das Cmdlet „Unregister-CcAppliance“ hebt die Registrierung der aktuellen Skype for Business Cloud Connector Edition-Appliance an einem PSTN-Standort in der Onlinemandantenkonfiguration auf.
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286873"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Das Cmdlet „Unregister-CcAppliance“ hebt die Registrierung der aktuellen Skype for Business Cloud Connector Edition-Appliance an einem PSTN-Standort in der Onlinemandantenkonfiguration auf.
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Registrierung einer aktuellen Appliance in der Onlinemandantenkonfiguration aufgehoben:
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Konfiguration lokal auf die Aufhebung der Registrierung überprüft, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen:
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird die Registrierung der aktuellen Appliance mit dem Namen „Appliance1“ am PSTN-Standort „Site1“ aufgehoben:
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Ähnlich wie beim Cmdlet „Register-CcAppliance“ gilt „SiteName“ in Kombination mit dem externen Edgeserver-FQDN in der Datei „CloudConnector.ini“ als PSTN-Standortidentität. Entsprechend gilt „ApplianceName“ in Kombination mit dem Vermittlungsserver-FQDN in der Datei „CloudConnector.ini“ als Appliance-Identität.
  
Nachdem die Registrierung der Appliance aufgehoben wurde, starten Sie den Cloud Connector-Verwaltungsdienst neu, und melden Sie sich als Network Service-Konto an.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Optional   <br/> |System.String  <br/> |Name des PSTN-Standorts, an dem die Appliance registriert ist. Der Standardwert ist der Wert „SiteName“ in der Datei „CloudConnector.ini“.  <br/> |
|ApplianceName  <br/> |Optional   <br/> |System.String  <br/> |Name der aktuellen Appliance. Der Standardwert ist der Computername des Hostservers.  <br/> |
|Local  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überprüft die Konfiguration lokal auf eine Registrierung, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Unregister-CcAppliance“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

