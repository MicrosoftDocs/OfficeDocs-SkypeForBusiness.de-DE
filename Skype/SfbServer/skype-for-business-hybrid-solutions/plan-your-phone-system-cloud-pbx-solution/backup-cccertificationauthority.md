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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das cmdlet Backup-CcCertificationAuthority sichert den Skype for Business Cloud Connector Edition Zertifizierungsstellendienst in einer Datei und speichert ihn im Ca-Ordner unter dem Websitefreigabeverzeichnis.
ms.openlocfilehash: abf94977abe2a0c3548b549ae0101ae399e124769eaaa9f05aabf203c69656a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282957"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Das cmdlet Backup-CcCertificationAuthority sichert den Skype for Business Cloud Connector Edition Zertifizierungsstellendienst in einer Datei und speichert ihn im Ca-Ordner unter dem Websitefreigabeverzeichnis.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Parameter

Keine
  
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert und im Ca-Ordner unter dem Websitefreigabeverzeichnis gespeichert:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Die Sicherung von Zertifizierungsstellen kann hilfreich sein, wenn Sie beabsichtigen, eine Cloud Connector-Appliance im Notfall mit demselben Zertifikat erneut bereitzustellen, oder wenn Sie die Appliance auf neue Hardware verschieben möchten. Der Befehl speichert die Kopie des Cloud Connector-Zertifizierungsstellendiensts vom AD-Server in \<SiteRootDirectory\> "\CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Backup-CcCertificationAuthority akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

