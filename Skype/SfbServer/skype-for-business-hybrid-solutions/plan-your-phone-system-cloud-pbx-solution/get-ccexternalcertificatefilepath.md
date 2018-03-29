---
title: Get-CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
ms.openlocfilehash: 9ceba99310ab25676a7cd3938ed386c4752f453e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Das Cmdlet „Get-CcExternalCertificateFilePath“ gibt den Pfad der externen Zertifikatdatei für die Skype for Business Cloud Connector Edition-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.
  
Dieses Cmdlet gilt für Skype for Business Cloud Connector Edition 1.4.1 und 1.4.2.
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt den Pfad des Zertifikats für den Edgeserver an:
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Beispiel 2

Das folgende Beispiel zeigt das für den Vermittlungsserver festgelegte Zertifikat an:
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Bei der Bereitstellung oder beim Ändern der Topologie müssen Sie den Pfad für das Zertifikat des Edgeservers und optional des Vermittlungsservers angeben. Das Zertifikat für den Vermittlungsserver ist erforderlich, wenn zwischen den Gateways und dem Vermittlungsserver TLS verwendet wird. Um den Pfad zu ändern, verwenden Sie das Cmdlet „Set-CcExternalCertificateFilePath“.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|Target  <br/> |Optional  <br/> | System.Management.Automation.SwitchParameter <br/> |Der Typ des angeforderten Dateipfads. Mögliche Typen:  <br/> „EdgeServer“ (Standard)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Das Cmdlet „Get-CcExternalCertificateFilePath“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Der Befehl gibt einen Dateipfad zurück.
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

