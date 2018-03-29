---
title: Reset-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Das Cmdlet „Reset-CcCACertificate“ installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.
ms.openlocfilehash: dc86c39e844accc789ba7a3503aa6261d40e5cb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Das Cmdlet „Reset-CcCACertificate“ installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen:
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn das Zertifikat der Stammzertifizierungsstelle kompromittiert oder nicht mehr sicher ist, müssen Sie das Zertifikat der Stammzertifizierungsstelle und alle von der Stammzertifizierungsstelle ausgestellten Zertifikate aktualisieren. Das Cmdlet „Reset-CcCACertificate“ widerruft alle Zertifikate, deinstalliert die Zertifizierungsstelle, installiert diese neu, und bereinigt dann alle Zertifikate, die sich auf den alten Zertifizierungsstellendienst beziehen. 
  
Weitere Informationen finden Sie unter "Certificate Zertifikaten oder interne Zertifikate CMS, Vermittlungsserver und Edge-Server ausgestellt werden in der Nähe Ablauf oder sind beschädigt" bei der Problembehandlung Ihrer bereitstellungs Cloud-Connector.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Reset-CcCACertificate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Erneuern CcCACertificate](renew-cccacertificate.md) Nur Version 1.4.2
  
[Erneuern CcServerCertificate](renew-ccservercertificate.md) Nur Version 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 und höher
  
[Erneuern CcServerCertificate](renew-ccservercertificate.md) Version 2.0 und höher
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

