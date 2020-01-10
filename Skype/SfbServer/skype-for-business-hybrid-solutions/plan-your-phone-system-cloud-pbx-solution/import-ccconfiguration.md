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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003335"
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
  

