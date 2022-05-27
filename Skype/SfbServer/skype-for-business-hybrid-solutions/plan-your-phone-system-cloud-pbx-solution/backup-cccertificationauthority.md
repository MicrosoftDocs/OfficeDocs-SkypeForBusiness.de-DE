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
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Das cmdlet Backup-CcCertificationAuthority sichert den Skype for Business Cloud Connector Edition Zertifizierungsstellendienst in einer Datei und speichert sie im Ca-Ordner unter dem Websitefreigabeverzeichnis.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675457"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Das cmdlet Backup-CcCertificationAuthority sichert den Skype for Business Cloud Connector Edition-Zertifizierungsstellendienst in einer Datei. Das Cmdlet speichert es auch im Ca-Ordner unter dem Websitefreigabeverzeichnis.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>Parameter

Keine

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der Zertifizierungsstellendienst in einer Datei gesichert und im Ca-Ordner unter dem Websitefreigabeverzeichnis gespeichert:

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Die Sicherung der Zertifizierungsstelle kann hilfreich sein, wenn Sie die erneute Bereitstellung einer Cloud Connector-Appliance mit demselben Zertifikat planen. Beispiel:

- Notfallwiederherstellung.
- Verschieben sie die Appliance auf neue Hardware.

Der Befehl speichert die Kopie des Cloud Connector-Zertifizierungsstellendiensts vom AD Server in `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`.

## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Backup-CcCertificationAuthority-Cmdlet akzeptiert keine weitergeleitete Eingabe.

## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine

## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  