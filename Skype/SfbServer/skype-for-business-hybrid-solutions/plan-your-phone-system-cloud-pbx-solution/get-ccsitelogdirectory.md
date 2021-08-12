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
description: Das cmdlet Get-CcSiteLogDirectory zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Skype for Business Cloud Connector Edition gespeichert sind.
ms.openlocfilehash: 7c15d0b715384fd18522122571da69f58a83ed337d46420e83f7ac35cfd0c018
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349517"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Das cmdlet Get-CcSiteLogDirectory zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Skype for Business Cloud Connector Edition gespeichert sind. 
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem die Protokolldateien für den Cloud Connector-Standort gespeichert sind:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Der Standardordner lautet "C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs". Sie können den Ordner ändern, indem Sie das Cmdlet Set-CcSiteDirectory ausführen. Es gibt kein separates Cmdlet, das nur den Speicherort des Protokollordners ändert, ohne das Websiteverzeichnis zu ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Get-CcSiteLogDirectory akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

