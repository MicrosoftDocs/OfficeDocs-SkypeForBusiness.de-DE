---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Das cmdlet Exit-CcUpdate beendet den Updatewartungsmodus auf dem Skype for Business Cloud Connector Edition Hostserver.
ms.openlocfilehash: 11499950a3332de31fe045ea23c1aa8f567da072
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625017"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Das cmdlet Exit-CcUpdate beendet den Updatewartungsmodus auf dem Skype for Business Cloud Connector Edition Hostserver. 
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Mit dem folgenden Befehl wird die Appliance, auf der sie ausgeführt wird, wieder in den Produktionsmodus versetzt: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn Sie Appliances in den Wartungsmodus versetzt haben, indem Sie das cmdlet Enter-CcUpdate angeben, werden diese mit dem cmdlet Exit-CcUpdate wieder in den Produktionsmodus versetzt. 
  
Weitere Informationen zum Versetzen von Appliances in den Wartungsmodus finden Sie unter Enter-CcUpdate.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Exit-CcUpdate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

