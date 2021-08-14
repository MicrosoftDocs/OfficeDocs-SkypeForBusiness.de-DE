---
title: Publish-CcAppliance
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
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Das Cmdlet Publish-CcAppliance erhält Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration und veröffentlicht sie in der Skype for Business Cloud Connector Edition Appliance auf dem Hostserver.
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326181"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Das Cmdlet Publish-CcAppliance erhält Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration und veröffentlicht sie in der Skype for Business Cloud Connector Edition Appliance auf dem Hostserver. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration abgerufen und in der Cloud Connector-Appliance auf dem Hostserver veröffentlicht:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Informationen zur hohen Verfügbarkeit enthalten die Vermittlungsserver-FQDNs und IP-Adressen des PSTN-Standorts. Neue DNS A-Einträge werden dem AD-Server für DIE IP-Adressen des Vermittlungsservers hinzugefügt. Neue Topologieelemente werden auf die zentrale Verwaltungs-Store für die Vermittlungsserver-FQDNs und IP-Adressen aktualisiert. 
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Publish-CcAppliance akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

