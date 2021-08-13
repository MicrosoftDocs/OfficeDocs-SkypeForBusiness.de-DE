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
description: Das Cmdlet Uninstall-CcAppliance deinstalliert die ausgeführte Skype for Business Cloud Connector Edition Appliance vom Hostserver.
ms.openlocfilehash: f82459e71ee3c7eea88030a2f265f0076a633a280ee3182920e599402f69a96c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344554"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Das Cmdlet Uninstall-CcAppliance deinstalliert die ausgeführte Skype for Business Cloud Connector Edition Appliance vom Hostserver. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Cloud Connector-Appliance vom Hostserver ausgeglichen und deinstalliert:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel wird die ausgeführte Cloud Connector-Appliance auf dem Hostserver ausgeglichen und deinstalliert, auch wenn der Ausgleichvorgang fehlgeschlagen ist:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Beispiel 3

Im nächsten Beispiel wird eine Cloud Connector-Sicherungsversion ohne Bestätigung des Benutzers deinstalliert:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn Sie die aktuell ausgeführte Version von Cloud Connector deinstallieren, werden die Ausgleichsdienste zuerst auf dem Vermittlungsserver und dem Edgeserver ausgeführt, damit gleichzeitige Anrufe beendet werden können, bevor die virtuellen Computer deinstalliert werden. Wenn Sie eine Sicherungsversion deinstallieren, wird die Entleerung nicht ausgeführt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Version <br/> | Optional <br/> |System.String  <br/> | Die Version von Cloud Connector, die vom Hostserver deinstalliert wird. Wenn nicht angegeben, deinstallieren Sie die aktuell ausgeführte Version. <br/> |
|Force  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Wenn Sie die aktuell ausgeführte Version deinstallieren, versuchen Sie, die Server auf dem Vermittlungsserver und dem Edgeserver auszugleichen, bevor Sie die virtuellen Computer deinstallieren. Wenn Sie den Schalter "Erzwingen" angeben, werden die virtuellen Computer deinstalliert, auch wenn die Ausgleichsdienste fehlschlagen. Dieser Parameter wird nur verwendet, um die aktuell ausgeführte Version zu deinstallieren.  <br/> |
|Bestätigen  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Bitten Sie den Benutzer um Bestätigung, die virtuellen Computer zu deinstallieren. Der Standardwert ist TRUE.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Uninstall-CcAppliance akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

