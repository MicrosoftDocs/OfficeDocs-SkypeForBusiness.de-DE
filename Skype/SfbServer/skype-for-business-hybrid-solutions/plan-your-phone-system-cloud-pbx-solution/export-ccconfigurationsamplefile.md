---
title: Export-CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Das Cmdlet „Export-CcConfigurationSampleFile“ exportiert eine Beispielkonfigurationsdatei (INI-Datei) für Skype for Business Cloud Connector Edition in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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

Im folgenden Beispiel wird lädt Beispielkonfigurationsdatei aus der Microsoft-Website und schreibt sie in das Verzeichnis Appliance der Cloud Connector Appliance:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Die aktuelle Version von Cloud-Connector müssen Sie mehrere Parameter in der INI-Datei bereitstellen; beispielsweise Parameter wie die IP-Adressen von virtuellen Computern für Komponenten von Cloud-Connector, Komponentennamen, Gateway-Parameter und So weiter.
  
Dieses Cmdlet, wenn auf dem Hostcomputer von Cloud-Connector ausführen lädt eine INI-Beispieldatei mit Beispielen für die Konfiguration aus der Microsoft-Website. Das Cmdlet schreibt die Datei in das Verzeichnis Appliance der Appliance Cloud-Connector. Das Appliance-Verzeichnis wird mit dem Cmdlet „Set-CcApplianceDirectory cmdlet“ angegeben.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Export-CcConfigurationSampleFile“ akzeptiert keine Pipelineeingaben.  
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

