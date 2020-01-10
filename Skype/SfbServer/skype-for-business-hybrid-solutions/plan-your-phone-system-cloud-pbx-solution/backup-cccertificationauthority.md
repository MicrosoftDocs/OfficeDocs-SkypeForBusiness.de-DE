---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003025"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Das Cmdlet „Backup-CcCertificationAuthority“ sichert den Zertifizierungsstellendienst von Skype for Business Cloud Connector Edition in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert, und diese wird im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts gespeichert:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Die Sicherung der Zertifizierungsstelle kann hilfreich sein, wenn Sie beabsichtigen, eine Cloud Connector-Appliance mit demselben Zertifikat für Notfälle erneut bereitzustellen, oder wenn Sie die Appliance auf eine neue Hardware verschieben möchten. Der Befehl speichert die Kopie des Diensts für die Cloud Connector-Zertifizierungsstelle vom anzeigen Server\<auf\>"SiteRootDirectory \CA\SfB CCE root. p12".
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Backup-CcCertificationAuthority“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

