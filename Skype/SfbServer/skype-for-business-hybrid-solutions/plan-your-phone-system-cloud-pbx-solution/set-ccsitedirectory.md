---
title: Set-CcSiteDirectory
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
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824189"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Das Cmdlet „Set-CcSiteDirectory“ legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Websitestamm Verzeichnis auf \\SiteShare\CloudConnector festgelegt:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Zur Bereitstellung von Gateway-Affinität und höchst Verfügbarkeit können Cloud Connector-Appliances in Websites kombiniert werden. Benutzer werden Websites anstelle von Cloud Connector-Appliances zugewiesen. Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind. Appliances verwenden diesen Ordner während der Bereitstellung. Dieser Ordner sollte für alle anderen Appliances auf einer Cloud Connector-Website freigegeben werden.
  
Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\SiteRoot. Der Pfad kann mit dem Cmdlet „Get-CcSiteDirectory“ angezeigt werden.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  Path <br/> | Erforderlich <br/> | System.String <br/> |Gibt den Pfad zu dem Ordner an, in dem Cloud Connector-Website Dateien gespeichert werden.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Set-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

