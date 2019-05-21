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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.
ms.openlocfilehash: 440253bc6b9c4e980a6f7ac4aae0c82ebad05660
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287380"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird eine Beispielkonfigurationsdatei von der Microsoft-Website heruntergeladen und in das Appliance-Verzeichnis der Cloud Connector-Appliance geschrieben:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Für die aktuelle Version von Cloud Connector müssen Sie mehrere Parameter in der INI-Datei angeben. beispielsweise Parameter wie die IP-Adressen virtueller Computer für die Cloud-Connector-Komponenten, Komponentennamen, Gatewayparameter usw.
  
Wenn dieses Cmdlet auf dem Hostcomputer von Cloud Connector ausgeführt wird, wird eine Beispiel-ini-Datei mit Konfigurationsbeispielen von der Microsoft-Website heruntergeladen. Das Cmdlet schreibt die Datei in das Appliance-Verzeichnis der Cloud Connector-Appliance. Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Export-CcConfigurationSampleFile“ akzeptiert keine Pipelineeingaben.  
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

