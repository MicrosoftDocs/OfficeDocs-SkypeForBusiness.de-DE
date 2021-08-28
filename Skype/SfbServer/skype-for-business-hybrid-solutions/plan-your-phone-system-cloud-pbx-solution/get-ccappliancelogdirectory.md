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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Das cmdlet Get-CcApplianceLogDirectory zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Skype for Business Cloud Connector Edition Appliance gespeichert sind.
ms.openlocfilehash: 826599ab785d8b4d74f0792c6091b2a5e78b74e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580359"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Das cmdlet Get-CcApplianceLogDirectory zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Skype for Business Cloud Connector Edition Appliance gespeichert sind.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den aktuellen Ordner, in dem Protokolle für die aktuelle Appliance von Cloud Connector gespeichert sind:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das cmdlet Get-CcApplianceLogDirectory zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Cloud Connector-Appliance gespeichert sind. Der Standardordner lautet "C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs". 
  
Sie können das Verzeichnis mithilfe des Cmdlets Set-CcApplianceDirectory ändern. 
  
Hinweis: Es gibt kein Cmdlet, das nur den Speicherort des Protokollordners ändert, ohne das Appliance-Verzeichnis zu ändern.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Get-CcApplianceLogDirectory akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Dieser Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

