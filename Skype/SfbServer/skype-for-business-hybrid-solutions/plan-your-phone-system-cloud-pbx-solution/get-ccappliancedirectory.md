---
title: Get-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert. '
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Das Cmdlet „Get-CcApplianceDirectory“ ruft das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.  
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird den aktuellen Ordner, in dem Konfiguration und dem virtuellen Computer Dateien Cloud Connector Komponenten gespeichert sind:
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Get-CcApplianceDirectory veranschaulicht, in dem alle Konfigurations-und virtuellen Computer, Protokolle und externe Zertifikate für die Cloud Connector Appliance gespeichert sind.
  
Jede Appliance Cloud Connector besteht aus vier Komponenten: Vermittlungsserver, zentralen Verwaltungsspeichers, Edge-Server und einem Domänencontroller. Der Standardordner ist C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Sie können den Ordner mit dem Cmdlet „Set-CCApplianceDirectory“ ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CCApplianceDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

