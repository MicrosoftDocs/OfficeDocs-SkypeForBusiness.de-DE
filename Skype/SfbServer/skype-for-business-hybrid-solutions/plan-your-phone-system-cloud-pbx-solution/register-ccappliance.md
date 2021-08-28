---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Das cmdlet Register-CcAppliance registriert Appliance-Informationen an einem PSTN-Standort in einer Onlinemandantenkonfiguration. Eine Appliance muss registriert werden, bevor sie vom Skype for Business Cloud Connector Edition-Verwaltungsdienst bereitgestellt und verwaltet werden kann.
ms.openlocfilehash: 159e74f91ca26cd0f8bdd214c9cd6ac45b5c1196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589959"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Das cmdlet Register-CcAppliance registriert Appliance-Informationen an einem PSTN-Standort in einer Onlinemandantenkonfiguration. Eine Appliance muss registriert werden, bevor sie vom Skype for Business Cloud Connector Edition-Verwaltungsdienst bereitgestellt und verwaltet werden kann.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die aktuellen Appliance-Informationen in einer Onlinemandantenkonfiguration registriert:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Konfiguration lokal auf Registrierung überprüft, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird die aktuelle Appliance mit dem Namen "Appliance1" am PSTN-Standort "Site1" registriert:
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Sie müssen den Namen und das Kennwort des Mandantenadministratorkontos angeben. Verwenden Sie das Konto, das Sie für die Cloud Connector Online-Verwaltung erstellt haben. 
  
Befolgen Sie in Version 1.4.2 und früheren Versionen die Anweisungen zum Bereitstellen des Kennworts für das externe Zertifikat, des Administratorkennworts für den abgesicherten Modus, des Domänenadministratorkennworts und des VM-Administratorkennworts. 
  
Befolgen Sie in Version 2.0 und höher die Anweisungen, um das Kennwort für das externe Zertifikat, das CceService-Kennwort und das CABackupFile-Kennwort bereitzustellen.
  
Starten Sie am Ende der Registrierung den Cloud Connector-Verwaltungsdienst neu, und melden Sie sich bei den Diensten als CceService-Konto an.
  
SiteName in Kombination mit dem externen FQDN des Edgeservers in der CloudConnector.ini Datei wird als PSTN-Standortidentität betrachtet. Wenn weder der SiteName noch der externe FQDN des Edgeservers zum Registrieren eines Standorts verwendet wurde, wird ein neuer Standort für diese Appliance in einer Onlinemandantenkonfiguration erstellt. Wenn eine PSTN-Standortidentität gefunden wird, verwendet ein PSTN-Standort diese Identität, und die Appliance wird an diesem PSTN-Standort registriert. 
  
In der folgenden Situation schlägt das Cmdlet fehl und gibt an, dass Site1 bereits registriert ist: 
  
- "SiteName" ist "Site1", und der externe FQDN des Edgeservers ist edgserver1.contoso.com. 
    
- Ein PSTN-Standort, dessen SiteName "Site1" und der externe Edgeserver-FQDN edgserver.contoso.com ist.
    
- Ein PSTN-Standort, dessen SiteName "NewSite" und der externe Edgeserver-FQDN edgserver1.contoso.com ist, wurde registriert. 
    
ApplianceName in Kombination mit dem Vermittlungsserver-FQDN in CloudConnector.ini Datei wird als Appliance-Identität betrachtet. Wenn weder der ApplianceName noch der Vermittlungsserver-FQDN zum Registrieren einer Appliance verwendet wurde, wird in der Onlinemandantenkonfiguration eine neue Appliance erstellt. Wenn die Appliance bereits registriert ist, schlägt das Cmdlet fehl.
  
In der folgenden Situation schlägt das Cmdlet fehl und gibt an, dass die Appliance bereits registriert ist: 
  
- ApplianceName ist Appliance1, und der Vermittlungsserver-FQDN ist ms1.vdomain.com.
    
- Am aktuellen PSTN-Standort wurde eine Appliance registriert, deren Name "Appliance1" und "Vermittlungsserver-FQDN" ms.vdomain.com ist, oder eine Appliance, deren Name "NewAppliance" und "Vermittlungsserver-FQDN" ms1.vdomain.com ist.
    
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Sitename  <br/> |Optional  <br/> |System.String  <br/> |Name des PSTN-Standorts, für den die Appliance registriert ist. Der Standardwert ist der SiteName-Wert in der CloudConnector.ini Datei.  <br/> |
|ApplianceName  <br/> |Optional  <br/> |System.String  <br/> |Name der aktuellen Appliance. Der Standardwert ist der Computername des Hostservers.  <br/> |
|Lokal  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überprüfen Sie Konfigurationen auf lokale Registrierung, ohne eine Verbindung mit der Onlinemandantenkonfiguration herzustellen.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Register-CcAppliance akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

