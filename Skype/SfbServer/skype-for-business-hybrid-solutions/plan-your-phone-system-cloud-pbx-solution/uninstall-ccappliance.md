---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. '
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824139"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Das Cmdlet „Uninstall-CcAppliance“ deinstalliert die ausgeführte Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver.  
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Cloud Connector-Appliance vom Hostserver entwässert und deinstalliert:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die ausgeführte Cloud Connector-Appliance auf dem Hostserver entladen und zwangsläufig deinstalliert, auch wenn der Abfluss Vorgang fehlgeschlagen ist:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird eine Cloud Connector-Sicherungsversion ohne Bestätigung des Benutzers deinstalliert:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn Sie die aktuelle Version von Cloud Connector deinstallieren, werden die Entwässerungs Dienste zunächst auf dem Vermittlungsserver und dem Edgeserver ausgeführt, damit gleichzeitige Anrufe beendet werden können, bevor die virtuellen Computer deinstalliert werden. Wenn Sie eine Sicherungsversion deinstallieren, wird kein Ausgleich ausgeführt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Version <br/> |  Optional <br/> |System.String  <br/> | Die Version des Cloud Connectors, die vom Hostserver deinstalliert wird. Wenn nichts angegeben ist, wird die zurzeit ausgeführte Version deinstalliert. <br/> |
|Force  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Wenn die zurzeit ausgeführte Version deinstalliert werden soll, wird versucht, Dienste auf dem Vermittlungsserver und dem Edgeserver auszugleichen, bevor die virtuellen Maschinen deinstalliert werden. Wenn Sie den Parameter „Force“ angeben, werden die virtuellen Maschinen auch dann deinstalliert, wenn der Dienstausgleich fehlgeschlagen ist. Dieser Parameter wird nur zum Deinstallieren der zurzeit ausgeführten Version verwendet.  <br/> |
|Confirm  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Bitten Sie die Benutzerbestätigung, die virtuellen Computer zu deinstallieren. Der Standardwert ist „TRUE“.  <br/> |
   
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
  

