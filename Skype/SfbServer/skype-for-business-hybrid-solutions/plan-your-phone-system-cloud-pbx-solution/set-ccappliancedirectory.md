---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Das Cmdlet Set-CcApplianceDirectory legt das Arbeitsverzeichnis auf dem Skype for Business Cloud Connector Edition Hostserver fest. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.
ms.openlocfilehash: 8ca6b8b8e175058e5f19c86a9dd1c6e0cf8a43ab6ef7a439eee4e09b5430f6a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306596"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Das Cmdlet Set-CcApplianceDirectory legt das Arbeitsverzeichnis auf dem Skype for Business Cloud Connector Edition Hostserver fest. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Arbeitsverzeichnis auf dem Hostserver auf "c:\cloudconnector\applianceroot" festgelegt:
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Pfad <br/> | Erforderlich <br/> |System.String  <br/> | Gibt den Pfad an, in dem alle Bereitstellungsdateien gespeichert werden. <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Set-CcApplianceDirectory akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

