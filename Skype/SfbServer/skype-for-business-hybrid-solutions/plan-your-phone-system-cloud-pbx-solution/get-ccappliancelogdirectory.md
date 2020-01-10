---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003395"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Das Cmdlet „Get-CcApplianceLogDirectory“ zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Skype for Business Cloud Connector Edition-Appliance gespeichert werden.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem Protokolle für die aktuelle Appliance des Cloud Connectors gespeichert sind:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet "Get-CcApplianceLogDirectory" zeigt das aktuelle Verzeichnis an, in dem die Protokolle für eine Cloud Connector-Appliance gespeichert sind. Der Standardordner lautet C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot\Logs. 
  
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
  

