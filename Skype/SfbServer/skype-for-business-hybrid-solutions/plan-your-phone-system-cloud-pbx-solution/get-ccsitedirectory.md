---
title: Get-CcSiteDirectory
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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Das cmdlet Get-CcSiteDirectory zeigt das aktuelle Verzeichnis an, in dem Konfigurationsdateien auf Standortebene gespeichert sind. Der Ordner enthält die Basis-VHD und Skype for Business Cloud Connector Edition Installationsdateien. Dieser Ordner sollte für alle anderen Appliances eines Cloud Connector-Standorts freigegeben werden.
ms.openlocfilehash: 279afabbb88aab162be8445007772e24d24d06d935130d5f4f27a8755a2fd25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343189"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Das cmdlet Get-CcSiteDirectory zeigt das aktuelle Verzeichnis an, in dem Konfigurationsdateien auf Standortebene gespeichert sind. Der Ordner enthält die Basis-VHD und Skype for Business Cloud Connector Edition Installationsdateien. Dieser Ordner sollte für alle anderen Appliances eines Cloud Connector-Standorts freigegeben werden.
  
Dieses Cmdlet gilt für Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem die Konfigurations- und virtuellen Computerdateien von Cloud Connector-Komponenten gespeichert sind:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Um Gatewayaffinität und hohe Verfügbarkeit bereitzustellen, können Cloud Connector-Appliances an Standorten kombiniert werden. Benutzer werden Standorten anstelle von Cloud Connector-Appliances zugewiesen. Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Basis-VHD- und Cloud Connector-Installationsdateien gespeichert sind. Appliances verwenden diesen Ordner während der Bereitstellung. Der Standardordner lautet "C:\Users \% userprofile%\CloudConnector\SiteRoot". Sie können den Pfad mithilfe des Cmdlets Set-CcSiteDirectory ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Get-CcSiteDirectory akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Dieser Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

