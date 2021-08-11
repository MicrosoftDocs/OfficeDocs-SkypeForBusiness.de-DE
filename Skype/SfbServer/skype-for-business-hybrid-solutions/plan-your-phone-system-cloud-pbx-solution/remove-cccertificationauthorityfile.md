---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Das Cmdlet Remove-CcCertificationAuthorityFile entfernt die Sicherungsdatei des Zertifizierungsstellendiensts im Zertifizierungsstellenordner unter dem Websitefreigabeverzeichnis für Skype for Business Cloud Connector Edition.
ms.openlocfilehash: aaff21023a63e8933235f4c462c1152339381ca0d9571ded57f6b43742679624
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288773"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
Das cmdlet Remove-CcCertificationAuthorityFile entfernt die Sicherungsdatei &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12" im Zertifizierungsstellenordner unter dem Websitefreigabeverzeichnis für Skype for Business Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Sicherungsdatei &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12" des Zertifizierungsstellendiensts im Ordner "Zertifizierungsstellendienst" im Verzeichnis "SiteRootDirectory \CA\SfB CCE Root.p12" entfernt:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Remove-CcCertificationAuthorityFile akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

