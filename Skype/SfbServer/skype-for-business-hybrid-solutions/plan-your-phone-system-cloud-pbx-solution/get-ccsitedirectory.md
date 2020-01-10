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
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Das Cmdlet „Get-CcSiteDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Installationsdateien für die Basis-VHD und für Skype for Business Cloud Connector Edition. Dieser Ordner sollte für alle anderen Appliances einer Cloud Connector-Website freigegeben werden.
ms.openlocfilehash: 095776a680fbbcc8c43a8f99700b357175010b5a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003365"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Das Cmdlet „Get-CcSiteDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Installationsdateien für die Basis-VHD und für Skype for Business Cloud Connector Edition. Dieser Ordner sollte für alle anderen Appliances einer Cloud Connector-Website freigegeben werden.
  
Dieses Cmdlet gilt für Cloud Connector Edition 1.4.1 und 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem die Konfigurations-und Virtual Machines-Dateien von Cloud Connector-Komponenten gespeichert sind:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Zur Bereitstellung von Gateway-Affinität und höchst Verfügbarkeit können Cloud Connector-Appliances in Websites kombiniert werden. Benutzer werden Websites anstelle von Cloud Connector-Appliances zugewiesen. Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind. Appliances verwenden diesen Ordner während der Bereitstellung. Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\SiteRoot. Sie können den Pfad mit dem Cmdlet „Set-CcSiteDirectory“ ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Dieser Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

