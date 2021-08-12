---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Das Cmdlet Enter-CcUpdate bereitet den Skype for Business Cloud Connector Edition Hostserver für den Updateprozess vor, indem es in den Wartungsmodus versetzt wird. Die Appliance beendet sofort alle Dienste, beendet alle laufenden Anrufe und lehnt alle neuen Anrufe ab.
ms.openlocfilehash: 75be5933e31f3966ab36f9957b78cd89c21a4a31df23b5761000a6e96cd9806e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303648"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

Das Cmdlet Enter-CcUpdate bereitet den Skype for Business Cloud Connector Edition Hostserver für den Updateprozess vor, indem es in den Wartungsmodus versetzt wird. Die Appliance beendet sofort alle Dienste, beendet alle laufenden Anrufe und lehnt alle neuen Anrufe ab.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Appliance für den Updateprozess vorbereitet, indem der Wartungsmodus aktiviert wird:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das cmdlet Enter-CcUpdate beendet sofort alle Dienste, die laufende Anrufe beenden, und die Appliance lehnt alle neuen Anrufe ab, die an andere Produktions-Appliances übertragen werden. Sie müssen sicherstellen, dass die verbleibenden Produktions-Appliances über genügend Kapazität verfügen, um die Anrufe der Appliance zu verarbeiten, die Sie auf die Aktualisierung vorbereiten.
  
Der Wartungsmodus ist nützlich, wenn in Ihrer Appliance beispielsweise automatische Updates aktiviert sind und Microsoft einen kritischen Hotfix veröffentlicht. Der Wartungsmodus ist auch hilfreich, wenn Sie sich entscheiden, automatische Updates zu deaktivieren, aber manuelle Updates konsistent durchführen.
  
Nach der Installation der Updates kann die Appliance wieder in den Produktionsmodus zurückgeführt werden, indem das Cmdlet Exit-CcUpdate ausgeführt wird.
  
> [!NOTE]
> Wenn Sie eine Cloud Connector-Appliance manuell aktualisieren möchten, müssen Sie sie innerhalb von 60 Tagen nach der Veröffentlichung der nächsten Version durch Microsoft aktualisieren. Microsoft unterstützt die zuvor veröffentlichte Version von Cloud Connector 60 Tage nach der Veröffentlichung der neuen Version. 
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Enter-CCUpdate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

