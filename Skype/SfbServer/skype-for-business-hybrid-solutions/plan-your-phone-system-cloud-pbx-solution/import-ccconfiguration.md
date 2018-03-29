---
title: Import-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importiert die Skype für Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf die Cloud Connector-Hostserver.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importiert die Skype für Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf die Cloud Connector-Hostserver.
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel kopiert die CloudConnector.ini aus dem Verzeichnis Appliance der Cloud Connector-Instanz zu %SystemDrive%\ProgramData\CloudConnector Verzeichnis:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="Examples"> </a>

Dieses Cmdlet kopiert die CloudConnector.ini aus dem Verzeichnis Appliance der Appliance Cloud-Connector in das Verzeichnis %SystemDrive%\ProgramData\CloudConnector. Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben. Das Cmdlet überschreibt vorhandene Dateien in % SystemDrive%\ProgramData\CloudConnector. Dieser Befehl gilt für Cloud Connector Edition Version 2.0.1 und höher.
  
## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Vorhandene Datei %SystemDrive%\ProgramData\CloudConnector ohne Benachrichtigung zu überschreiben.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das Cmdlet Import-CcConfiguration akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

Keine.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

Export-CcConfiguration
  

