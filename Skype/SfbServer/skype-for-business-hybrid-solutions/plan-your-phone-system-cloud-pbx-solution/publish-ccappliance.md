---
title: Veröffentlichen von CcAppliance
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
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a>Veröffentlichen von CcAppliance
 
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
  
[Deinstallieren von CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Aufheben der Registrierung CcAppliance](unregister-ccappliance.md)
  

