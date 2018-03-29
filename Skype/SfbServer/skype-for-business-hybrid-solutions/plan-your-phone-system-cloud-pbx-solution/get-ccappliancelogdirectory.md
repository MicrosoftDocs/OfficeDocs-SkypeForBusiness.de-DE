---
title: Get-CcApplianceLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem die Protokolle für die aktuelle Anwendung von Cloud-Connector gespeichert werden:
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Get-CcApplianceLogDirectory zeigt das aktuelle Verzeichnis, in dem die Protokolle für eine Cloud-Connector Appliance gespeichert werden. Der Standardordner ist C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Sie können das Verzeichnis mit dem Cmdlet „Set-CcApplianceDirectory“ ändern.  
  
Hinweis: Es gibt kein Cmdlet, das nur den Speicherort des Protokollordners, aber nicht das Appliance-Verzeichnis ändert.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Get-CcApplianceLogDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Dieser Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

