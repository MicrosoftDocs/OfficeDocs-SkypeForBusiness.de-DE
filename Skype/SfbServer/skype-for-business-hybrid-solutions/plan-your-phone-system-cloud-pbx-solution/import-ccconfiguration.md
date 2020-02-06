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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799855"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die CloudConnector. ini aus dem Appliance-Verzeichnis der Cloud Connector-Instanz in das%SystemDrive%\ProgramData\CloudConnector-Verzeichnis kopiert:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="Examples"> </a>

Mit diesem Cmdlet wird die CloudConnector. ini aus dem Appliance-Verzeichnis der Cloud Connector-Appliance in das%SystemDrive%\ProgramData\CloudConnector-Verzeichnis kopiert. Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben. Mit dem Cmdlet werden alle vorhandenen Dateien in%SystemDrive%\ProgramData\CloudConnector. überschrieben. Dieser Befehl gilt für Cloud Connector Edition Version 2.0.1 und höher.
  
## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Vorhandene Datei in%SystemDrive%\ProgramData\CloudConnector ohne Benachrichtigung überschreiben.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das Cmdlet "Import-CcConfiguration" akzeptiert keine Pipeline-Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

Keine.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

Export-CcConfiguration
  

