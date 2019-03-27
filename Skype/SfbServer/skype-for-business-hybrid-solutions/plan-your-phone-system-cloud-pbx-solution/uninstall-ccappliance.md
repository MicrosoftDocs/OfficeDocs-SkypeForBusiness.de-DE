---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. '
ms.openlocfilehash: 7b2def71eee17c81b6f178a18d4c248557a0f022
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885648"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel verbraucht und die Cloud Connector Appliance vom Hostserver deinstalliert:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächste Beispiel verbraucht und das Entfernen die ausgeführte Appliance Cloud Connector auf dem Hostserver deinstalliert, auch wenn der ausgleichen-Prozess konnte nicht:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Beispiel 3

Im nächste Beispiel werden eine Cloud-Connector Sicherungsversion ohne Bestätigung des Benutzers deinstalliert:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn Sie die aktuelle ausgeführte Version von Cloud-Connector deinstallieren, werden ausgleichen Services zuerst auf dem Vermittlungsserver und Edge-Server gleichzeitige Anrufe beendet ist, bevor Sie die virtuellen Computer deinstallieren können ausgeführt. Wenn Sie eine Sicherungsversion deinstallieren, wird kein Ausgleich ausgeführt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Version <br/> |  Optional <br/> |System.String  <br/> | Die Version der Cloud-Verbindung, die vom Hostserver deinstalliert werden. Wenn nichts angegeben ist, wird die zurzeit ausgeführte Version deinstalliert. <br/> |
|Force  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Wenn die zurzeit ausgeführte Version deinstalliert werden soll, wird versucht, Dienste auf dem Vermittlungsserver und dem Edgeserver auszugleichen, bevor die virtuellen Maschinen deinstalliert werden. Wenn Sie den Parameter „Force“ angeben, werden die virtuellen Maschinen auch dann deinstalliert, wenn der Dienstausgleich fehlgeschlagen ist. Dieser Parameter wird nur zum Deinstallieren der zurzeit ausgeführten Version verwendet.  <br/> |
|Confirm  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Bitten Sie Bestätigung So deinstallieren Sie die virtuellen Computer des Benutzers. Der Standardwert ist „TRUE“.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Uninstall-CcAppliance“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

