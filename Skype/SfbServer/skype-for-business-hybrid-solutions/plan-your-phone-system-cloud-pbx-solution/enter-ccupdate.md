---
title: Geben Sie CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Das Cmdlet „Enter-CcUpdate“ bereitet den Hostserver von Skype for Business Cloud Connector Edition auf den Updateprozess vor, indem es ihn in den Wartungsmodus versetzt. Die Appliance Isdrained – d. h., alle aktuellen Anrufe abgeschlossen, aber neue Aufrufe zurückgewiesen.
ms.openlocfilehash: f9b789bbd76bd3405617dc170af0695f9cbe94ed
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450511"
---
# <a name="enter-ccupdate"></a>Geben Sie CcUpdate
 
Das Cmdlet „Enter-CcUpdate“ bereitet den Hostserver von Skype for Business Cloud Connector Edition auf den Updateprozess vor, indem es ihn in den Wartungsmodus versetzt. Die Einheit ist "ein Ausgleich vorgenommen" – d. h., alle aktuellen Anrufe abgeschlossen, aber neue Aufrufe zurückgewiesen. 
  
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
  
Nach der Installation der Updates können Sie die Appliance wieder in den Produktionsmodus versetzen, indem Sie das Cmdlet „Exit-CcUpdate“ ausführen.
  
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
  

