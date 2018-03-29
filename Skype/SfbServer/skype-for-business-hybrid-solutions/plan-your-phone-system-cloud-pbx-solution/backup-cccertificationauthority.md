---
title: Sicherung CcCertificationAuthority
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
ms.openlocfilehash: b3cb566dc72b3966eaa1480f3e17e4d6b46c06a2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="backup-cccertificationauthority"></a>Sicherung CcCertificationAuthority
 
Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert, und diese wird im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts gespeichert:
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Certification Authority Sicherung kann hilfreich sein, wenn Sie eine Cloud-Connector Appliance mit demselben Zertifikat bei einem Notfall erneut bereitstellen möchten, oder wenn Sie die Einheit auf neue Hardware verschieben möchten. Der Befehl speichert die Kopie der Dienst der Cloud Connector Zertifizierungsstelle aus den Active Directory-Server für "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Backup-CcCertificationAuthority“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

