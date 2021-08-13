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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Das Cmdlet Unregister-CcAppliance hebt die Registrierung der aktuellen Skype for Business Cloud Connector Edition Appliance von einem PSTN-Standort in der Onlinemandantenkonfiguration auf.
ms.openlocfilehash: de872082f6a025a736b871a76d41061c888acb1f401739229ba7ad670a0c19ce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344544"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Das Cmdlet Unregister-CcAppliance hebt die Registrierung der aktuellen Skype for Business Cloud Connector Edition Appliance von einem PSTN-Standort in der Onlinemandantenkonfiguration auf.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Registrierung einer aktuellen Appliance aus der Onlinemandantenkonfiguration aufgehoben:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Konfiguration überprüft, um die lokale Registrierung aufzuheben, ohne eine Verbindung mit der Onlinemandantenkonfiguration herzustellen:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird die Registrierung der aktuellen Appliance mit dem Namen "Appliance1" am PSTN-Standort "Site1" aufgehoben:
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Ähnlich wie beim cmdlet Register-CcAppliance gilt SiteName in Kombination mit dem externen FQDN des Edgeservers in der CloudConnector.ini Datei als PSTN-Standortidentität. Ebenso gilt ApplianceName in Kombination mit dem Vermittlungsserver-FQDN in der CloudConnector.ini-Datei als Appliance-Identität.
  
Nachdem die Registrierung der Appliance aufgehoben wurde, starten Sie den Cloud Connector-Verwaltungsdienst neu, und melden Sie sich als NetworkService-Konto an.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Sitename <br/> |Optional  <br/> |System.String  <br/> |Name des PSTN-Standorts, in dem die Appliance registriert ist. Der Standardwert ist der SiteName-Wert in CloudConnector.ini Datei.  <br/> |
|ApplianceName  <br/> |Optional  <br/> |System.String  <br/> |Name der aktuellen Appliance. Der Standardwert ist der Computername des Hostservers.  <br/> |
|Lokal  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überprüfen Sie die Konfiguration auf lokale Registrierung, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Unregister-CcAppliance akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

