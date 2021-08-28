---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.
ms.openlocfilehash: efcc73fd5883c61753688923d44c01e10fc74ea8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623397"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die CloudConnector.ini aus dem Appliance-Verzeichnis der Cloud Connector-Instanz in das Verzeichnis %SystemDrive%\ProgramData\CloudConnector kopiert:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="Examples"> </a>

Dieses Cmdlet kopiert die CloudConnector.ini aus dem Appliance-Verzeichnis der Cloud Connector-Appliance in das Verzeichnis %SystemDrive%\ProgramData\CloudConnector. Das Appliance-Verzeichnis wird mithilfe des Cmdlets Set-CcApplianceDirectory angegeben. Das Cmdlet überschreibt alle vorhandenen Dateien in %SystemDrive%\ProgramData\CloudConnector. Dieser Befehl gilt für Cloud Connector Edition, Version 2.0.1 und höher.
  
## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überschreiben Sie die vorhandene Datei in %SystemDrive%\ProgramData\CloudConnector ohne Benachrichtigung.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das cmdlet Import-CcConfiguration akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

None.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

Export-CcConfiguration
  

