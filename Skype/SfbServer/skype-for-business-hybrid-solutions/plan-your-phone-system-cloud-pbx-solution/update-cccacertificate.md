---
title: Update-CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Das Cmdlet Update-CcCACertificate erneuert das Skype für Business Cloud Connector Edition Stammzertifikat der Zertifizierungsstelle, die in der Nähe Ablauf oder bereits abgelaufen ist.
ms.openlocfilehash: f23298f1be30ab96b3e77ff0625ff6e3b419e111
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Das Cmdlet Update-CcCACertificate erneuert das Skype für Business Cloud Connector Edition Stammzertifikat der Zertifizierungsstelle, die in der Nähe Ablauf oder bereits abgelaufen ist. 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine.
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert:  
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.
  
Wenn das Stammzertifikat in Ihrer Nähe Ablauf oder bereits abgelaufen ist, führen Sie das Cmdlet Update-CcCACertificate, um das Zertifikat zu erneuern. Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.
  
Wenn mehrere Einheiten auf der gleichen PSTN-Website vorhanden sind, führen Sie das Cmdlet Update-CcCACertificate in alle am gleichen Standort der PSTN-Einheiten.
  
Als letzten Schritt ausführen, um das Stammzertifikat in einer lokalen Datei in die erste Appliance exportieren Export-CcRootCertificate und klicken Sie dann kopieren Sie und installieren Sie das exportierte Zertifikat zu PSTN-Gateways.
  
Mit diesem Befehl wird das Cmdlet erneuern CcCACertificate in der Cloud Connector 2.0 und spätere Versionen ersetzt.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Update-CcCACertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine. 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Erneuern CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

