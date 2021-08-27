---
title: Export-CcConfigurationSampleFile
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
ms.localizationpriority: medium
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Das Cmdlet Export-CcConfigurationSampleFile exportiert eine Skype for Business Cloud Connector Edition Beispielkonfigurationsdatei (.ini) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die für Ihre Bereitstellung zu verwendende Datei ändern und umbenennen.
ms.openlocfilehash: 409514761c3bfeccebb671d289201fc67f58d220
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603664"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Das Cmdlet Export-CcConfigurationSampleFile exportiert eine Skype for Business Cloud Connector Edition Beispielkonfigurationsdatei (.ini) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die für Ihre Bereitstellung zu verwendende Datei ändern und umbenennen.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird eine Beispielkonfigurationsdatei vom Microsoft-Standort heruntergeladen und in das Appliance-Verzeichnis der Cloud Connector-Appliance geschrieben:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Für die aktuelle Version von Cloud Connector müssen Sie mehrere Parameter in der .ini-Datei angeben. Beispielsweise Parameter wie die IP-Adressen virtueller Computer für die Cloud Connector-Komponenten, Komponentennamen, Gatewayparameter usw.
  
Wenn dieses Cmdlet auf dem Hostcomputer von Cloud Connector ausgeführt wird, wird ein Beispiel .ini Datei mit Konfigurationsbeispielen von der Microsoft-Website heruntergeladen. Das Cmdlet schreibt die Datei in das Appliance-Verzeichnis der Cloud Connector-Appliance. Das Appliance-Verzeichnis wird mithilfe des Cmdlets Set-CcApplianceDirectory angegeben.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Export-CcConfigurationSampleFile akzeptiert keine weitergeleitete Eingabe. 
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

