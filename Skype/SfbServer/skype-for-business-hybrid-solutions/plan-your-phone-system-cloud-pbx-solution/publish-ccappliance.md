---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'Das Cmdlet „Publish-CcAppliance“ ruft Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration ab und veröffentlicht sie in der Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver. '
ms.openlocfilehash: 119b5e816555eedf221d9db06be15e6a778936d4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879805"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Das Cmdlet „Publish-CcAppliance“ ruft Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration ab und veröffentlicht sie in der Skype for Business Cloud Connector Edition-Appliance auf dem Hostserver.  
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird hohe Verfügbarkeit aus der online-Mandantenkonfiguration abgerufen und an die Cloud Connector Appliance auf dem Hostserver veröffentlicht wird:
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Die Informationen zur hohen Verfügbarkeit enthalten die Vermittlungsserver-FQDNs und die IP-Adressen des PSTN-Standorts. Neue DNS-A-Einträge werden zum AD-Server für IP-Adressen für Vermittlungsserver hinzugefügt. Neue Topologieelemente werden im zentralen Verwaltungsspeicher für die Vermittlungsserver-FQDNs und IP-Adressen aktualisiert.  
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Publish-CcAppliance“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

