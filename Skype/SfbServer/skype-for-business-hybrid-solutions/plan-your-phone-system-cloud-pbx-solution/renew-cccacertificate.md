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
description: Das Cmdlet Renew-CcCACertificate erneuert das zertifikat der stammzertifizierungsstelle Skype for Business Cloud Connector Edition, das bald abläuft oder bereits abgelaufen ist. Dieser Befehl wurde in Update-CcCACertificate in Cloud Connector 2.0 und neueren Versionen geändert.
ms.openlocfilehash: 49b58e18d6393d5a3f9665fea98cba73f22d9c3259f0036dc93dce9dbf67e567
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340781"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Das Cmdlet Renew-CcCACertificate erneuert das zertifikat der stammzertifizierungsstelle Skype for Business Cloud Connector Edition, das bald abläuft oder bereits abgelaufen ist. Dieser Befehl wurde in Update-CcCACertificate in Cloud Connector 2.0 und neueren Versionen geändert.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cloud Connector-Stammzertifizierungsstellenzertifikat ist fünf Jahre ab dem Datum gültig, an dem der Zertifizierungsstellendienst installiert ist.
  
Wenn das Stammzertifikat bald abläuft oder bereits abgelaufen ist, führen Sie das Cmdlet Renew-CcCACertificate aus, um das Zertifikat zu erneuern. Nachdem das Stammzertifikat erneuert wurde, werden dem AD-Server, der zentralen Store und dem Edgeserver automatisch neue Zertifikate ausgestellt.
  
Wenn mehrere Appliances am selben PSTN-Standort vorhanden sind, führen Sie das cmdlet Renew-CcCACertificate in allen Appliances desselben PSTN-Standorts aus.
  
Führen Sie als letzten Schritt Export-CcRootCertificate aus, um das Stammzertifikat in eine lokale Datei in der ersten Appliance zu exportieren, kopieren und installieren Sie dann das exportierte Zertifikat in Ihre PSTN-Gateways.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Renew-CcCACertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

