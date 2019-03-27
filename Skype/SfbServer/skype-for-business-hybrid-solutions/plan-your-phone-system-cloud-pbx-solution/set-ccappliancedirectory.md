---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Das Cmdlet „Set-CcApplianceDirectory“ legt das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888182"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Das Cmdlet „Set-CcApplianceDirectory“ legt das Arbeitsverzeichnis auf dem Hostserver von Skype for Business Cloud Connector Edition fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Arbeitsverzeichnis auf dem Hostserver auf „c:\cloudconnector\applianceroot“ festgelegt:
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|  Path <br/> | Erforderlich <br/> |System.String  <br/> |  Gibt den Pfad an, in dem alle Bereitstellungsdateien gespeichert werden. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Set-CcApplianceDirectory“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

