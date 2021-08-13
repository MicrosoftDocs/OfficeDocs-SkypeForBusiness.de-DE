---
title: Get-CcExternalCertificateFilePath
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
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Das cmdlet Get-CcExternalCertificateFilePath gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
ms.openlocfilehash: 3f0a3bc761beb1a2aa1c88bfabf509e4aef17b012f52e04be1ec5944df73ba9c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315381"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Das cmdlet Get-CcExternalCertificateFilePath gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den Pfad des Zertifikats für den Edgeserver:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Beispiel 2

Das folgende Beispiel zeigt den Zertifikatsatz für den Vermittlungsserver:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Während der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Edgeserverzertifikat und optional für den Vermittlungsserver angeben. Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn TLS zwischen den Gateways und dem Vermittlungsserver verwendet wird. Verwenden Sie das Cmdlet Set-CcExternalCertificateFilePath, um den Pfad zu ändern.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Ziel  <br/> |Optional  <br/> | System.Management.Automation.SwitchParameter <br/> |Typ des angeforderten Dateipfads. Zu den Typen gehören:  <br/> EdgeServer (Standard)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Das Cmdlet Get-CcExternalCertificateFilePath akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

