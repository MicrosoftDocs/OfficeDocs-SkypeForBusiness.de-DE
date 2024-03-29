---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Das Cmdlet Reset-CcCACertificate installiert den AD Server des Zertifizierungsstellendiensts neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.
ms.openlocfilehash: 21f62724f74504216bcd38f5498b3a7068722512
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624967"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Das Cmdlet Reset-CcCACertificate installiert den AD Server des Zertifizierungsstellendiensts neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der AD-Server des Zertifizierungsstellendiensts neu installiert, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn das Zertifikat der Stammzertifizierungsstelle kompromittiert oder nicht mehr sicher ist, müssen Sie das Zertifikat der Stammzertifizierungsstelle und alle von der Stammzertifizierungsstelle ausgestellten Zertifikate aktualisieren. Das cmdlet Reset-CcCACertificate widerruft alle Zertifikate, deinstalliert und installiert die Zertifizierungsstelle neu, und bereinigt dann alle Zertifikate im Zusammenhang mit dem alten Zertifizierungsstellendienst. 
  
Weitere Informationen finden Sie unter "Zertifizierungsstellenzertifikate oder interne Zertifikate, die für CMS, Vermittlungsserver und Edgeserver ausgestellt wurden, laufen in Kürze ab oder sind kompromittiert" in der Problembehandlung für Ihre Cloud Connector-Bereitstellung.
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Reset-CcCACertificate akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

None.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Nur Version 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Nur Version 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 und höher
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 und höher
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

