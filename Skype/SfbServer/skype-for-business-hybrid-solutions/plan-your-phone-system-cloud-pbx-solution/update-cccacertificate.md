---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Das Cmdlet Update-CcCACertificate erneuert das Skype for Business Cloud Connector Edition-Stammzertifizierungsstellen-Zertifikat, das nahezu abgelaufen ist oder bereits abgelaufen ist.
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824119"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Das Cmdlet Update-CcCACertificate erneuert das Skype for Business Cloud Connector Edition-Stammzertifizierungsstellen-Zertifikat, das nahezu abgelaufen ist oder bereits abgelaufen ist. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine.
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird das Zertifikat der Stammzertifizierungsstelle erneuert:  
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Zertifikat der Stammzertifizierungsstelle für Cloud Connector ist fünf Jahre lang gültig, gerechnet ab dem Datum der Installation des Zertifizierungsstellendiensts.
  
Wenn das Stammzertifikat nahezu abgelaufen ist oder bereits abgelaufen ist, führen Sie das Cmdlet Update-CcCACertificate aus, um das Zertifikat zu erneuern. Nach der Erneuerung des Stammzertifikats werden automatisch neue Zertifikate für den AD-Server, den zentralen Verwaltungsspeicher und den Edgeserver ausgestellt.
  
Wenn mehrere Appliances auf derselben PSTN-Website vorhanden sind, führen Sie das Cmdlet Update-CcCACertificate in allen Appliances der gleichen PSTN-Website aus.
  
Letzter Schritt: Führen Sie das Cmdlet „Export-CcRootCertificate“ aus, um das Stammzertifikat in eine lokale Datei in der ersten Appliance zu exportieren. Kopieren Sie dann das exportierte Zertifikat, und installieren Sie es in Ihren PSTN-Gateways.

  
Dieser Befehl ersetzt das Cmdlet Renew-CcCACertificate in Cloud Connector 2,0 und höheren Versionen.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Update-CcCACertificate akzeptiert keine Pipelineeingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine. 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

