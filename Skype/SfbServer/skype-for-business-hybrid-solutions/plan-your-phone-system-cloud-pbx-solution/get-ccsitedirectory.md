---
title: Get-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Das Cmdlet „Get-CcSiteDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Installationsdateien für die Basis-VHD und für Skype for Business Cloud Connector Edition. In diesem Ordner sollten für alle anderen Einheiten einer Cloud-Connector-Website freigegeben werden.
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Das Cmdlet „Get-CcSiteDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Installationsdateien für die Basis-VHD und für Skype for Business Cloud Connector Edition. In diesem Ordner sollten für alle anderen Einheiten einer Cloud-Connector-Website freigegeben werden.
  
Dieses Cmdlet gilt für Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird den aktuellen Ordner, in dem die Konfiguration und virtuelle Computer Dateien Cloud Connector Komponenten gespeichert sind:
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Um Gateway Affinität und hohe Verfügbarkeit zu ermöglichen, können in Websites Cloud Connector Appliances kombiniert werden. Benutzer werden anstelle von Cloud-Connector Appliances zugewiesen. Jeder Standort verfügt über einen freigegebenen Ordner, in dem die Installationsdateien für die Basis-VHD und für Cloud Connector gespeichert sind. Verwenden Sie diesen Ordner Appliances während der Bereitstellung. Der Standardordner ist C:\Users\%userprofile%\CloudConnector\SiteRoot. Sie können den Pfad mit dem Cmdlet „Set-CcSiteDirectory“ ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CcSiteDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Dieser Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

