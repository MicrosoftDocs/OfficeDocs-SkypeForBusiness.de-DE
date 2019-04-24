---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist. Mit diesem Befehl wurde Update-CcCACertificate in der Cloud Connector 2.0 und spätere Versionen geändert.
ms.openlocfilehash: 616abb35d577b816368854396a201b9f07b40d12
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250892"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist. Mit diesem Befehl wurde Update-CcCACertificate in der Cloud Connector 2.0 und spätere Versionen geändert.
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert:  
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.
  
Wenn das Stammzertifikat in Kürze abläuft oder bereits abgelaufen ist, führen Sie das Cmdlet „Renew-CcCACertificate“ aus, um das Zertifikat zu erneuern. Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.
  
Wenn sich an einem PSTN-Standort mehrere Appliances befinden, führen Sie das Cmdlet „Renew-CcCACertificate“ in allen Appliances des gleichen PSTN-Standorts aus.
  
Letzter Schritt: Führen Sie das Cmdlet „Export-CcRootCertificate“ aus, um das Stammzertifikat in eine lokale Datei in der ersten Appliance zu exportieren. Kopieren Sie dann das exportierte Zertifikat, und installieren Sie es in Ihren PSTN-Gateways.

  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Renew-CcCACertificate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

