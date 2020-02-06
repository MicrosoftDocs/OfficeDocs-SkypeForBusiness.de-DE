---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist. Dieser Befehl wurde in Update-CcCACertificate in Cloud Connector 2,0 und höheren Versionen geändert.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824271"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Das Cmdlet „Renew-CcCACertificate“ erneuert das Zertifikat der Stammzertifizierungsstelle für Skype for Business Cloud Connector Edition, das in Kürze abläuft oder bereits abgelaufen ist. Dieser Befehl wurde in Update-CcCACertificate in Cloud Connector 2,0 und höheren Versionen geändert.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert:  
  
```powershell
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
  

