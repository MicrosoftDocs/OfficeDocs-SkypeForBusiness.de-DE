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
description: Das cmdlet Set-CcSiteDirectory legt das Verzeichnis fest, in dem Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Konfigurationsdateien.
ms.openlocfilehash: 9642c91e811e62b08f2b0e219b5eaa7b9ac7359fcdb6114c028735851280da59
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286244"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Das cmdlet Set-CcSiteDirectory legt das Verzeichnis fest, in dem Konfigurationsdateien auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Konfigurationsdateien.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Stammverzeichnis der Website auf \\ "SiteShare\CloudConnector" festgelegt:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Um Gatewayaffinität und hohe Verfügbarkeit bereitzustellen, können Cloud Connector-Appliances an Standorten kombiniert werden. Benutzer werden Standorten anstelle von Cloud Connector-Appliances zugewiesen. Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Basis-VHD- und Cloud Connector-Installationsdateien gespeichert sind. Appliances verwenden diesen Ordner während der Bereitstellung. Dieser Ordner sollte für alle anderen Appliances an einem Cloud Connector-Standort freigegeben werden.
  
Der Standardordner lautet "C:\Users \% userprofile%\CloudConnector\SiteRoot". Der Pfad kann mithilfe des Cmdlets Get-CcSiteDirectory angezeigt werden.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Pfad <br/> | Erforderlich <br/> | System.String <br/> |Gibt den Pfad zu dem Ordner an, in dem Cloud Connector-Websitedateien gespeichert werden.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Set-CcSiteDirectory akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

