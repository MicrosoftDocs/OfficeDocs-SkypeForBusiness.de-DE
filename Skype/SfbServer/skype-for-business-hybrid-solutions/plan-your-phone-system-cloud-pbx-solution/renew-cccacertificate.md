---
title: Erneuern CcCACertificate
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
ms.openlocfilehash: bfcf7c69e27af8ebf83c85a8c90cc46491fbc454
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="renew-cccacertificate"></a>Erneuern CcCACertificate
 
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
  
Als letzten Schritt ausführen, um das Stammzertifikat in einer lokalen Datei in die erste Appliance exportieren Export-CcRootCertificate und klicken Sie dann kopieren Sie und installieren Sie das exportierte Zertifikat zu PSTN-Gateways.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Renew-CcCACertificate“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Erneuern CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

