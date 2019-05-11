---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Das Enter-CcUpdate-Cmdlet wird die Skype für Business Cloud Connector Edition Hostserver für des Aktualisierungsvorgangs indem Sie ihn im Wartungsmodus ablegen vorbereitet. Die Appliance Isdrained – d. h., alle aktuellen Anrufe abgeschlossen, aber neue Aufrufe zurückgewiesen.
ms.openlocfilehash: 42c8f7fa668fa94040276e7749e93b5832d511cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929431"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate
 
Das Enter-CcUpdate-Cmdlet wird die Skype für Business Cloud Connector Edition Hostserver für des Aktualisierungsvorgangs indem Sie ihn im Wartungsmodus ablegen vorbereitet. Die Einheit ist "ein Ausgleich vorgenommen" – d. h., alle aktuellen Anrufe abgeschlossen, aber neue Aufrufe zurückgewiesen. 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Appliance auf den Updateprozess vorbereitet, indem sie in den Wartungsmodus versetzt wird:
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Enter-CcUpdate-Cmdlet wird sofort beenden Sie alle Dienste beenden alle laufenden Anrufe und die Anwendung lehnt keine neuen Anrufe, die auf andere Appliances Produktion übertragen werden. Sie müssen sicherstellen, dass die verbleibenden Produktion-Einheiten verfügen über genügend Kapazität, um Anrufe von der Anwendung, die Sie zum Aktualisieren vorbereiten.
  
Der Wartungsmodus ist hilfreich, wenn zum Beispiel für Ihre Appliance automatische Updates aktiviert sind und Microsoft einen wichtigen Hotfix veröffentlicht. Außerdem ist der Wartungsmodus hilfreich, wenn Sie zwar beschließen, automatische Updates zu deaktivieren, aber regelmäßig manuelle Updates ausführen.
  
Nach der Installation der Updates, kann die Appliance wieder zu Produktionsmodus geschaltet werden durch Ausführen des Cmdlets Exit-CcUpdate.
  
> [!NOTE]
> Wenn Sie eine Cloud-Connector Appliance manuell aktualisieren möchten, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung von Microsoft der nächsten Version zu aktualisieren. Microsoft unterstützt die zuvor veröffentlichte Version von Cloud-Connector für 60 Tage nach der Veröffentlichung der neuen version 
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Enter-CCUpdate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine  
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

