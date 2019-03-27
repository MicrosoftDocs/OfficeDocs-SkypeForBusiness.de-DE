---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Gibt die Version der Cloud Connector Appliance zurück. Get-CCVersion kann nur auf dem Hostcomputer der Cloud-Verbindung verwendet werden.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881333"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Gibt die Version der Cloud Connector Appliance zurück. Get-CCVersion kann nur auf dem Hostcomputer der Cloud-Verbindung verwendet werden.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

Gibt die Version der Cloud Connector Appliance basierend auf PowerShell-Skripts installiert, Dateien im Verzeichnis Appliance und die virtuellen Computer auf Hostserver bereitgestellt.
  
## <a name="parameters"></a>Parameter

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Optional  <br/> |System.String  <br/> |Typ der Version. Wert des Parameters kann RunningScripts, RunningBits, BackupBits oder alle entsprechen. Standardwert ist RunningScripts.  <br/> |
   
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgende Beispiel zeigt die Cloud Connector Version des derzeit ausgeführten Skripts in der open-PowerShell-Konsole:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Beispiel 2

Das folgende Beispiel zeigt die Version Cloud Connector, der derzeit ausgeführten Binärdateien auf den virtuellen Computern bereitgestellt. Sie können die Version in den Namen der ausgeführten virtuellen Computer im Hyper-V-Manager finden Sie unter:
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das Cmdlet Get-CcVersion akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

Keine.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

Keine.
  

