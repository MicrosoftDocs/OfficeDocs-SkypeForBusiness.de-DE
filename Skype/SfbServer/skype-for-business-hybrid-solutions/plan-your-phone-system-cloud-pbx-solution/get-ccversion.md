---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Gibt die Version der Cloud Connector-Appliance zurück. Get-CCVersion können nur auf dem Hostcomputer von Cloud Connector verwendet werden.
ms.openlocfilehash: a94c15516ff07f908ee8094f7f76347da8c32156
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605994"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Gibt die Version der Cloud Connector-Appliance zurück. Get-CCVersion können nur auf dem Hostcomputer von Cloud Connector verwendet werden.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

Gibt die Version der Cloud Connector-Appliance basierend auf installierten PowerShell-Skripts, Dateien im Appliance-Verzeichnis und den auf dem Hostserver bereitgestellten virtuellen Computern zurück.
  
## <a name="parameters"></a>Parameter

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Optional  <br/> |System.String  <br/> |Typ der Version. Der Wert des Parameters kann RunningScripts, RunningBits, BackupBits oder All sein. Der Standardwert ist RunningScripts.  <br/> |
   
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt die Cloud Connector-Version des aktuell ausgeführten Skripts in der geöffneten PowerShell-Konsole:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Beispiel 2

Das folgende Beispiel zeigt die Cloud Connector-Version der derzeit ausgeführten Binärdateien, die auf den virtuellen Computern bereitgestellt werden. Sie können die Version in den Namen der ausgeführten virtuellen Computer im Hyper-v-Manager anzeigen:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das cmdlet Get-CcVersion akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

None.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

None.
  

