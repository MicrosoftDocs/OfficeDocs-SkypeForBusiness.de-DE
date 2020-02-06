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
description: Das Cmdlet Remove-CcCertificationAuthorityFile entfernt die Sicherungsdatei des Zertifizierungsstellendiensts im Ordner "Zertifizierungsstelle" unter dem Website Freigabeverzeichnis für Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824291"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
Das Cmdlet Remove-CcCertificationAuthorityFile entfernt die Zertifizierungsstellen-Dienst Sicherungs&lt;Datei&gt;"SiteRootDirectory \CA\SfB CCE root. p12" im Ordner "Zertifizierungsstelle" unter dem Website Freigabeverzeichnis für Skype for Business Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Sicherungsdatei des Zertifizierungsstellen&lt;Diensts&gt;"SiteRootDirectory \CA\SfB CCE root. p12" im Ordner "Zertifizierungsstelle" unterhalb des Website Freigabe Verzeichnisses entfernt:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Remove-CcCertificationAuthorityFile“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

