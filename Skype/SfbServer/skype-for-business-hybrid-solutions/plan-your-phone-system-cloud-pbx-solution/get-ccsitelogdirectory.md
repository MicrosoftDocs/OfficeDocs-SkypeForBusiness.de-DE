---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 'Das Cmdlet „Get-CcSiteLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden. '
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799885"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Das Cmdlet „Get-CcSiteLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Skype for Business Cloud Connector Edition gespeichert werden.  
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem die Protokolldateien für die Cloud Connector-Website gespeichert sind:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\SiteRoot\Logs. Sie können den Ordner ändern, indem Sie das Cmdlet „Set-CcSiteDirectory“ ausführen. Es gibt kein separates Cmdlet, das nur den Speicherort des Protokollordners, aber nicht das Standortverzeichnis ändert.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CcSiteLogDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

