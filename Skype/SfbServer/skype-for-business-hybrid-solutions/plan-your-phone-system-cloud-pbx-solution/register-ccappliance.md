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
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Das Cmdlet „Register-CcAppliance“ registriert Appliance-Informationen für einen PSTN-Standort in einer Onlinemandantenkonfiguration. Sie müssen eine Appliance registrieren, bevor diese bereitgestellt und mit dem Skype for Business Cloud Connector Edition-Verwaltungsdienst verwaltet werden kann.
ms.openlocfilehash: 93f1fe59a199214615c5ecdf8445f6c363ce6bbe
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003305"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Das Cmdlet „Register-CcAppliance“ registriert Appliance-Informationen für einen PSTN-Standort in einer Onlinemandantenkonfiguration. Sie müssen eine Appliance registrieren, bevor diese bereitgestellt und mit dem Skype for Business Cloud Connector Edition-Verwaltungsdienst verwaltet werden kann.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die aktuellen Appliance-Informationen in einer Onlinemandantenkonfiguration registriert:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die Konfiguration lokal auf eine Registrierung überprüft, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird die aktuelle Appliance unter dem Namen „Appliance1“ am PSTN-Standort „Site1“ registriert:
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Sie müssen den Namen und das Kennwort für das Administratorkonto des Mandanten angeben. Verwenden Sie das Konto, das Sie für die Onlineverwaltung von Cloud Connector erstellt haben. 
  
Befolgen Sie in Version 1.4.2 und älteren Versionen die Anweisungen zum Bereitstellen des Kennworts für externes Zertifikat, des Administratorkennworts für den sicheren Modus, des Domänenadministrator Kennworts und des VM-Administratorkennworts. 
  
Befolgen Sie in Version 2,0 und höher die Anweisungen zum Bereitstellen des externen Zertifikats Kennworts, des CceService-Kennworts und des CABackupFile-Kennworts.
  
Starten Sie nach Abschluss der Registrierung den Cloud Connector-Verwaltungsdienst neu, und melden Sie sich bei den Diensten als CceService-Konto an.
  
„SiteName“ in Kombination mit dem externen Edgeserver-FQDN in der Datei „CloudConnector.ini“ gilt als PSTN-Standortidentität. Wenn weder „SiteName“ noch der externe Edgeserver-FQDN zum Registrieren eines Standorts verwendet wurde, wird in einer Onlinemandantenkonfiguration ein neuer Standort für diese Appliance erstellt. Wenn eine PSTN-Standortidentität gefunden wird, verwendet ein PSTN-Standort diese Identität, und die Appliance wird an diesem PSTN-Standort registriert.  
  
In der folgenden Situation schlägt das Cmdlet fehl und weist darauf hin, dass „Site1“ bereits registriert ist:  
  
- 	„SiteName“ entspricht „Site1“, und der externe Edgeserver-FQDN lautet „edgserver1.contoso.com“.  
    
- Der „SiteName“ eines PSTN-Standorts entspricht „Site1“, und der externe Edgeserver-FQDN lautet „edgserver.contoso.com“.
    
- Ein PSTN-Standort mit dem „SiteName“ „NewSite“ und dem externen Edgeserver-FQDN „edgserver1.contoso.com“ wurde registriert.  
    
„ApplianceName“ in Kombination mit dem Vermittlungsserver-FQDN in der Datei „CloudConnector.ini“ gilt als Appliance-Identität. Wenn weder „ApplianceName“ noch der Vermittlungsserver-FQDN zum Registrieren einer Appliance verwendet wurde, wird in der Onlinemandantenkonfiguration eine neue Appliance erstellt. Wenn die Appliance bereits registriert ist, schlägt das Cmdlet fehl.
  
In der folgenden Situation schlägt das Cmdlet fehl und weist darauf hin, dass die Appliance bereits registriert ist:  
  
- „ApplianceName“ entspricht „Appliance1“, und der Vermittlungsserver-FQDN lautet „ms1.vdomain.com“.
    
- Am aktuellen PSTN-Standort wurde eine Appliance mit dem Namen „Appliance1“ und dem Vermittlungsserver-FQDN „ms.vdomain.com“ oder eine Appliance mit dem Namen „NewAppliance“ und dem Vermittlungsserver-FQDN „ms1.vdomain.com“ registriert.
    
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Optional   <br/> |System.String  <br/> |Name des PSTN-Standorts, für den die Appliance registriert ist. Der Standardwert ist der Wert „SiteName“ in der Datei „CloudConnector.ini“.   <br/> |
|ApplianceName  <br/> |Optional   <br/> |System.String  <br/> |Name der aktuellen Appliance. Der Standardwert ist der Computername des Hostservers.  <br/> |
|Local  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überprüft Konfigurationen lokal auf eine Registrierung, ohne eine Verbindung mit einer Onlinemandantenkonfiguration herzustellen.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Register-CcAppliance“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

