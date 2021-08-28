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
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Das cmdlet Get-CcExternalCertificateFilePath gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622037"
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
|Target  <br/> |Optional  <br/> | System.Management.Automation.SwitchParameter <br/> |Typ des angeforderten Dateipfads. Zu den Typen gehören:  <br/> EdgeServer (Standard)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Das cmdlet Get-CcExternalCertificateFilePath akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

