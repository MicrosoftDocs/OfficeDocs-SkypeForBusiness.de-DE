---
title: Set-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgende Beispiel wird das Stammverzeichnis der Website auf \\SiteShare\CloudConnector:
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Um Gateway Affinität und hohe Verfügbarkeit zu ermöglichen, können in Websites Cloud Connector Appliances kombiniert werden. Benutzer werden anstelle von Cloud-Connector Appliances zugewiesen. Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind. Verwenden Sie diesen Ordner Appliances während der Bereitstellung. In diesem Ordner sollten für alle anderen Appliances in einer Cloud-Connector-Website freigegeben werden.
  
Der Standardordner ist C:\Users\%userprofile%\CloudConnector\SiteRoot. Der Pfad kann mit dem Cmdlet „Get-CcSiteDirectory“ angezeigt werden.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  Path <br/> | Erforderlich <br/> | System.String <br/> |Gibt den Pfad zu dem Ordner, in dem Cloud-Connector-Website-Dateien gespeichert werden.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Set-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

